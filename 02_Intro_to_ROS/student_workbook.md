- Name: Noah Kustyn
- Date: 2/14/2023


# Introduction to ROS -- Self Study

---

- Use this document to help you study.
- For each item, make a list of questions that you have.  Identify all of the things that don't make sense to you.  Clearly denote these as questions.
- Also, make notes when you have answered a question.  Clearly denote these as things that you now understand.
- In the end, you should have no unanswered questions.

- This document is written in *markdown*.  It's a great language for documentation.  Here's a cheatsheet for you:  https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet

- You will be asked to turn in paper copies of your compiled document.  Please make sure it's neatly formatted.  I suggest using the 
`retext` software package that is already installed on your virtual machine.

---

## Textbook Chapters

### Chapter 1 -- Introduction

Just read this chapter...**DO NOT INSTALL ANYTHING**. Your virtual machine already has the software loaded and configured for you.  


- Unanswered Questions:
	- [I suggest making a bullet list of questions here]
	
- Answered Questions and/or General notes
	- [Again, bulleted lists are pretty nice]	


---

### Chapter 2 -- Preliminaries

Just read this chapter...**DO NOT INSTALL ANYTHING**. Your virtual machine already has the software loaded and configured for you.  

- Unanswered Questions:
	
- Answered Questions and/or General notes
- We refer to ROS programs as nodes, to help us remember that each program is just one piece of a much larger system.
- ROS graph nodes represent a software module that is sending or receiving messages, and ROS graph edges represent a stream of messages between two nodes.
- Packages are just locations in the filesystem.
- roslaunch will automatically instantiate a roscore if one does not exist when roslaunch is invoked.

---

### Chapter 3 -- Topics

- Unanswered Questions:
	
- Answered Questions and/or General notes
- A topic is a name for a stream of messages with a defined type.
- Topics implement a publish/subscribe communication mechanism, one of the more common ways to exchange data in a distributed system.
- In order to see a publishers messages, a subscriber will need the name of the topic, the message type of the topic, and the name of the callback function.
- Use existing message types and SI units whenever possible.
- A single node can have multiple publications and subscriptions.

---

### Chapter 4 -- Services	

- Unanswered Questions:
	
- Answered Questions and/or General notes
- Services are just synchronous remote procedure calls; they allow one node to call a function that executes in another node.
- The simplest way to use a service is to call it using the rosservice command.
- We can subscribe to topics that are not yet advertised, but we can only use advertised services.
- If you omit arguments that the service needs to run, you might get strange return values.

---

### Chapter 5 -- Actions

- Unanswered Questions:
	
- Answered Questions and/or General notes
- While services are synchronous, actions are asynchronous.
- Similar to the request and response of a service, an action uses a goal to initiate a behavior and sends a result when the behavior is complete.
- The action further uses feedback to provide updates on the behavior’s progress toward the goal and also allows for goals to be canceled.
- Actions are themselves implemented using topics.
- The first step in creating a new action is to define the goal, result, and feedback message formats in an action definition file.
- While service definitions have two parts (request and response), action definitions have three parts (goal, result, and feedback).


---

## ROS Tutorials

- *In several of the links below, you'll be given options to follow the "catkin" or "rosbuild" materials.*  
**Select "catkin"**.  

### 1)  [Navigating the ROS Filesystem](http://wiki.ros.org/ROS/Tutorials/NavigatingTheFilesystem)

This tutorial introduces ROS filesystem concepts, and covers using the `roscd`, `rosls`, and `rospack` commandline tools.

- Unanswered Questions:
	
- Answered Questions and/or General notes
- rospack allows you to get information about packages.
- roscd allows you to change directory directly to a package or a stack.
- roscd can also move to a subdirectory of a package or stack.
- rosls allows you to list directly in a package by name rather than by absolute path.


### 2)  [Creating a ROS Package](http://wiki.ros.org/ROS/Tutorials/CreatingPackage)

This tutorial covers using catkin to create a new package, and rospack to list package dependencies.

**IN SECTION 4, DO NOT ADD THE WORKSPACE TO YOUR ROS ENVIRONMENT:**

> ~~$ . \~/catkin_ws/devel/setup.bash~~ 

*This has already been done for you in your virtual machine.*


- Unanswered Questions:
	
