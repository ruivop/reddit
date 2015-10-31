#Software Architecture (4+1 view model)

##Logical View
####UML Class diagram, Communication diagram, Sequence diagram

##Implemation View
This particular view focuses on how reddit is built, which technological elements are required to run the system and its configurability, testability, etc and the existing frameworks and libraries it uses.
The components and connectors that are referred to in the next scope reflect software entities and their relationships.

We have two types of components, the application components, that are responsible for implementing domain-level responsibilies and the the infrastructure components, the ones needed to run the system but are not directly related to the application functionality. The only thing that states if a certain component is an application or infrastructure component is the application being studied.

####UML Component Diagrams
A component diagram represents how differente components can be intertwined to form larger components and software systems. A component is the requirement to run an executable, a document, a database or a library.
All of these components' interfaces are connected by an assembly connector. This relationship creates a provider and a consumer.

There are two types of connectors:

The assembly connector connects two different components, and labeling one as the provider and the other as the consumer. This connector is defined from an interface/port to a provided one.

The delegation connector links the external part of a component to its internal realization of the behavior of the component.

![Component Diagram](http://i.imgur.com/ALqdG83.png?1)
##Physical View
####UML Deployment Diagrams

##Process View
This view is the one who manages all of the dynamic aspects of the system, explains its processes and how they comunicate. It also addresses distribution of tasks, performance and integrators.
####UML Activity Diagrams
These diagrams are representations of the workflow of all of the activities and actions. The shapes used are:
	
	- Rounded brown rectangles represent "actions"

	- Diamonds representing "decisions"
	
	- Black circle states the initial state of the flow
	
	- Circle with an "X" represents the final state of the flow

	- Rounded green rectangles represent "activities"

Finally, the arrows point towards the next activity or action taken.

![Component Diagram](http://i.imgur.com/pKu8oKs.png?1)

##Use Case View
The use case view is a list of actions and its steps to achieve a goal. The actor (in this case the user) has follow the steps correctly to reach his main goal.
The analysis of the use case is important to analise all of the requirements that are requested.
This view provides the summary of what the system has to offer and the body of the project. It also puts everyone on sync on what needs to be done and how it has to be done.
###User Case Diagrams
####Subreddits
![User (subreddits)](http://i.imgur.com/vOugXTu.png?1)
#####Create a subreddit
Access the sidebar and click the button "Create your own subreddit".

Fill all the text area available (name, title, description, sidebar, submission text)-

Change the language, type of subreddit, the content options and the wiki option.

Set the filter for the posts, links and comments.
#####Search for a term
Access the sidebar and enter the term you're searching in the text box.

Sort the results by time, relevance, newest, hottest or on top.

It is also possible to do an advance search, adding the author of the post or the subreddit.
#####Modding a subreddit
It is only possible to mod a subreddit if you're invited to one or if you own a subreddit.
As a mod, you can:

Change the subreddit settings.

Edit the stylesheet (html).

Edit approved submitters.

Access the traffic stats.

Access the reports.

Access the spam.

Change banned and muted users.

Edit flairs.
####Threads
![User (threads)](http://i.imgur.com/xaRjfI1.png?1)
#####Post a thread
Access the sidebar and press "Submit a new link".

Create a link thread or a text thread.

Change the title.

Change the url it redirects to.

Choose the subreddit where you want to post the thread.
#####Comment a thread
Access a thread.

Fill the text box below the post.

Press "save".
#####Upvote/downvote a thread
Choose a thread.

Click on the arrow pointing up to upvote or click on the arrow pointing down to downvote.
#####Reply to a comment on a thread
Access a thread.

Choose the comment you want to reply to.

Press the "reply".

Fill the text box that just appeared.

Press "save".
####Flairs
![User (flair)](http://i.imgur.com/vhrEgUo.png?1)
#####Set a user flair
Access the sidebar and press the "edit flair" next to your username.

Choose the flair.

Press the checkbox that says "Show my flair on this subreddit. It looks like:".
###Set a thread flair
Create a thread.

Submit the thread.

Below the title of your thread press "flair".

Change to one that is available.
####Communication
![User (communication)](http://i.imgur.com/w8ho3XX.png?1)
#####Send private messages
Access www.reddit.com/user/username in which username is the user you want to send a message to.
####User preferences
![User (preferences)](http://i.imgur.com/Y95p4xM.png?1)
#####Change options
In the right side of the screen press "Preferences" next to your username.

Change the link, comment, messaging, display, content, privacy and beta options.
#####Manage applications
In the right side of the screen press "Preferences" next to your username.

Press "apps" in the tabs menu.

Manage your authorized applications (either revoke their access or don't).
#####Access RSS feeds
In the right side of the screen press "Preferences" next to your username.

Press "RSS feeds" in the tabs menu.

Access the private and moderator listings, private profile pages, user inbox and moderator inbox.
#####Add friends
In the right side of the screen press "Preferences" next to your username.

Press "friends" in the tabs menu.

Fill the text box with the username of whom you want to add as a friend.
#####Block users from messaging
Receive a message from the user you want to block.

In the right side of the screen, press the envelope next to your username.

Press "messages" in the tabs menu.

Search for a message from the user you want to block.

Press "block user" below the message.

Press "yes".
#####Unblock users from messaging
In the right side of the screen press "Preferences" next to your username.

Press "blocked" in the tabs menu.

Search for the user you want to remove from your blocked list, and press "remove" next to their username.

Press "yes."
#####Change e-mail
In the right side of the screen press "Preferences" next to your username.

Press "password/email" in the tabs menu.

Input your password.

Change your e-mail.

Press "save".
#####Change password
In the right side of the screen press "Preferences" next to your username.

Press "password/email" in the tabs menu.

Input your password.

Input your password twice.

Press "save".
#####Deleting the account
In the right side of the screen press "Preferences" next to your username.

Press "delete" in the tabs menu.

Input your account credentials.

Optionally, fill the text area explaining why you're deleting the account.

Press the checkbox saying "I understand that deleted accounts are not recoverable".

Press "delete account".

#References
*https://www.reddit.com/r/redditdev/comments/3mztkk/making_reddit_documentation/ *
*https://www.reddit.com/r/redditdev/comments/tszxg/trying_to_figure_out_the_reddit_code_is_there/c4pgo4x *
*https://www.reddit.com/r/redditdev/comments/3qjdz2/reddit_41_architectural_view_model/ *
*http://sparxsystems.com/resources/uml2_tutorial/ *
*https://en.wikipedia.org/wiki/Reddit *
*http://alistair.cockburn.us/Use+cases%2c+ten+years+later *
*http://alistair.cockburn.us/Why+I+still+use+use+cases *
