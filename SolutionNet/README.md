# Getting Started with CLI Visual Code 

## Available Scripts

Open VS Code terminal and navigate to the directory where you want to create solution folder. Use following commands, 

The -o parameter lets you specify the output directory

### `dotnet new sln -o SolutionNet`

Navigate to solution direction

### `Cd .\SolutionNet\ `

Create new projects under root solution folder

### `dotnet new webapi -o SolutionNet.WebApi `

Add projects to solution (use tab to navigate path).

### `dotnet sln SolutionNet.sln add .\SolutionNet.WebApi\SolutionNet.WebApi.csproj `

### How to run the ASP.NET Core Web API project using .NET Core CLI?

### `dotnet run`

Once you type dotnet run and press the enter button, you will get the below message.

>info: Microsoft.Hosting.Lifetime[14]
>>Now listening on: https://localhost:7191

>info: Microsoft.Hosting.Lifetime[14]
>>Now listening on: http://localhost:5231

http://localhost:5231 run 404 page, don’t worry. Just type swagger at the end of the URL and press enter and you will get the following webpage. 

> https://localhost:7191/swagger/index.html

## ASP.NET Core Web API Files and Folders

### The launchsettings.json file 

contains some settings that are going to be used by .NET Core Framework when we run the application either from Visual Studio or by using .NET Core CLI. Another point that you need to keep in mind, the launchSettings.json file is only used within the local development machine. So, this file is not required when we publishing our ASP.NET Core Web API application into the production server.

 If you are running your application from the visual studio then IIS Express Profile will be used (for HTTP the port number will be 63044 and for HTTPS the port number will be 44395). On the other hand, if you are running your application using .NET Core CLI, then MyFirstWebAPIProject profile will be used which is nothing but using Kestrel Web Server and for HTTP protocol it uses the port number 5000 and for HTTPS protocol it uses the port number 5001.

### Controllers:

The ASP.NET Core Web API is a controller-based approach. All the controllers of your ASP.NET Core Web API Application should and must reside inside the Controllers folder. 

we have one Get method which is decorated with the HttpGet attribute. And when we call the following URL (https://localhost:7191/WeatherForecast) using any client (Swagger, Postman, and Browser), this is the method going to return the data. We will discuss Controller in detail in our upcoming articles.

### appsettings.json file:

The next file that we are going to discuss is the appsettings.json file. This is the same as web.config or app.config of our traditional .NET Application. The appsettings.json file is the application configuration file in ASP.NET Core Web Application used to store the configuration settings such as database connections strings, any application scope global variables, etc.

### appsettings.Development.json:

If you want to configure some settings based on the environments then you can do such settings in appsettings.{Environment}.json file. You can create n number of environments like development, staging, production, etc. 

### Program.cs class file:
The Startup class is like the Global.asax file of our traditional .NET application. As the name suggests, it is executed when the application starts

## How to Create a Docker Image of a .NET Web API

Docker traitera chaque ligne du Dockerfile. Le . dans la docker build commande définit le contexte de génération de l’image.

> docker build -t solutionnet.webapi -f Dockerfile .

Running the Docker Image

> docker run -ti --rm -p 8080:80 solutionnet.webapi

Note: On arrive pas a lancer le http://localhost:8080/swagger/index.html mais directement http://localhost:8080/WeatherForecast

Supprimer une image

> docker rmi solutionnet.webapi
> docker rmi solutionnet.webapi --force