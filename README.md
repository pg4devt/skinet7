# Build an e-commerce app with .NET Core and Angular

## VSCode Extensions
	- C#, C# Extensions, NuGet Gallery
	
## NuGet Packages
	- Microsoft.EntityFrameworkCore.Sqlite
	- Microsoft.EntityFrameworkCore.Design
	
## Command to verify .NET installation (Currently 7.0.101)
```
dotnet --info
```
	
## .NET commands
```
dotnet 	--help # command information
dotnet new list # list of templates to create
```

## Create a solution/project
```
dotnet new sln #create solution
dotnet new webapi -n API # create a Web API
dotnet new sln # create new solution
dotnet sln add API # add API project to the solution
dotnet sln list # list projects in a solution

dotnet run # run the solution
```

## Run the solution and see ongoing changes
```
dotnet watch 
dotnet watch --no-hot-reload
```

## Create https dev certificates
```
dotnet dev-certs https --clean
dotnet dev-certs https --trust
```

## Install EF Core

- Go to https://nuget.org/packages/dotnet-ef to check for latest version
	```
	dotnet tool install --global dotnet-ef --version 7.0.3
	```
- Check locally if already installed and what version
	```
	dotnet tool list # check if already installed
	```
- Install
	```
	dotnet tool install --global dotnet-ef --version 7.0.3
	```
- Update if already installed
	```
	dotnet tool update --global dotnet-ef --version 7.0.3
	```
	
## EF Core for Code-First Migration
- Go to API folder
	```
	dotnet ef
	dotnet ef migrations
	dotnet ef migrations add InitialCreate -o Data/Migrations
	dotnet ef database update
	```	
	
## Create New Infrastructure project
```
dotnet new classlib -n Core
dotnet new classlib -n Infrastructure
dotnet sln add Core
dotnet sln add Infrastructure
```	

## Add projects as reference dependencies

API --> Infrastructure --> Core

```
cd API
dotnet add reference ..\Infrastructure
cd ..\Infrastructure
dotnet add reference ..\Core
cd ..
dotnet restore
```

## Save the project using Git
```
git status
git init
git branch -m main

```
