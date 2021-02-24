# Enterprise module (C# branch)

### ASP.NET Core, WCF

#### What Is the difference between .NET Core and .NET Standard? How do them relate to “classic” .NET?
-NET Core is a free,  cross-platform, open source framework for Windows,
 Linux and macOS operating System. It is a cross-platform successor to .NET Framework.
It supports console, ASP.NET Core, cloud and Universal Windows Platform applications. 

-.NET Standard: This is the set of fundamental APIs (commonly referred to as base class library or BCL) 
that all .NET implementations must implement. By targeting .NET Standard,
 you can build libraries that you can share across all your .NET apps, no matter on which .NET implementation
 or OS they run. There are various implementations of .NET. Each implementations allows .Net code to execuite 
 different places(linux, macOs, Windows etc.).NET Standard is a formal specification of the API's 
 that are common across all these .NET implementations. Net Standard is not a framerowk or platform of its own. 
 It does not have implementations or a runtime, it just defines a specification what different 
 .NET platforms has to implement to remain .NET Standard compilant.
 
#### What is ASP.NET MVC?
-ASP.NET MVC is a free web framework for building web applciations on e.g. .NET core using HTML, CSS, And Javascript. 
-ASP.NET MVC is based on Model-VIew-Controller(MVC) architecture. Developers can build dynamic web applications 
using ASP.NET MVC framework that enables a clean separation of concerns, fast development.

#### Can you explain Model, Controller and View in MVC?
-Model: it represents the shape of the data. A class in c# is used to describe a model. Model objects store data retrieved from the database.
-View in MVC is a user interface. View display model data to the user and also enables them to modify them. 
View in ASP.NET core  is Html, CSS and some special syntax(Razor syntax) that makes it easy to communicate with the model and controller.
-The controller handles the user request. Typically, the user uses the view and raises an HTTP request, which will be handled by the controller. 
The controller processes the request and returns the appropriate view as response

#### Explain the page lifecycle of MVC.
-1.Routing
    -All the requests are routed to a special class called Controller. The controller is responsible for generating the response and sending the content 
	back to the browser
-2.Url Routing Module intercepts the request
    -Whenever you make a request against an ASP.NET MVC application, the request is intecepted by the UrlRoutingModule HTTP Module.
	When the UrlRoutingModule interceps a reuqest , it wraps up the current HTTPContext in an HttpCOntextWrapper object. 
	The HttpCOntextWrapper object derives from HttpContextBase class.
-3. MVC handler executes
    - MVCHandler also inherit from the IHTTPAsyncHandler when ,MVC Handler executes it will call the BeginProcessRequest method of the httpAsyncHandler
	asynchronously.
    -When the process request method is called a new controller gets created. The controller is created from a ControllerFactory. 
	There is a ControllerBuilder Class which will set the ControleerFactory.
    -The RequetContext and the name of the Controller will be passed to the method CreateController Method to get the particular Controller.
-4.Controller Executes
    controller is called and its action called requested by user
    -The Execute() method starts by creating the TempData object. TempData is a dictioanry derived from TempDataDictionary class and stroed in
	short lives session and it is a string key and object value
    -The Execute() method gets the Action from the RouteData based on the URL. The controller class then call the ControllerActionInvoker that builds
	a list of parameters from the request. 
    -These paramerets extracted from the request parameters, will act as method parameters. The parameters will be passed to whatever controller methods 
	gets executed
    -Finally it will call the InvokeAction method to execute the Action
-5.Render View Method Called
    -At last when we call return View() Render View method is called and puts response on the page to be displayed.
    -THe controller typycally either executer the RedirectToAction Method or the RenderView Method.
	When you call a controller's RenderView() method, the call is delegated to the current ViewEngine's RenderView() method. 
    -THe WebFormViewEngine.RenderView() method uses a class named the ViewLocator class to find the view.
	Next, it uses a BuildManager to create an instance of a ViewPage class from its path.

    Next, if the page has a master page, the location of the master page is set if the page has ViewData, the ViewData is set.
	Finally, the RenderVIew() method called on the ViewPage   


#### What is Razor View Engine?
Razor is a templating engine and ASP.NET MVC has implemented a view engine which allows us to use Razor inside of an MVC application to produce HTML.

#### What you mean by Routing in MVC?
In MVC, routing is a process of mapping the browser request to the controller action and return response back. 
Each MVC application has default routing for the default HomeController.
 We can set custom routing for newly created controller.

