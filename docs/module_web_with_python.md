# Web with Python questions

## Software design

### Clean code

#### Point out 5 suggestions, how to format an SQL query!
       	1: Indent Your Code
       	2: Use the WITH Clause instead HAVING
	3: Explain Yourself with Comments
	4: Break Queries into Steps
      	5: Stick with One Naming Convention
#### What layers can you name in a simple web application?
	View
	Application service
	Database
	Domain

### Error handling
#### What error can occur, when an array does not have an element on the requested index?
	Index error.
#### What is the “finally” block, and how would you use it?
	The finally block is as the name , some code that you want to 		execute regardless of what happens.
#### Why should we catch special exception types?
Exception handling ensures that the flow of the program doesn't break when an exception occurs. For example, if a program has bunch of statements and an exception occurs mid way after executing certain statements then the statements after the exception will not execute and the program will terminate abruptly.

### Security
#### What is SQL injection? How to protect an application against it?
SQL Injection (SQLi) is a type of an injection attack that makes it possible to execute malicious SQL statements. Prevent SQL Injection attacks with input validation and parametrized queries with prepared statements: do not use the input directly. Also sanitizing all input e.g.: remove potential malicious code elements such as single quotes and other special characters.
#### What is XSS? How to protect an application against it?
Cross-site script injection. Most of all:
      Filter input on arrival. At the point where user input is received, filter as strictly as possible based on what is expected or valid input.
    • Encode data on output. At the point where user-controllable data is output in HTTP responses, encode the output to prevent it from being interpreted as active content. Depending on the output context, this might require applying combinations of HTML, URL, JavaScript, and CSS encoding.
    • Use appropriate response headers. To prevent XSS in HTTP responses that aren't intended to contain any HTML or JavaScript, you can use the Content-Type and X-Content-Type-Options headers to ensure that browsers interpret the responses in the way you intend.
    • Content Security Policy. As a last line of defense, you can use Content Security Policy (CSP) to reduce the severity of any XSS vulnerabilities that still occur.
#### How to properly store passwords?
In at least hashed form. Or hashed and salted.
#### What is HTTPS?
Hypertext Transfer Protocol Secure (HTTPS) is an extension of the Hypertext Transfer Protocol (HTTP). It is used for secure communication over a computer network, and is widely used on the Internet It protects against man-in-the-middle attacks.
#### What is encryption and decryption?
Encrypting hide something. Decryption is revealing the secret content.
#### What is hashing?
A hash function is where a computer takes an input of any length and content (e.g. letters, numbers, and symbols) and uses a mathematical formula to chop it, mix it up, and produce an output of a specific length.
#### What is the difference between encryption and hashing? When would you use which?
Encrypting is done by a key, reversible; with the same key it can be decrypted. Length hang from the source length. Used in cases when the content is also important and needed, possible to transfer it in a secure way.
Hashing is irreversible, one way transformation. It’s ideal for passwords.
#### What encryption methods do you know?
Symmetric and asymmetric.
AES Advanced Encryption Standard is a symmetric encryption algorithm that encrypts fixed blocks of data (of 128 bits) at a time. The keys used to decipher the text can be 128-, 192-, or 256-bit long.
RSA is considered an asymmetric algorithm due to its use of a pair of keys.
You’ve got your public key,which is what we use to encrypt our message,
 and a private key to decrypt it
#### What hashing methods do you know?
MD5 , SHA-2
#### How/where would you store sensitive data (like db password, API key, ...) of your application?
Fist I would encrypt ,and after on a secured server.

## Computer science

### Algorithms

#### What is the difference between Stack and Queue data structure?
Stack data structure have just one pointer, adding operation (push) or removing operation (pop) take place from the top of the list, 
for example: LIFO (Last In First Out)
Queue have two pointers. One for each side of the list. The front side can take a new operation (enqueue),
to remove (dequeue) an operation the pointer should use the the rear side. Principle: FIFO (First In First Out)
#### What is BubbleSort? Describe the main logic of this sorting algorithm.
BubbleSort is a sorting method. Starting from the first element, comparing it with the next. If the next element higher then the previous move to the next. Else swap them. And so on till the last index.
#### Explain the process of finding the maximum and minimum value in a list of numbers!
Iterate trough the list of numbers. Set the first as highest/lowest. Then comparing each next element with the firsts and replace it with the first accordingly.
#### Explain the process of calculating the average value in an array of numbers!
Adding each element value together and dividing it with the the total element count.
#### What is Big O complexity? Explain time and space complexity!
Big O Notation is to describe the complexity of an algorithm. How long an algorithm takes to run. It is to compare the efficiency of different approaches to a problem. Big O express the run time as it grows relative to the input, as the input gets larger.
#### Explain the process of calculating the average value in a list of numbers!
Similar to the average counting of an array. We have to move along each nodes and adding together the values, than dividing them with the total nodes count.

