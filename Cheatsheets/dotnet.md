# dotnet Command Line
## Solution and Project Management
- `dotnet new sln`
  - Create a new Solution
- `dotnet sln add .\Foo\Foo.csproj`
  - Add a Project to a Solution
- `dotnet new <project-type> --name <project-name>`
  - Create a new project
  - `dotnet new --list`
    - List all installed project types
    - Frequently used:
      - `webapi` - ASP.NET Core Web API
      - `web` - ASP.NET Core Empty
- `dotnet restore`
- `dotnet build`

## Package Management
- `dotnet add package Newtonsoft.Json`
  - Add a Nuget Reference
  - `dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0 -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json`
    - Add Nuget reference with all options
- `dotnet add app/app.csproj reference lib/lib.csproj`
  - Add a reference to another project

## Running a Project
- `dotnet run -p Foo\Foo.csproj`

## Aspire
- Check if Aspire templates are installed
  - `dotnet new list aspire`
### [Instrumenting existing solution](https://learn.microsoft.com/en-us/dotnet/aspire/get-started/add-aspire-existing-app)
#### Basic Setup
1. AppHost
    1. Create a new AppHost project
        - `dotnet new aspire-apphost -o eShopLite.AppHost`
    1. Add AppHost project to solution
        - `dotnet add ./eShopLite.AppHost/eShopLite.AppHost.csproj reference ./Store/Store.csproj
1. ServiceDefaults
    1. Create a new ServiceDefaults project
        - `dotnet new aspire-servicedefaults -o eShopLite.ServiceDefaults`
    1. Add ServiceDefaults project to solution
        - `dotnet sln ./eShopLite.sln add ./eShopLite.ServiceDefaults/eShopLite.ServiceDefaults.csproj`
    1. Add ServiceDefaults project reference to AppHost
        - `dotnet add ./eShopLite.AppHost/eShopLite.AppHost.csproj reference ./Products/Products.csproj`
    1. Add ServiceDefaults project reference to {your project}
        - `dotnet add ./eShopLite.AppHost/eShopLite.AppHost.csproj reference ./Products/Products.csproj`
1. Add ServiceDefaults to your WebApplication Builder
    1. Update your _Program.cs_ files, adding the following line immediately after their `var builder = WebApplication.CreateBuilder(args);` line:
        - `builder.AddServiceDefaults();`
1. Update AppHost project
    1. Open the Program.cs file of the app host project, and replace its contents with the following C# code:
        - <pre>var builder = DistributedApplication.CreateBuilder(args);<br />builder.AddProject<Projects.Store>("store");<br />builder.Build().Run();</pre>
#### Add Service Discovery
// TODO: