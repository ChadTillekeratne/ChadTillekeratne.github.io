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



