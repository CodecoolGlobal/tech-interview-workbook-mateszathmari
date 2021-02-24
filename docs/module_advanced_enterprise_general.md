# General enterprise questions

## Software engineering

### Architectures

#### What is n-tier (or multi-tier) architecture?
N-tier architecture is also called multi-tier architecture because the software is engineered to have the processing, data management, and presentation functions physically and logically separated.  That means that these different functions are hosted on several machines or clusters, ensuring that services are provided without resources being shared and, as such, these services are delivered at top capacity.  The “N” in the name n-tier architecture refers to any number from 1.

 
Important:
- there should be separate components / layers (SoC)
- the layers ideally should have a linear, hierarchical structure
- the layers should interact only with their direct neighbor below them


#### What are microservices? Advantages and disadvantages?
Microservices are a way of breaking large software projects into loosely coupled modules, which communicate with each other through simple Application Programming Interfaces (APIs). Advantages of microservice:

Smaller and faster developments
Scalability
Ease of understanding
Improved fault isolation
Eliminate vendor or technology lock-in
Disadvantages of microservices:

Communication between services is complex
More services equal more resources
Global testing difficulty
Debugging problems can be harder

#### What is Separation of Concerns?
Separation of concerns (SoC) is a design principle for separating a computer program into distinct sections such that each section addresses a separate concern. At a low level, this principle is closely related to the Single Responsibility Principle of object oriented programming. For example the business logic of the application is a concern and the user interface is another concern. Changing the user interface should not require changes to business logic and vice versa. The design will be more maintainable, less tightly coupled, and less likely to violate the Don’t Repeat Yourself principle. When concerns are well-separated, individual sections can be reused, as well as developed and updated independently. At an architectural level, separation of concerns is a key component of building layered applications.

#### What is a layered design and why is it important in enterprise applications?
Layered architecture are n-tiered patterns where the components are organized in horizontal layers. This is the traditional method for designing most software and is meant to be self-independent. All components are interconnected but not dependent on each other. Layered architecture has 4 layers

Presentation layer – contains all categories related to the presentation layer
Business layer – business logic
Persistence layer – used for function like object-relational mapping
Database layer – where all data is stored
Using a layered design for an enterprise application has a series of benefits, such as easy to test as components because are separated on different layers and easy to implement.

#### What is Dependency Injection?
Dependency injection is a technique whereby one object supplies the dependencies of another object. Dependency injection is basically providing the objects that an object needs (its dependencies) instead of having it construct them itself.

Dependencies can be injected into objects by many means:

constructor injection
setter injection
interface injection
dependency injection frameworks (e.g. Spring)
So now its the dependency injection’s responsibility to:

Create the objects
Know which classes require those objects
And provide them all those objects
If there is any change in objects, then DI looks into it and it should not concern the class using those objects. This way if the objects change in the future, then its DI’s responsibility to provide the appropriate objects to the class.

Inversion of control —the concept behind DI This states that a class should not configure its dependencies statically but should be configured by some other class from outside.

Benefits of using DI:

Helps in Unit testing.
Boiler plate code is reduced, as initializing of dependencies is done by the injector - component.
Extending the application becomes easier.
Helps to enable loose coupling, which is important in application programming.


#### What is the DAO pattern? When and how to implement?
The Data Access Object (DAO) pattern is a structural pattern that allows us to isolate the application / business layer from the persistence layer (usually a relational database, but it could be any other persistence mechanism) using an abstract API. The functionality of this API is to hide from the application all the complexities involved in performing CRUD operations in the underlying storage mechanism. This permits both layers to evolve separately without knowing anything about each other.

The participants in Data Access Object Pattern:

Data Access Object Interface - The interfaces which provides a flexible design. This interface defines the standard operations to be performed on a model object(s).

Data Access Object concrete class - This class implements above interface. This class is responsible to get data from a data source which can be database / xml or any other storage mechanism.

Model Object or Value Object - The model which is transferred from one layer to the other. This object is simple POJO containing get/set methods to store data retrieved using DAO class.

#### What is SOA? When to use?
SOA is an acronym for Service-oriented architecture, an architectural style of building software applications: a collection of services which are communicating with each other: this can be simply a data passing or two or more services can coordinating an activity.