- Answered Questions and/or General notes
- The package must contain a catkin compliant package.xml file.
- The package must contain a CMakeLists.txt which uses catkin.
- Each package must have its own folder
- You can customize a package by updating the description tag, maintainer tag, license tag, and dependencies tag.


				
### 3) [Building a ROS Package](http://wiki.ros.org/ROS/Tutorials/BuildingPackages)

**IN SECTION 1, DO NOT DO THIS:**
> ~~# source /opt/ros/\<YOUR_ROS_DISTRO\>/setup.bash~~

> ~~$ source /opt/ros/kinetic/setup.bash             # For Kinetic for instance~~

*This has already been done for you in your virtual machine.*


- Unanswered Questions:
	
- Answered Questions and/or General notes
- Note that catkin_make first displays what paths it is using for each of the 'spaces'.
- The build folder is the default location of the build space and is where cmake and make are called to configure and build your packages.
- The devel folder is the default location of the devel space, which is where your executables and libraries go before you install your packages.



### 4)  [Understanding ROS Nodes](http://wiki.ros.org/ROS/Tutorials/UnderstandingNodes)

This tutorial introduces ROS graph concepts and discusses the use of `roscore`, `rosnode`, and `rosrun` commandline tools.		

**IN SECTION 1, DO NOT DO THIS:**
> ~~$ sudo apt-get install ros-\<distro\>-ros-tutorials~~
	
*This has already been done for you in your virtual machine.*


- Unanswered Questions:
	
- Answered Questions and/or General notes
- ROS nodes use a ROS client library to communicate with other nodes.
- Nodes can publish or subscribe to a Topic and provide or use a Service.
- rosrun allows you to use the package name to directly run a node within a package.
- rosnode is a ROS tool which gives information about a node.



### 5) [Understanding ROS Topics](http://wiki.ros.org/ROS/Tutorials/UnderstandingTopics)

This tutorial introduces ROS topics as well as using the rostopic and rqt_plot commandline tools.

**IN SECTION 2.1, DO NOT DO THIS:**
> ~~$ sudo apt-get install ros-\<distro\>-rqt~~

> ~~$ sudo apt-get install ros-\<distro\>-rqt-common-plugins~~

*Your virtual machine already has these things installed.*


- Unanswered Questions:
	
- Answered Questions and/or General notes
- rostopic echo shows the data published on a topic.
- rostopic list returns a list of all topics currently subscribed to and published.
- Communication on topics happens by sending ROS messages between nodes.
- The type of the message sent on a topic can be determined using rostopic type.
- rostopic pub publishes data on to a topic currently advertised.


### 6)  [Understanding ROS Services and Parameters](http://wiki.ros.org/ROS/Tutorials/UnderstandingServicesParams)

This tutorial introduces ROS services, and parameters as well as using the `rosservice` and `rosparam` commandline tools.

- Unanswered Questions:
	
- Answered Questions and/or General notes


### 7)  [Creating a ROS msg and srv](http://wiki.ros.org/ROS/Tutorials/CreatingMsgAndSrv)

This tutorial covers how to create and build msg and srv files as well as the `rosmsg`, `rossrv` and `roscp` commandline tools.

- Unanswered Questions:
	
- Answered Questions and/or General notes


### 8a)  [Writing a Simple Publisher and Subscriber (Python)](http://wiki.ros.org/ROS/Tutorials/WritingPublisherSubscriber%28python%29)

This tutorial covers how to write a publisher and subscriber node in python.

- Unanswered Questions:
	
- Answered Questions and/or General notes


### 8b)  [Examining the Simple Publisher and Subscriber](http://wiki.ros.org/ROS/Tutorials/ExaminingPublisherSubscriber)

This tutorial examines running the simple publisher and subscriber.

- Unanswered Questions:
	
- Answered Questions and/or General notes


### 9a)  [Writing a Simple Service and Client (Python)](http://wiki.ros.org/ROS/Tutorials/WritingServiceClient%28python%29)

This tutorial covers how to write a service and client node in python.

- Unanswered Questions:
	
- Answered Questions and/or General notes


### 9b)  [Examining the Simple Service and Client](http://wiki.ros.org/ROS/Tutorials/ExaminingServiceClient)

This tutorial examines running the simple service and client.

- Unanswered Questions:
	
- Answered Questions and/or General notes

---

## Textbook Github Site

Please take a few moments to familiarize yourself with these resources:

- https://github.com/osrf/rosbook
- https://github.com/osrf/rosbook/issues?utf8=✓&q=
- https://www.oreilly.com/catalog/errata.csp?isbn=0636920024736

These will come in handy throughout the semester.


