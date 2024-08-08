# Entity Framework

## Definition

#### General

The Entity Framework (EF) is an ORM (Object-Relational Mapping) framework that serves as a data access layer for .NET (C#) to connect with various databases.
Among others, SQL databases, MySQL, SQLite, or Azure Cosmos DB can be connected.
The Entity Framework automatically creates an abstraction of the database to different classes, which can be used in the code.
It allows developers to interact with a database through code without using SQL queries.
Currently, there are 2 Versions of Entity Framework available, EF6, which is no longer actively being developed, and EFCore, which is the current, state-of-the-art version.

#### Language-specific

Classes, called Entities, constructed by Entity Framework support LINQ-Queries, change tracking and updates to the database.
EF currently does not support Reflection in C#, so no changes can be made to the entities at runtime.

## Additional Information

- EF needs to be installed via the NuGet Package Management System
- There are 2 approaches to the initialization of EF, Code-First and Database-First
- In a Database-First approach, the entities are created by EF in the Scaffolding procedure
- To use the entities and the connected database, a database context needs to be constructed in the code

## Code

Adding a new object to the database:
```csharp
using (var context = new MyDbContext())
{
    var car = new Car { Name = "Mercedes", MaxSpeed = 240f, Wheels = 4 };

    context.Cars.Add(car); // Add Car to table

    context.SaveChanges(); // save changes to DB
}
```

Using LINQ-queries with EF:
```csharp
var allMercedes = context.Cars.Where(c => c.Name == "Mercedes");

var mercedes = context.Cars.FirstOrDefault(c => c.Name == "Mercedes"); 
```

## Sources

Leismann, J.C., 2023. Entity Framework in C#. Die C# Hilfe. Available at: <https://csharp-hilfe.de/entity-framework-in-csharp/> [Accessed 8 August 2024].

Microsoft, 2024. Entity Framework documentation hub. [online] Available at: <https://learn.microsoft.com/en-us/ef/> [Accessed 8 August 2024].

Musso, E., 2024. Entity Framework using C#. [online] Available at: <https://www.c-sharpcorner.com/article/entity-framework-introduction-using-c-sharp-part-one/> [Accessed 8 August 2024].