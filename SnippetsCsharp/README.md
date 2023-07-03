Getting Started with CLI Visual Code
Available Scripts
Open VS Code terminal and navigate to the directory where you want to create solution folder. Use following commands,

The -o parameter lets you specify the output directory

dotnet new sln -o SnippetsCsharp
Navigate to solution direction

Cd .\SnippetsCsharp\ 
Create new projects under root solution folder

dotnet new console

Add a C# project to a solution:
dotnet sln add todo-app/todo-app.csproj


Remove a C# project from a solution:
dotnet sln remove todo-app/todo-app.csproj