When to use?             
-If you want to integrate heterogeneous technologies and applications… eg. your database in postgres, you have code in Java and in Python
-If you want to keep business logic in one place (easier to change)
-Business process reuse (multiple use case for the same process - you can quickly create new business processes from existing services)



### Testing

#### What are unit test, integration test, system test, regression test, acceptance test? What is the major difference between these?

Unit test: The goal of Unit testing is to test each unit separately and ensure that each unit is working as expected. The unit test cases writing and execution is done by the developer (not the tester) to make sure that individual units are working as expected. The scope of Unit testing is narrow, it covers the Unit or small piece of code under test. The smallest part of individual components like functions, procedures, classes, interfaces etc. The main intention of this activity is to check whether units are working as per design and handling error and exception more neatly. The both positive and negative conditions should handle properly. Unit tests should have no dependencies on code outside the unit tested. Complex dependencies and interactions to the outside world are stubbed or mocked. This is very first step in level of testing and started before doing integration testing.

Integration test: Once all modules are developed and integrated with other modules then Integration testing is to be carried out to discover the issues arise when different modules are interacting with each other to build overall system. Integration testing is a type of testing to check if different pieces of the modules are working together. The scope of Integration testing is wide, it covers the whole application under test and it requires much more effort to put together. Integration testing is dependent on other outside systems like databases, hardware allocated for them etc.

System test: System testing is the type of testing to check the behaviour of a complete and fully integrated software product based on the software requirements specification (SRS) document. The main focus of this testing is to evaluate Business / Functional / End-user requirements. This is black box type of testing where external working of the software is evaluated with the help of requirement documents & it is totally based on Users point of view. For this type of testing do not required knowledge of internal design or structure or code. This testing is to be carried out only after System Integration Testing is completed. In the integration testing testers are concentrated on finding bugs/defects on integrated modules. But in the Software System Testing testers are concentrated on finding bugs/defects based on software application behavior, software design and expectation of end user.

Regression test: Regression testing is type of testing carried out to ensure that changes made in the fixes or any enhancement changes are not impacting the previously working functionality. It is executed after enhancement or defect fixes in the software or its environment.

Acceptance test: User acceptance is a type of testing performed by the Client to certify the system with respect to the requirements that was agreed upon. This is beta testing of the product & evaluated by the actual end users. The main purpose of this testing is to validate the end to end business flow.

#### What is code coverage? Why is it used? How you can measure?
Code coverage is an important concept in software testing, which measures to what extent the code of a program is covered by automated tests, ie. how many code lines, methods, etc. are run and tested by the set of tests.

Code coverage is usually measured as a percentage of the functions, statements, branches (eg. if-else), lines of code actually tested when the test suite is run. The bigger the percentage, the smaller the chance that undetected bugs remain in the program.

#### What does mocking mean? How would you do it 'manually' (i. e. without using any fancy framework)?
Mocking is primarily used in unit testing. An object under test may have dependencies on other (complex) objects. To isolate the behavior of the object you want to replace the other objects by mocks that simulate the behavior of the real objects. This is useful if the real objects are impractical to incorporate into the unit test. In short, mocking is creating objects that simulate the behavior of real objects.

#### What is a test case? What is an assertion? Give examples!
An assertion is a boolean expression at a specific point in a program which will be true unless there is a bug in the program. A test assertion is defined as an expression, which encapsulates some testable logic specified about a target under test. Usually the logic for each test assertion is limited to one single aspect specified. An assertion allows testing the correctness of any assumptions that have been made in the program. If an assertion fails, the method call does not return and an error is reported. If a test contains multiple assertions, any that follow the one that failed will not be executed. For this reason, it's usually best to try for one assertion per test.

Example:

public int Add (int num1, int num2) { return num1 + num2 }

int expected = 5 Int actual = Add(2, 3)

Assert.AreEqual(expected, actual);

#### What is TDD? What are the benefits?
TDD is for test-driven development. This is a software development process, relies on repeating a very short development cycle. The guts of this process is to write tests first, then write code to pass the tests. 
 - write tests: first the developer has to understand the feature’s specification, and write unit tests for it.
 - run all tests, make them fail: this step makes sure, that the tests does not succeed accidentally, without any code was written. 
 - write the code: need explanation?
 - run tests: if all tests pass, the developer can be sure that the written code works well.
 - refactor: this is a good point to check the code base, and clean it up. 
 - repeat