### Procedural
#### How the CASE condition works in SQL?
CASE is a program-flow controlling structure, it checks the cases ,when the condition is true it goes into and execute it and never checks the cases after, if none of the cases are true , it executes what is in the else clause.
#### How the switch-case condition works in JavaScript?
Switch CASE is a program-flow controlling structure, it checks the cases ,when the condition is true it goes into and execute it and never checks the cases after, if none of the cases are true , it executes what is in the else clause.
#### How to achieve a switch-case-like structure in Python?
With if – elif statements.
#### Explain variable scoping in Python!
According to the LEGB rule: local, enclosing, global, built-in, the look-up for the namespaces are started from the most inner scope: which is the local. E.g.: in the body of a function.
#### What’s the difference between const and var in JavaScript?
var is a variable, the value can be modified after all. const is a constant, the value is immutable, can't be reassigned after declaration.
#### How the list comprehension looks like in Python?
List = [a+1 for a in range(5)]
#### How the “ternary expression” looks like in Python?
a = 1 if b == 2 else 2
#### How the ternary expression looks like in JavaScript?
condition ? exprIfTrue : exprIfFalse
#### How to import a function from another module in Python?
from module import module_name 
calling: module_name.function_name
#### How to import a function from another module in JavaScript?
import name from "module-name";

### Functional
#### What is recursion?
Recursive in functions mean: that the function call itself again .
#### Write a recursive function which calculates the Fibonacci numbers!
function fibo(limit, firstNumber, secondNumber) {
        if (limit === 0) {
            break;
        } else {
		limit -= 1;
		let nextFiboNum = firstNumber + secondNumber;
	    	console.log(nextFiboNum);
	   	firstNumber = secondNumber;
	    	secondNumber = nextFiboNum;
		fibo(limit, firstNumber, secondNumber) 
	    }
    }
#### How to store a function in a variable in Python?
def my_function():
    print("this is the function")

function_variable = my_function

print(function_variable)
#### List the ways of defining a callable logical unit in JavaScript!
      let obj = {
              myMethod(arg1, arg2) {
                  ...
              }
          };
#### What is an event listener? How to attach one?
Event listeners give functionality to the application. Trough them can be triggered a function by the user. Locating the target, attaching a listener function and in the callback handling the event with an event handler function.
    • Locating:
        ◦ object: window or document
        ◦ methods: getElementById ,getElementsBy[TagName, .ClassName],
querySelector, querySelectorAll
    • Attaching:
        ◦ method: addEventListener
        ◦ event listener: a string named event listener type
        ◦ event handler: a callable function
	example:
document.querySelector(".Btn").addEventListener("click", displayDate);
#### How to trigger an event in JavaScript?
Event listeners have a target, which they listen for. It can be triggered by:
    • mouse actions
    • keyboard actions
#### What is a callback function? Tell some examples of its usage.
A function if passed as argument to a function, is a callback function. The invoking function become a higher-order function, and will control the execution of called back function
E.g.: a script can modify the content after a fetch script executed and returned the values.
#### What is a Python decorator? How does it work? Tell some examples of its usage.
Decorator is function, executed before the invoked function and the return value bounded with the decorated function return value.
#### What is the difference between synchronous and asynchronous execution?
sync: being executed after the page has loaded and the script also be loaded. async: load of the page and the script started parallel, script executed right after calling.

## Programming languages

### SQL

#### How can you connect your application to a database server? What are the possible ways?
I need a connection string and a connection object from the database provider to set a session with the database server. For phyton we can use the psycopg2 module api's to connect an application with psql database.
#### When do you use the DISTINCT keyword in SQL?
DISTINCT is used in the SELECT statement to remove duplicate rows from a result .
#### What are aggregate functions in SQL? Give 3 examples.
An aggregate function performs a calculation on a set of values, and returns a single value.
    • MAX()
    • SUM()
    • AVG()
    • COUNT()
    • MIN()
#### What kind of JOIN types do you know in SQL? Could you give examples?
    • (INNER) JOIN:
        ◦ return the corresponding values if each table have the connection point.
    • LEFT (OUTER) JOIN / RIGHT (OUTER) JOIN:
        ◦ return the corresponding values if one of tables (corresponding) have the connection point.
