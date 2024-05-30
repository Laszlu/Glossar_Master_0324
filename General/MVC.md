# MVC

## Definition

Mode-View-Controller (MVC) ist ein Design Pattern in der Software Architektur, bei dem die Software in 3 zentrale Bestandteile unterteilt wird, "Model", die "View" und der "Controller".
Mit "View" bezeichnet man meist das User Interface oder andere Schnittstellen, über die der Nutzer das Programm bedient und die grafische Darstellung des Programms.
Das "Model" dient vor allem zur Struktrierung und Speicherung der Daten, die das Programm verarbeitet.
Der "Controller" schließlich steuert die gesamte Anwendung und verarbeitet die Daten, die zum Beispiel vom Nutzer oder vom Sensoren oder Ähnlichem kommen.
Diese Architektur einer Anwendung ermöglicht eine flexible Architektur mit hoher Wiederverwendbarkeit der einzelnen Module.

## Zusatzinformationen

- Bei einer kleinen Anwendung bedeutet der Einsatz einer MVC-Architektur einen sehr hohen Aufwand und ist nicht in jedem Fall sinnvoll
- MVC ermöglicht eine sehr einfache Erweiterung eines Programms durch die hohe Modularität und die geringe Abhängigkeit der Module
- In ASP.NET setzt MVC oft Dependancy Injection ein, um SOLID Prinzipien einzuhalten und die Verantwortungen der Module besser zu trennen

## Grafiken

Darstellung der MVC Architektur:
![Image](https://upload.wikimedia.org/wikipedia/commons/thumb/a/a0/MVC-Process.svg/1000px-MVC-Process.svg.png)
Quelle: https://upload.wikimedia.org/wikipedia/commons/thumb/a/a0/MVC-Process.svg/1000px-MVC-Process.svg.png

## Quellen

Kowa, 2020. Model-View-Controller-Paradigma – GlossarWiki. [online] GlossarWiki HS Augsburg. Available at: <https://glossar.hs-augsburg.de/Model-View-Controller-Paradigma> [Accessed 30 May 2024].

Microsoft, 2023. Overview of ASP.NET Core MVC. [online] Available at: <https://learn.microsoft.com/en-us/aspnet/core/mvc/overview?view=aspnetcore-8.0> [Accessed 30 May 2024].

RegisFrey, 2010. The model, view, and controller (MVC) pattern relative to the user. [online] Wikipedia. Available at: <https://en.wikipedia.org/wiki/File:MVC-Process.svg> [Accessed 30 May 2024].