#### What are the unit testing best practices? (Eg. how many assertion should a test case contain?)
Naming your tests: The name of your test should consist of three parts:
The name of the method being tested.
The scenario under which it's being tested.
The expected behavior when the scenario is invoked.
For example: Add_SingleNumber_ReturnsSameNumber()

Avoid logic in tests: When writing your unit tests avoid manual string concatenation and logical conditions such as if, while, for, etc.
Check only a single thing in one test method (practically: use 1 assert per test method)
Never push a failing test to the repository. (Use @Ignore if really necessary.)
Use separate folder for tests as you might not want to deliver (ie. give to the user) your test along with the production code.

#### What is arrange/act/assert pattern?
Arrange your objects, creating and setting them up as necessary.
Act on an object.
Assert that something is as expected.
```
public void Add_EmptyString_ReturnsZero()
{
    // Arrange
    var stringCalculator = new StringCalculator();

    // Act
    var actual = stringCalculator.Add("");

    // Assert
    Assert.Equal(0, actual);
}
```


### DevOps

#### What is continuous integration? Why is CI important?
Continuous integration (CI) is the practice of automating the integration of code changes from multiple contributors into a single software project. The CI process is comprised of automatic tools that assert the new code’s correctness before integration

CI is an asset to a software producing organization. CI benefits are not limited to the engineering team but greatly benefit the overall organization. CI enables better transparency and insight into the process of software development and delivery. These benefits enable the rest of the organization to better plan and execute go to market strategies.

#### Why are tests important in the CI workflow?
If you test and deploy code more frequently, it will eventually reduce the risk level of the project you are working on as you can detect bugs and code defects earlier. This means they are easier to fix and you can fix them sooner which makes it cheaper to fix them.


#### Name some software that help the CI workflow!
Jenkins
Travis
Circle CI
Gitlab CI

#### What is Continuous Delivery?
Continuous delivery is an extension of continuous integration to make sure that you can release new changes to your customers quickly in a sustainable way. This means that on top of having automated your testing, you also have automated your release process and you can deploy your application at any point of time by clicking on a button.

#### What is Continuous Deployment?
Continuous deployment goes one step further than continuous delivery. With this practice, every change that passes all stages of your production pipeline is released to your customers. There's no human intervention, and only a failed test will prevent a new change to be deployed to production.

Continuous deployment is an excellent way to accelerate the feedback loop with your customers and take pressure off the team as there isn't a Release Day anymore. Developers can focus on building software, and they see their work go live minutes after they've finished working on it.

#### What is DevOps?
DevOps (a compound word made from "Development" and "Operations") is a new practice and job role in Software development that emerged from the birth of the cloud and agile methodologies. It can be seen as an evolution of the SysAdmin role, but requires much more knowledge.

Typical tasks of a DevOps person is everything IT related except actually writing the software. In practice this means the following:

Build systems that enable CI/CD workflows
Manage the "cloud", set up its infrastructure, security, install and configure apps
Make sure that there are monitoring and alerting systems in place in case of issues
Automate everything: deployments, releases, upgrades.

### Software Methodologies

#### What kind of software-lifecycle models do you know?
A software lifecycle model is a standardised format for planning, organising and running a new development project.

Agile, Lean, Waterfall, Iterative, Spiral, DevOps, Extreme Programming, Rapid Prototyping

#### What is a UML diagram? What kind of diagram types do you know?
A UML diagram is a diagram based on the UML (Unified Modeling Language) with the purpose of visually representing a system along with its main actors, roles, actions, artifacts or classes, in order to better understand, alter, maintain, or document information about the system.

Class diagram
Package diagram

#### What is a UML class diagram? What are the typical elements?
A class diagram in the Unified Modeling Language (UML) is a type of static structure diagram that describes the structure of a system by showing the system's classes, their attributes, methods, and the relationships among objects.

The class diagram is the main building block of object-oriented modeling.

Elements:

Class
Attribute
Generalization
Association
Multiplicity
Aggregation

#### What kind of design patterns do you know? Bring at least 3 examples.
Factory Pattern - In Factory pattern, we create object without exposing the creation logic to the client and refer to newly created object using a common interface.