#### What are the constraints in sql?
Constraints are defining what value type can accepted by the column.
Like : NOT NULL, UNIQUE, PRIMARY KEY.
#### What is a cursor in SQL? Why would you use one?
A cursor is a temporary work area created in the system memory when a SQL statement is executed. A cursor contains information on a select statement and the rows of data accessed by it. This temporary work area is used to store the data retrieved from the database, and manipulate this data. 
#### What are database indexes? When to use?
To faster reach of a database table values, we can create an index. The index containing a field value and point to the row which hold the column. Index is sorted and acting like a placeholder to a faster search: no need the look up all the columns in the rows for the data.
#### What are database transactions? When to use?
A transaction is a single unit of logic or work.  Database transactions should be done for all or nothing. Using transactions ensures that the database engine can roll back the transaction.
#### What kind of database relations do you know? How to define them?
Table connection defined by keys, which are representing the connection between the tables.
    1. one-to-one
        ◦ if one table primary key referenced as the other table foreign key.
    2. one-to-many
        ◦ if one table primary key referenced as more than one other table foreign key.
    3. many-to-many
        ◦ if more than one table key pointing to more than one table keys. For that is needed an intersection table who is controlling the connection between the relations.
#### You have a table with an “address” field which contains data like “3525, Miskolc, Régiposta 9.” (postcode, city, street name and address). How would you query all records related to Miskolc?
SELECT * FROM table WHERE city = 'Miskolc';
#### How would you keep track of what kind of data has changed after an UPDATE or DELETE operation in a table?
I would create a log table and create a trigger on that will insert a row into person_log table whenever the table/s row/s get updated/deletes/added

### HTML & CSS

#### What’s the difference between XML, XHTML and HTML?
XML --- eXtensible Markup Language XHTML - eXtesnsible Hypertext Markup Language HTML -- Hypertext Markup Language SGML -- Standard Generalized Markup Language
HTML is SGML based, developed to parse data written in a serialized language (tags are predefined) and display it from the point of user or UI. Media or object can also be a part of the document.
XML is mostly for parsing data and transfer it between sites or to communicate different applications with each other. Tags are not predefined and strict in closing tags but not in case.
XHTML is XML based, composing the two other attributes. Parsed as an HTML document but allowing XML specifications.
#### How to include a JavaScript file in a webpage?
<script type="javascript" src="javascript.js"></script>
#### How to include a CSS file in a webpage?
<link rel="stylesheet" type="css" href="stylesheet.css"/>
#### How to select an element using its id in CSS?
With selectors. Selectors can be tag_name {}, .class_name {} and #id_name {}.
#### How to select elements using their class in CSS?
.class_name {}
#### How to select elements which have the ‘alpha’ and ‘beta’ classes in CSS?
With chaining the class selectors: .alpha.beta {}
#### How to select all list items in all ordered lists on the page in CSS?
< ol >: li {}
#### How to select elements using their attributes in CSS?
 selector[attribute_name] {}
#### What are UX and UI?
User Experience and User Interface.
#### Please list some points that an application should fulfill to have good UX.
    • Fulfill the users' needs
    • Have a clear stucture
    • Consistency
    • Understandable
    • Usability
#### What is XML, XSLT, DTD?
    • XML is a markup language, to create XML document in the proper way
    • XSLT - Extensible Stylesheet Language Transformations is the XML stylesheet formatting language
    • DTD -- Document Type Definition is for validating the XML document
#### What is the difference between HTML and XML?
XML is abbreviation for eXtensible Markup Language whereas HTML stands for Hypertext Markup Language.
    • XML mainly focuses on transfer of data while HTML is focused on presentation of the data.
    • XML is content driven‭‬‬‬‬‬‬‬‬‬‬‬‬‬‬‬ whereas HTML is format driven‭‬‬‬‬‬‬‬.
    • XML is Case sensitive while HTML is Case insensitive.
    • XML provides namespaces support while HTML doesn't provide namespaces support.
    • XML is strict for closing tag while HTML is not strict.
    • XML tags are extensible whereas HTML has limited tags.
    • XML tags are not predefined whereas HTML has predefined tags.

### Javascript

