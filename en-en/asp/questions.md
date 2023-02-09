### What is the ASP.NET Core?
[ASP.NET Core](https://www.dotnettricks.com/training/masters-program/aspnet-core) is not an upgraded version of ASP.NET. ASP.NET Core is completely rewriting that work with the .net Core framework. It is much faster, configurable, modular, scalable, extensible, and has cross-platform support. It can work with both .NET Core and .net framework via the .NET standard framework. It is best suitable for developing cloud-based such as web applications, mobile applications, and IoT applications.
ASP.NET Core was primarily designed to make the most important part of the ASP.NET components under the concept learn and the compose framework where the previous ASP.NET components were released under a variety of different licenses periodically, The ASP.NET Core framework is a completely open-sourced framework. Apart from the other parts of the framework of the .NET framework libraries, the ASP.NET Core is primarily designed from scratch to be the platform-agnostic that performs seamlessly. It will allow the ASP.NET Core apps to be deployed on the various platforms or the o/s such as the macOS or Linux-based servers or certain devices.

### What are the features provided by ASP.NET Core?

Following are the core features that are provided by the ASP.NET Core
- Built-in supports for [Dependency Injection](https://www.dotnettricks.com/learn/dependencyinjection)
- Built-in supports for the logging framework and it can be extensible
- Introduced a new, fast and cross-platform web server - Kestrel. So, a web application can run without IIS, Apache, and Nginx.
- Multiple hosting ways are supported
- It supports modularity, so the developer needs to include the module required by the application. However, the [.NET Core framework is also providing the meta package that includes the libraries](https://www.dotnettricks.com/learn/netcore)
- Command-line supports to creating, building, and running of the application
- There is no web.config file. We can store the custom configuration into an appsettings.json file
- There is no Global.asax file. We can now register and use the services in the startup class
- It has good support for asynchronous programming
- Support WebSocket and SignalR
- Provide protection against CSRF (Cross-Site Request Forgery)

### What are the advantages of ASP.NET Core over ASP.NET?
There are the following advantages of ASP.NET Core over ASP.NET :

- It is cross-platform, so it can be run on Windows, Linux, and Mac.
- There is no dependency on framework installation because all the required dependencies are shipped with our application
- ASP.NET Core can handle more requests than the ASP.NET
- Multiple deployment options available withASP.NET Core

### What is the startup class in ASP.NET core?

The startup class is the entry point of the ASP.NET Core application. Every .NET Core application must have this class. This class contains the application configuration related items. It is not necessary that the class name must be "Startup", it can be anything, we can configure the startup class in the Program class.
    
```csharp
public class Program {
	public static void Main(string[] args) {
		CreateWebHostBuilder(args).Build().Run();
	}
	public static IWebHostBuilder CreateWebHostBuilder(string[] args) => WebHost.CreateDefaultBuilder(args).UseStartup<TestClass>();
}
```

### Describe the Dependency Injection.

Dependency Injection is a Design Pattern that's used as a technique to achieve the Inversion of Control (IoC) between the classes and their dependencies.
ASP.NET Core comes with a built-in Dependency Injection framework that makes configured services available throughout the application. You can configure the services inside the ConfigureServices method as below.
    
```csharp
services.AddScoped();
```

A Service can be resolved using constructor injection and DI framework is responsible for the instance of this service at run time. For more visit ASP.NET Core Dependency Injection

### How to read values from Appsettings.json file?

You can read values from appsettings.json using below code.

```csharp
class Test{
	// requires using Microsoft.Extensions.Configuration;
 	private readonly IConfiguration Configuration;
    public TestModel(IConfiguration configuration) {
        Configuration = configuration;
    }
	/*public void ReadValues(){
		var val = Configuration["key"]; // reading direct key values
		var name = Configuration["Employee:Name"]; // read complex values
	}*/
}
```
Default configuration provider first load the values from appsettings.json and then from appsettings.Environment.json file.
Environment specific values override the values from appsettings.json file. In development environment appsettings.Development.json file values override the appsettings.json file values, same apply to production environment.
You can also read the appsettings.json values using options pattern described Read values from appsettings.json file. 

### How ASP.NET Core serve static files?

In ASP.NET Core, Static files such as CSS, images, JavaScript files, HTML are the served directly to the clients. ASP.NET Core template provides a root folder called wwwroot which contains all these static files. UseStaticFiles() method inside Startup.Configure enables the static files to be served to client.
You can serve files outside of this webroot folder by configuring Static File Middleware as following.

```csharp
app.UseStaticFiles(new StaticFileOptions
    {
        FileProvider = new PhysicalFileProvider(
            Path.Combine(env.ContentRootPath, "MyStaticFiles")), // MyStaticFiles is new folder
        RequestPath = "/StaticFiles"  // this is requested path by client
    });
// now you can use your file as below
<img src="/StaticFiles/images/profile.jpg" class="img" alt="A red rose" />
 // profile.jpg is image inside MyStaticFiles/images folder
```


### Explain Session and State management in ASP.NET Core

As we know HTTP is a stateless protocol. HTTP requests are independent and does not retain user values. 
There are different ways to maintain user state between multiple HTTP requests.

- Cookies
- Session State
- TempData
- Query strings
- Hidden fields
- HttpContext.Items
- Cache