Singleton Pattern - This pattern involves a single class which is responsible to create an object while making sure that only single object gets created. This class provides a way to access its only object which can be accessed directly without need to instantiate the object of the class.

Iterator Pattern - This pattern is used to get a way to access the elements of a collection object in sequential manner without any need to know its underlying representation. The elements of an aggregate object can be accessed and traversed without exposing its representation (data structures).

MVC Pattern - MVC Pattern stands for Model-View-Controller Pattern. This pattern is used to separate application's concerns.

#### What is the purpose of the Iterator Pattern?
This pattern is used to get a way to access the elements of a collection object in sequential manner without any need to know its underlying representation. The elements of an aggregate object can be accessed and traversed without exposing its representation (data structures).

#### What do you know about the SOLID principles?
These 5 principles were introduced by Robert C. Martin (Uncle Bob), in his 2000 paper Design Principles and Design Patterns. The intention of these principles is to make software designs more understandable, easier to maintain and easier to extend.

S — Single responsibility principle Every module or class should have responsibility over a single part of the functionality provided by the software.

O — Open/closed principle "Software entities ... should be open for extension, but closed for modification." We can make sure that our code is compliant with the open/closed principle by utilizing inheritance and/or implementing interfaces that enable classes to polymorphically substitute for each other.

L — Liskov substitution principle "Objects in a program should be replaceable with instances of their subtypes without altering the correctness of that program." If S is a subtype of T, then objects of type T may be replaced (or substituted) with objects of type S. More generally it states that objects in a program should be replaceable with instances of their subtypes without altering the correctness of that program.

I — Interface segregation principle "Many client-specific interfaces are better than one general-purpose interface." No client should be forced to depend on methods it does not use. Put more simply: Do not add additional functionality to an existing interface by adding new methods. Instead, create a new interface and let your class implement multiple interfaces if needed.

D - Dependency inversion principle "One should "depend upon abstractions, [not] concretions." Dependency inversion principle is a way to decouple software modules. This principle states that High-level modules should not depend on low-level modules. Both should depend on abstractions. Abstractions should not depend on details. Details should depend on abstractions.

#### How would you separate data storage code and business logic code (which uses stored data) in an application?
I would use MVC design pattern

## Computer science

### Data Structures

#### What is the difference between Stack and Queue data structure?
Queue and stack are both generic data collections.
Queues implement the so called FIFO (First-In-First-Out) method. The structure is designed to have elements be put at the end of the queue (add(e) or offer(e)) and be removed (remove() or poll()) from the beginning, much like a queue at the supermarket. The poll() and offer(e) methods can return special values in case of failure while add(e) and remove(e) throw exceptions.
Stacks implement the so called LIFO (Last-In-First-Out) method. The structure is designed much like a stack of plates on a shelf: you put the plate at the top of the stack, and take the plate from the top. Stacks offer methods for getting and removing the last item (pop()), pushing an item on the top of the stack (push(e)), taking a look at the element on the top without removing it (peek()).


#### What is a graph? What are simple graphs? What are directed graphs? What are weighted graphs?
A Graph is a non-linear data structure consisting of nodes and edges. The nodes are sometimes also referred to as vertices and the edges are lines or arcs that connect any two nodes in the graph. A node is a basic unit of a data structure, such as a linked list or tree data structure. Nodes contain data and also may link to other nodes. Links between nodes are often implemented by pointers.

Simple graph: A graph with no loops and no parallel edges is called a simple graph. Directed graph: In a directed graph, each edge has a direction. Weighted graphs: Each edge of a graph has an associated numerical value, called a weight. Usually, the edge weights are nonnegative integers. Weighted graphs may be either directed or undirected.

#### What are trees? What are binary trees? What are binary search trees?
Tree: A tree is an undirected graph in which any two vertices are connected by exactly one path. In a tree there exist only one path between any two vertices whereas a graph can have unidirectional and bidirectional paths between the nodes. In the tree, there is exactly one root node, and every child can have only one parent. As against, in a graph, there is no concept of the root node. Unlike Arrays, Linked Lists, Stack and queues, which are linear data structures, trees are hierarchical data structures.

Main applications of trees include:

