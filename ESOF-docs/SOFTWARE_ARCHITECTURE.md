#TO DO (read this *http://sparxsystems.com/resources/uml2_tutorial/ .* boys)

#Introduction
In describing the architecture of reddit, it is useful to make a distinction between "reddit" the software and "reddit.com" the main user and developer of that software. reddit is able to run on a single machine, or through a data center with hundreds of machines. reddit.com is at the latter end of the spectrum and employs a few tricks that are outside of the reddit software itself as well. This architectural overview starts by describing what is intrinsic to reddit, and then goes on to explain what is currently set up for reddit.com.

# reddit (the software)

Unlike many other high-traffic sites, reddit is a very monolithic piece of software, for better or worse. The reddit application takes HTTP requests and does all the necessary work itself to fetch data from databases and build a proper response.

There are two core permanent data stores that reddit uses, PostgreSQL and Cassandra. Increasingly, ZooKeeper is becoming important for some forms of data storage, but its use remains optional at the code level right now. Memcached is used heavily to speed up many forms of lookup.

A fair (and increasing) amount of reddit's write workload is done outside of user requests to reduce the effect of processing slowdowns. Changes to be executed are queued up by a RabbitMQ messaging server and distributed out to backend jobs for processing.

## PostgreSQL

reddit uses [PostgreSQL](http://en.wikipedia.org/wiki/Postgres) in two distinct ways: through the *ThingDB* model, which is akin to a key/value store, and through more traditional relational models.

### ThingDB

The ThingDB model is the core Postgres data persistence mechanism for most of the objects that people would associate with reddit e.g. Links, Comments, Accounts, and Subreddits. In short, this data model is a mostly-schemaless key/value store that uses two tables for each thing type, its "thing" table and its "data" table.

The first table is the "thing" table. It has a fixed set of columns common to all things such as ID, whether or not the thing is deleted or marked spam, and the thing's upvote / downvote counts. Some of these columns are repurposed when they don't have a useful meaning for the thing type in question (e.g. a Subreddit's "ups" is its number of subscribers). Having these frequently used attributes in a fixed schema makes it easy to do relatively fast sorts on the things.

ThingDB's flexibility comes in through the "data" table. For every attribute on a thing that isn't represented by a column in the thing table, a row is created in the data table. This allows zero-effort flexibility in the schema of things, but does mean higher overhead via joins and the like to fetch the data.

Lookups done through the ThingDB model can fetch individual items or groups of items in batch. Writes are always done one item at a time.

### Relational data

There is some data that's stored in a more traditional relational form, including traffic statistics and transaction information for selling ads and gold subscriptions. This isn't terribly unique to reddit and not worth much more description.

## Cassandra

[Apache Cassandra](http://en.wikipedia.org/wiki/Apache_cassandra) is a distributed key/value datastore. It offers transparent [sharding](http://en.wikipedia.org/wiki/Shard_(database_architecture)) and is resistant to hardware failures.

### Memcached

[Memcached](http://en.wikipedia.org/wiki/Memcached) is used very heavily throughout reddit to add fast-access caching. This is the first of many layers of cache that sciteit uses. Commonly used bits of pretty much anything are stored in memory so they can be quickly accessed as needed.

There are several distinct ways

* sgm

* [pagecache](https://github.com/PHOENIX-MEDIA/Magento-PageCache-powered-by-Varnish) - An internal cache of certain logged-out reddit responses, to reduce database load and improve responsiveness.

* [rendercache](https://https://www.drupal.org/project/render_cache) - This module attempts to alleviate needless rebuilding and re-rendering of entities on subsequent page loads by caching.
When an entity is updated a new cache key is generated; there's no waiting for a cache to time out.

* [memoize](https://clojuredocs.org/clojure.core/memoize) - Returns a memoized version of a referentially transparent function. The
memoized version of the function keeps a cache of the mapping from arguments
to results and, when calls with the same arguments are repeated often, has
higher performance at the expense of higher memory use.

## Asynchronous messages via RabbitMQ

Many tasks take a large amount of time to execute and would be ill suited to happen in-request while the user is waiting. Certain tasks that get performed regularly, such as needing to update the number of votes or add something to the search index, shouldn't hold up the main reddit app. Instead the main app writes these things to a queue, rabbit-mq managers these queues and executes the tasks when there are resources to do so.

## ZooKeeper

Unlike a simple website that just runs on a single web server, a site like Reddit uses a cluster of servers. Doing this allows the load to be spread about, and also to better cope with failures of single servers.
One product for controlling this sort of arrangement is called Apache Zookeeper.

Apache ZooKeeper is an effort to develop and maintain an open-source server which enables highly reliable distributed coordination. ZooKeeper is a centralized service for maintaining configuration information, naming, providing distributed synchronization, and providing group services. All of these kinds of services are used in some form or another by distributed applications.

## reddit.com

TODO


##Logical View
####UML Package Diagrams

##Implemation View
####UML Component Diagrams

##Deployment View
####UML Deployment Diagrams

##Process View
####(?) "Shows how, at run-time", the system is composed of interacting processes."

##Use Case View
####(+1) "Relates all of the other views."

#References
*https://www.reddit.com/r/redditdev/comments/3mztkk/making_reddit_documentation/*
1 - someone has an idea

2 - people in charge approve of idea and assign a developer to work on it

3 - developer works on it and puts it into a pull request

4 - developer makes changes based on code review and product review

5 - deploy the feature to a subset of users

6 - iterate on feedback

7 - deploy to more users

8 - iterate on feedback

9 - deploy to everyone