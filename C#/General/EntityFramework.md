# Entity Framework

## Definition

#### Allgemein

The Entity Framework (EF) is an ORM (Object-Relational Mapping) framework that serves as a data access layer for .NET (C#) with various databases.
Among others, SQL databases, MySQL, SQLite, or Azure Cosmos DB can be linked.
The Entity Framework automatically creates an abstraction of the database in classes that can be used in the code.
It allows developers to interact with a database through code without using SQL queries.
Currently, there are 2 Versions of Entity Framework available, EF6, which is no longer actively being developed, and EFCore, which is the current, state-of-the-art version.

#### Sprachenspezifisch

Classes (Entities) constructed by Entity Framework support LINQ-Queries, change tracking and updates to the database.
EF currently does not support Reflection in C#, so no changes can be made to the entities at runtime.

## Zusatzinformationen

- EF needs to be installed via the NuGet Package Management System
- There are 2 approaches to the initialization of EF, Code-First and Database-First
- In a Database-First approach, the entities are created by EF in the Scaffolding procedure
- To use the entities and the connected database, a database context needs to be constructed in the code

## Grafiken

### Titel der Grafik

![Image](https://www.google.com/images/branding/googlelogo/1x/googlelogo_color_272x92dp.png)

Quelle: https://www.google.com/images/branding/googlelogo/1x/googlelogo_color_272x92dp.png

## Code

Code Snippet:
```csharp
using (var context = new MyDbContext())
{
    var car = new Car { Name = "Mercedes", MaxSpeed = 240f, Wheels = 4 };

    context.Cars.Add(car); // Wir fügen der Tabelle das Auto hinzu

    context.SaveChanges(); // Wir speichern die Änderungen
}
```

## Quellen

Link: [Google](google.de)