Manipulate hierarchical data.
Make information easy to search (see tree traversal).
Manipulate sorted lists of data.
Router algorithms
Binary tree: a binary tree is a tree data structure in which each node has maximum two children, which are referred to as the left child and the right child.

Binary search tree: Binary Search Tree is a node-based binary tree data structure which has the following properties:

The left sub-tree of a node has a key less than or equal to its parent node's key.
The right sub-tree of a node has a key greater than to its parent node's key.
The above properties of Binary Search Tree provide an ordering among keys so that the operations like search, minimum and maximum can be done fast.

#### How can you store graphs in programs? What are the advantages/disadvantages per each?

A CSRF attack can be initialized using a GET or POST request and can make use of an Iframe with attributes that make it invisible.

#### What are graph traversal algorithms? What is BFS, how does it work? What is DFS, how does it work?

Breadth-First Search (BFS) is an algorithm used to traverse through all of the nodes within a graph, tree, etc. It uses a Queue, which is a list of the nodes the algorithm is going to visit, and the algorithm ends when the Queue is empty (indicating that their are no more nodes to be visited).

Depth-First Search (DFS) is a recursive algorithm that uses the idea of backtracking. It involves exhaustive searches of all the nodes by going ahead, if possible, else by backtracking. This recursive nature of DFS can be implemented using stacks.

#### How does dictionary work?
HashMap in C# works on hashing principle. It is a data structure which allows us to store object and retrieve it in constant time O(1) provided we know the key. In hashing, hash functions are used to link key and value in HashMap.

When we call put method, hashcode() method of the key object is called so that hash function of the map can find a bucket location to store value object. When you want to retrieve the object, you call the get() method and again pass the key object. This time again key object generate same hash code (it's mandatory for it to do so to retrieve the object and that's why HashMap keys are immutable e.g. String) and we end up at same bucket location.

#### Why is it important for keys in a hashmap to have an immutable type? (Consider string for example.)

If immutable, the object's hashcode wont change and it allows caching the hashcode of different keys which makes the overall retrieval process very fast. Also for mutable objects ,the hashCode() might be dependent on fields that could change, if this happens you wont be able to find the key (and its value) in the HashMap since hashCode() returns different value.


### Algorithms

#### What is QuickSort? Describe the main logic of this sorting algorithm.
QuickSort is one of the most efficient sorting algorithms and is based on the splitting of an array into smaller ones. The name comes from the fact that, quick sort is capable of sorting a list of data elements significantly faster than any of the common sorting algorithms.

Quicksort first divides a large array into two smaller sub-arrays: the low elements and the high elements. Quicksort can then recursively sort the sub-arrays. The steps are:

Pick an element, called a pivot, from the array.
Partitioning: reorder the array so that all elements with values less than the pivot come before the pivot, while all elements with values greater than the pivot come after it (equal values can go either way). After this partitioning, the pivot is in its final position. This is called the partition operation.
Recursively apply the above steps to the sub-array of elements with smaller values and separately to the sub-array of elements with greater values.


## Software design

### Security

#### What is OAuth2?
OAuth 2 is an authorization framework that enables applications to obtain limited access to user accounts on an HTTP service, such as Facebook, GitHub, Amazon... It works by delegating user authentication to the service that hosts the user account, and authorizing third-party applications to access the user account. It is commonly used as a way for Internet users to grant websites or applications access to their information on other websites but without giving them the passwords. OAuth essentially allows access tokens to be issued to third-party clients by an authorization server, with the approval of the resource owner. The third party then uses the access token to access the protected resources hosted by the resource server. OAuth 2 provides authorization flows for web and desktop applications, and mobile devices.

 


#### What is Basic Authentication?
Basic authentication is a simple authentication scheme built into the HTTP protocol. The client sends HTTP requests with the Authorization: Basic header, followed by credentials in the base64 encoding of id and password joined by a single colon (username:password).

#### What is CORS, why it's needed in browsers?
Cross-Origin Resource Sharing (CORS) is a mechanism that uses additional HTTP headers to tell browsers to give a web application running at one origin, access to selected resources from a different origin. A web application executes a cross-origin HTTP request when it requests a resource that has a different origin (domain, protocol, or port) from its own. An example of a cross-origin request: the front-end JavaScript code served from https://domain-a.com uses XMLHttpRequest to make a request for https://domain-b.com/data.json.

