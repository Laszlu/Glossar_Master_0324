# MVVM

## Definition

MVVM, oder Model-View-ViewModel, ist ein Design Pattern für Software Architektur, welches die Aufgaben innerhalb des Codes in 3 Bestandteile unterteilt, Model, View und ViewModel.
Das Model stellt dabei den Speicherort für die verarbeiteten Daten dar und alle Logik die für diese Speicherung und eventuelle Validierung notwendig ist.
Der View bildet die Struktur und Darstellung der App für den User und wird meist in einer eigenen Darstellungssprache, wie HTML oder XAML geschrieben.
Das ViewModel bildet dabei das Verbindungsstück zwischen Model und View, und besteht vor allem aus Properties und Commands, auf die Daten aus dem View gebunden werden können und benachrichtigt den View über Veränderung mithilfe von Events.


## Zusatzinformationen

- MVVM ist am einfachsten umzusetzen mithilfe von Frameworks, die schon benötigte Interfaces (INotifyPropertyChanged) oder Events implementieren
- Durch die Trennung von Daten, UI und Business Logik ist die Änderung und Wartung von einzelnen Teilen wesentlich einfacher
- Unit Test können ohne Einsatz der View gebaut werden
- MVVM wird vorrangig im Design von Desktop-Anwendungen oder Apps eingesetzt, vor allem in Verbindung mit WPF, .NET MAUI oder XAMARIN

## Grafiken

Darstellung der MVVM Architektur:
![Image](https://learn.microsoft.com/en-us/dotnet/architecture/maui/media/mvvm-pattern.png)
Quelle: https://learn.microsoft.com/en-us/dotnet/architecture/maui/media/mvvm-pattern.png

## Quellen

Microsoft, 2012. The MVVM Pattern. [online] Available at: <https://learn.microsoft.com/en-us/previous-versions/msp-n-p/hh848246(v=pandp.10)> [Accessed 30 May 2024].

Microsoft, 2022. Model-View-ViewModel - .NET. [online] Available at: <https://learn.microsoft.com/en-us/dotnet/architecture/maui/mvvm> [Accessed 30 May 2024].