#### What is Layout in MVC?
-An application may contain a specific UI parts that remains the same throughout the application, such as header, left navigation, right bar,
 or footer section. ASP.NET MVC introduced a Layout view which cotntains these common UI portions so that we dont have to write the same code in every page.
 E.G. an application UI may contain a header, left menu bar and footer section that remains the same on every page. Only the center changes dynamically.
 
#### What ConfigureServices() method does in Startup.cs?
The Configure method is used to specify how the app responds to HTTP requests. The request pipeline is configured by adding middleware 
components to an IApplicationBuilder instance. 
IApplicationBuilder is available to the Configure method, but it isn't registered in the service container.

#### What Configure() method does in Startup.cs?
The Configure method is used to specify how the app responds to HTTP requests.
 The request pipeline is configured by adding middleware components to an IApplicationBuilder instance.
 IApplicationBuilder is available to the Configure method, but it isn't registered in the service container

#### What is wwwroot folder in ASP.NET Core?
-all the static files go in this folder. These are assets that the app will serve directly to clients, 
including HTML files, CSS files, image files and js files.
-Code files should be placed outside of wwwroot, including c# files and razor views.
 Having wwwroot folder keeps a clean separation between code files and static files.

#### What’s the usage of [InternalsVisibleTo] attribute? What are pros and cons of it?
Pros
-Allows your test libraries to access internal classes and methods for additional testing and coverage
-Keeps your public API limited to what you want to publish
-Provides greater flexibility for internal refactoring and backwards compatibility
-Reduces the surface area of your public API</ul>
Cons
-Easily abused, so things usually marked “private” are now marked “internal”
-Potential loss of encapsulation
-Decision about what should be public could be wrong
-Essentially two levels of “public” visibility that have to be managed

#### Explain what is WCF?

#### Mention what is the endpoint in WCF and what are the three major points in WCF?

#### Object Relational Mapping, Entity Framework


#### What is an ORM? What are benefits, when to use?
ORM stands for Object Relational Mapper,it helps you take advantage of the oop principles while you are managing relational database.
 You are able to define what the structure in your database should look like, using code. Additionaly you can use code for your queries as well.
 An ORM library is a completely ordinary library written in your language of choice that encapsulates the code needed to manipulate data,
 so you aint use SQL anymore. 

Benefits:
    -DRY: you wirte your data model in only one place, and its easier to update , maintain and reuse the code
    -it forces u to write mvc code, which makes it cleaner
    -a lot of stuff is done automatically like database handling
    -it lets you use OOP goodness like data inheritance without difficulties 
	
#### What is Entity Framework? What are the advantages, limitations?
-Entity Framework core is a modern object-database mapper for .NET . It supports LINQ queries, change tracking, updates, and schema migrations.
 EF Core works with many databases, including SQL Database, Postresql, MySQL etc..
-EF core can serve as an object-relational mapper (O/RM) which:
    -enables .NET developers to work with databses using .NET objects.
    -Eliminates the need for most of the data-access code that typically needs to be written 

-limitations: 
    -if there is any schema change in databse ef core will not work. You have to update schema in solution as well.
	
#### What is lazy loading?
For example, If an entire photo gallery is downloaded but the user leaves after only viewing the first image, then the result is wasted memory and bandwidth.
 ... With lazy loading, pages are created with placeholder content which is only replaced with actual content when the user needs it.
 
#### What is the difference between code first and DB first approach?
- in Code first approach we will first create entity classes with properties defined in it. 
Entity framework will create the database and tables based on the entity classes defined. So database is generated from the code.
 When the .net code runs, database will get created.

-The database first appriach created model codes (classes,properties, dbContext etc) from the database in the project and those classes become the link
 between the database and the controller.
it also creates the entity framework from an existing database. We use all other functionalities,
 such as the model/database sync and the code generation

#### What is a migration script?
Migration scripts are customizable SQL scripts created by user through ApexSQL Source Control containing any specific configuration changes,
 or overrides that need to be executed before or after applying an object change from source control, or they can be executed instead of a change.

#### What is a navigation property?
Navigation properties are Entity Frameworks way of representing Foreign Key relationships inside the database.
Navigation properties allow you to define relationships between entities (rows in your database) in a way that makes sense in an object oriented language.

#### Name 3 different attributes used in EF Core, what can they do for you?
-from Data Annotations attributes in ef core can be applied on an entity class or properties to override default conventions.
    [Required] = can be applied to a property to specify that the corresponding column is a notnull column in the database
    [Key] can be applied to a property to specify a key property in an entity and make the corresponding column a PrmiaryKey Column in the database
    [MinLength] can be applied to a property to specify the minimum string length allowd in the corresponding column in the database. 

