#TO DO (read this *http://sparxsystems.com/resources/uml2_tutorial/ .* boys)

##Logical View
####UML Package Diagrams

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
##Deployment View
####UML Deployment Diagrams

##Process View
This view is the one who manages all of the dynamic aspects of the system, explains its processes and how they comunicate. It also addresses distribution of tasks, performance and integrators.
####UML Activity Diagrams
These diagrams are representations of the workflow of all of the activities and actions. The shapes used are:
	
	* rounded brown rectangles represent "actions"

	* diamonds representing "decisions"
	
	* black circle states the initial state of the flow
	
	* a circle with an "X" represents the final state of the flow

	* rounded green rectangles represent "activities"

Finally, the arrows point towards the next activity or action taken.
![Component Diagram](http://i.imgur.com/pKu8oKs.png?1)

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