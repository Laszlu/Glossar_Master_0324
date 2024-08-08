# Dependency Injection

## Definition

#### General

Dependency Injection (referred to as "DI") is a technique in object-oriented programming.
The goal of DI is to manage the dependencies within a class in a centralized location, thereby making a class independent of its dependencies.
To achieve this, the use of an object is separated from the creation.
By using DI, two of the five SOLID principles are being followed: Dependency Inversion and Single Responsibility.
Hard-coded dependencies should be avoided for various reasons, one being that if the dependency changes, the dependent class needs to be modified as well.
Additionally, these dependencies scatter the configuration of the application throughout the code, making it harder to maintain.

#### Language-specific

In C#, or more specifically .NET, DI is implemented via the application's service container.
.NET provides a built-in service container in which services are created at the start of the application and then registered into a service collection.
Once all services are registered, the service container is built, and the rest of the application starts.
Within classes, dependencies are injected through the constructor, and the framework handles the creation and disposal of instances.

## Additional Information

- In ASP.NET, besides regular classes, there are also CSHTML files, or in the case of the Blazor framework, Razor pages
  - For these files, dependency injection is handled via a special `@inject` directive
- When registering a service in the service collection, there are 3 possible lifetimes:
  - Transient
    - A service with a Transient lifetime is created each time it is requested from the service container
  - Scoped
    - A service with a Scoped lifetime is created once per client request in the case of a web app
  - Singleton
    - A Singleton service is either created at the first use or at a specific time by the developer, and the same instance is used for every subsequent request

## Code

Registration of the service in the service container and application startup:
```cs
HostApplicationBuilder builder = Host.CreateApplicationBuilder(args);

builder.Services.AddSingleton<IServiceInterface, Service>();

using IHost host = builder.Build();

host.Run();
```

Constructor Injection:
```cs
public class Example
{
  private IServiceInterface Service {get; set;}

  public Example(IServiceInterface service)
  {
    Service = service;
  }
}
```

## Sources

Janssen, T., 2023. Design Patterns Explained – Dependency Injection. [online] Stackify. Available at: <https://stackify.com/dependency-injection/> [Accessed 30 May 2024].

Microsoft, 2024. Dependency injection - .NET. [online] Available at: <https://learn.microsoft.com/en-us/dotnet/core/extensions/dependency-injection> [Accessed 30 May 2024].