CORS is a way to bypass the "Same Origin Policy" which is the security measure preventing you from making ajax requests to a different domain.

Same Origin Policy For security reasons, browsers restrict cross-origin HTTP requests initiated from scripts. The Same Origin Policy states that a website on one domain cannot make an xhr request to another domain. This prevents a malicious website from making requests to a known website (think Facebook or Google). For example, XMLHttpRequest and the Fetch API follow the same-origin policy.

#### How can you initialize a CSRF attack?
A CSRF attack can be initialized using a GET or POST request and can make use of an Iframe with attributes that make it invisible.

#### What is JWT used for? Where to store it on client side?
JSON Web Token is a standard used to create access tokens for an application.

It works this way: the server generates a token that certifies the user identity, and sends it to the client.

The client will send the token back to the server for every subsequent request, so the server knows the request comes from a particular identity.

The token is stored in an HttpOnly cookie. The other methods are all prone to XSS attacks and as such they should be avoided. An HttpOnly cookie is not accessible from JavaScript, and is automatically sent to the origin server upon every request, so it perfectly suits the use case.

### Threaded programming

#### When do you need to use threads in an application?

Multithreading is a widespread programming and execution model that allows multiple threads to exist within the context of one process. These threads share the process's resources, but are able to execute independently. The threaded programming model provides developers with a useful abstraction of concurrent execution. Multithreaded applications have the following advantages:

Responsiveness
Faster execution
Lower resource consumption
Parallelization: applications looking to use multicore or multi-CPU systems can use multithreading to split data and tasks into parallel subtasks and let the underlying architecture manage how the threads run

#### What is a daemon thread?
Daemon thread is a low priority thread that runs in background to perform tasks such as garbage collection. Traditionally daemon processes in UNIX were those that were constantly running in background, much like services in Windows. A daemon thread in Java is one that doesn't prevent the JVM from exiting. Specifically the JVM will exit when only daemon threads remain.

#### What is the difference between concurrent and parallel execution of code?
Concurrent execution: Running lots of independent things at the same time. A task doesn't have to wait for the other tasks to finish, for it to advance. In single-core setup, suspending and alternating between threads is required (also called pre-emptive multithreading / task switching).
In parallel execution, application breaks down a task into subtasks, and they both advance simultaneously - that is literally at the same time. It requires multi-core CPU.
 An application can be concurrent, but not parallel. This means that it processes more than one task at the same time, but the tasks are not broken down into subtasks, and they are not processed simultaneously. An application can also be parallel but not concurrent. This means that the application only works on one task at a time, and this task is broken down into subtasks which can be processed in parallel.
 


#### What is the most important problem developers are faced when using threads?
One of the most important is deadlock: when two or more threads are blocked forever, waiting for each other to lend access to a resource.
But there are more: 
Starvation – Occurs when a process never gains accesses to resources, never allowing the program to finish.
Race Conditions – Occurs when processes that must occur in a particular order occur out of order due to multiple threading. More specifically, this is discussing a data race, please avoid arguments such as this one.
Livelock – Occurs when two threads are dependent on each other signals and are both threads respond to each others signals. If this is the case, the threads can cause a loop similar to something between a deadlock and starvation.


#### In what kind of situations can deadlocks occur?
First there are locks:
A lock occurs when multiple processes try to access the same resource at the same time. One process loses out and must wait for the other to finish.
Deadlock occurs when: Thread ‘A’ locks Resource 1, that Thread ‘B’ wants to use, and Thread ‘B’ locks Resource 3 that Thread ‘A’ wants to use at the same time, and they get stuck forever.
 


#### What are possible ways to prevent deadlocks from occurring?
Followings are some of the available techniques to prevent deadlocks:
Non overlapping locks
Lock ordering
Lock timeout
Single thread


#### What does critical section or critical region mean in the context of concurrent programming?
In concurrent programming, concurrent accesses to shared resources can lead to unexpected behavior, so parts of the program where the shared resource is accessed need to be protected in ways that avoid the concurrent access. This protected section is the critical section or critical region. It cannot be executed by more than one process at a time. Typically, the critical section accesses a shared resource, such as a data structure, a peripheral device, or a network connection, that would not operate correctly in the context of multiple concurrent accesses.