#### What is javascript?
JS is a scripting language designed to control web page content.
#### When to use AJAX? Bring examples of its usage.
AJAX programming is that you can exchange data in the background without actually disturbing the user experience.
- Comments: (when a commenter hits the comment button, it's nice to see the comment appear immediately on the page.)
#### What is DOM and how to manipulate it from Javascript?
DOM - Document Object Model DOM is representative displaying for the according html document, and those objects can modified.
    • Creating, removing or replacing an element
    • Modifying an element's text and/or HTML content
    • Get an element content and work with it
      let element = document.querySelector('selector');
      elemen.syle.backgroundColor = ‘black’;
#### What are events and how/why to use them in Javascript?
JavaScript's interaction with HTML is handled through events that occur when the user or the browser manipulates a page. With event listeners to catch them and with event handlers to react for them. Using for make a site interactive, informative or any other UX, UI purpose.
#### What is event bubbling/capturing? How would you use it?
Event bubbling and capturing are two ways of event propagation in the HTML DOM API, when an event occurs in an element inside another element, and both elements have registered a handle for that event.
Capturing  Start with outer elements and continue with inner elements.
Bubbling is opposite, the inner elements first and after outers.
#### What is JSON and how do we use it?
JSON format is used for serializing and transmitting structured data over a network connection. Primarily to transmit data between a server and web application.

## Software engineering

### Version control

#### What type of branching strategy would you use?
Opening a new branch for every development station(tasks). When it's done then merge back to master so avoid conflicts or losing a good state the code.
#### What would you do if you find a bug on the production code (master branch)?
I would open a new branch (like HOTFIX): fix the bug, after testing merging it back to master.
#### How can you move changes from one branch to another in GIT?
Make and checkout to a new branch will copy the actual state of the original branch .
#### How does a VCS help with code reviews?
With the pull request, as inviting the other members to review the developed branch.
#### What is your favorite git command? Why?
git clone  It’s a new exciting beginning.
#### What does remote/local mean in Git?
Remote exists on the git server. Local files are the copy of them on my disk. 

### DevOps

#### Why is it good to use a package manager software?
Easy, safe and clean install packages, modules, extensions.
#### Why is it good to use a virtual environment for a project?
Different dependencies can safely separated for every project. For example one project is hanging around from a while, there is already an update for one of the module which is used by. With venv the module can be available in both versions without any problem.

### Networks

#### What kind of HTTP status codes do you know?
    • 100–199 - Informational responses
    • 200–299 - Successful responses
    • 300–399 - Redirects
    • 400–499 - Client errors
    • 500–599 - Server errors
#### What is a API?
Application Programming Interface.
    • An API is code, that allows two software programs to communicate with each other. One program can call another programs API to get access to data or functionality of the other program.
#### What is REST API?
A RESTful API is an application program interface (API) that uses HTTP requests to GET, PUT, POST and DELETE data.
#### What is JSON? When to use?
JavaScript Object Notation. JSON format is used for serializing and transmitting structured data over network connection. It is primarily used to transmit data between a server and web applications.
#### What is TCP/IP? What layers does it define, what are they responsible for?
TCP/IP - Transmission Control Protocol/Internet Protocol
is the language a computer uses to access the internet. It consists of a suite of protocols designed to establish a network of networks to provide a host with access to the internet. (its like a set of rules to allow communicate each other)
TCP defines how applications can create channels of communication across a network. It also manages how a message is assembled into smaller packets before they are then transmitted over the internet and reassembled in the right order at the destination address.
IP defines how to address and route each packet to make sure it reaches the right destination. Each gateway computer on the network checks this IP address to determine where to forward the message.
#### What’s the difference between TCP and UDP?
Both TCP and UDP are protocols used for sending bits of data—known as packets—over the Internet. Both protocols build on top of the IP protocol. In other words, whether you’re sending a packet via TCP or UDP, that packet is sent to an IP address. These packets are treated similarly, as they’re forwarded from your computer to intermediary routers and on to the destination.
TCP Transmission Control Protocol (TCP) is a connection-oriented protocol that computers use to communicate over the internet. It is one of the main protocols in TCP/IP networks. TCP provides error-checking and guarantees delivery of data and that packets will be delivered in the order they were sent.
UDP  User Datagram Protocol (UDP) is a connectionless protocol that works just like TCP but assumes that error-checking and recovery services are not required. Instead, UDP continuously sends datagrams to the recipient whether they receive them or not.

TCP
Reliable
Connection-oriented
Segment retransmission and flow control through windowing
Segment sequencing
Acknowledge sequencing

UDP
Unreliable
Connectionless
No windowing or retransmission
No sequencing
No acknowledgment

#### How does an HTTP Request look like? What are the most relevant HTTP header fields?
Request headers contain more information about the resource to be fetched, or about the client requesting the resource. Method name, target address, user agent, encodings and connection types, cookie information.
#### How does an HTTP Response look like? What are the most relevant HTTP header fields?
Response headers hold additional information about the response. status of the response, location where it came from, its content length or MIME type.
#### What is DNS? How does it work?
DNS - Domain Name Servers They maintain a directory of domain names and translate them to Internet Protocol (IP) addresses.
#### What is a web server?
A Web server is a program that uses HTTP (Hypertext Transfer Protocol) to serve the files that form Web pages to users, in response to their requests, which are forwarded by their computers' HTTP clients. Dedicated computers and appliances may be referred to as Web servers as well.
#### Explain the client-server architecture.
Each computer or process on the network is either a client or a server.
Clients are the users whom consuming the
Servers provided, hosted, managed network.
#### What would you use a session for?
For conserving a temporary state about the connection and about the user. They expire after the browser closed.
#### What would you use a cookie for?
For saving locally data about the user or from the connection types or settings.

## Software Development Methodologies

#### What kind of software development methodologies do you know? What are the main features of these?
#### What are the SCRUM roles?
#### What are the SCRUM ceremonies?
#### What are the SCRUM artifacts?
#### What is the main goal of a retrospective meeting?
#### Explain, when would you recommend to use the waterfall methodology?
