# Dependancy Injection

## Definition

#### Allgemein

Dependancy Injection (im Folgenden "DI") ist eine Programmiertechnik in der objektorientierten Programmierung.
Das Ziel von DI ist, die Abhängigkeiten innerhalb einer Klasse an einer zentralen Stelle verwalten zu können und damit eine Klasse unabhängig von ihren Abhängigkeiten zu machen.
Um dies zu erreichen wird die Verwendung eines Objekts von seiner Erstellung getrennt.
Durch den Einsatz von DI werden 2 der 5 Prinzipien von SOLID befolgt, Dependancy Inversion und Single Responsibility.
Hard-Coded Abhängigkeiten sollten aus verschiedenen Gründen vermieden werden, zum einen weil bei Veränderung der Abhängigkeit auch die abhängige Klasse geändert werden muss.
Außerdem verteilt sich durch solche Abhängigkeiten die Konfiguration der Anwendung über den gesamten Code und ist schlechter zu warten.

#### Sprachenspezifisch

In C#, oder spezifischer .NET, wird DI über den Service-Container der Anwendung implementiert.
.Net bietet einen integrierten Service-Container, Services werden beim Start der Anwendung erstellt und danach in eine Servie-Collection registriert.
Sobald alle Services registriert wurden, wird der Service-Container gebaut und der Rest der Anwendung gestartet.
Innerhalb der Klassen werden die Abhängigkeiten dann im Konstruktor injected und das Framework kümmert sich um die Erstellung und das Aufräumen von Instanzen.

## Zusatzinformationen

- In ASP.NET gibt es neben normalen Klassen auch CSHTML-Dateien, oder im Falle des Blazor Frameworks, Razor-Pages
  - bei diesen Dateien wird die Injection der Abhängigkeiten über eine spezielle Direktive abgehandelt
- Bei der Registrierung eines Services in die Service-Collection gibt es 3 mögliche Lifetimes:
  - Transient
    - Ein Service mit Transient Lifetime wird jedesmal erzeugt, wenn er beim Service-Container angefragt wird
  - Scoped
    - Ein Service mit Scoped Lifetime wird im Falle einer Web-App einmal pro Client-Request erzeugt
  - Singleton
    - Ein Singleton Service wird entweder bei der ersten Nutzung oder vom Entwickler zu einem festen Zeitpunkt erstellt, bei jeder folgenden Anfrage wird die selbe Instanz verwendet

## Code

Registrierung des Service in den Service-Container und Start der Anwendung:
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

## Quellen

Janssen, T., 2023. Design Patterns Explained – Dependency Injection. [online] Stackify. Available at: <https://stackify.com/dependency-injection/> [Accessed 30 May 2024].

Microsoft, 2024. Dependency injection - .NET. [online] Available at: <https://learn.microsoft.com/en-us/dotnet/core/extensions/dependency-injection> [Accessed 30 May 2024].