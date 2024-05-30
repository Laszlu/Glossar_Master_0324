# Dynamic Typing

## Definition

#### Allgemein

Programmiersprachen bestimmen die Typen ihrer Variablen entweder zur Compile-Time oder dynamisch zur Runtime.
Skript-Sprachen wie JavaScript oder Python werden nicht kompiliert und die Variablen können daher nur während der Runtime geprüft werden.
Bei kompilierten Sprachen wie C# oder C++ werden die Typen beim Kompiliervorgang geprüft, aber es gibt integrierte Techniken, um diese Prüfung zu umgehen.

#### Sprachenspezifisch

In C# wurde in Version 4.0 der "dynamic" Type eingeführt, mit dem der Type Check während der Compile-Time umgangen werden kann.
Stattdessen wird der reale Typ einer dynamic-Variabel während der Runtime ermittelt.
In Kombination mit Reflection kann der Typ im Code abgefragt werden.

## Zusatzinformationen

- In den meisten Fällen verhält sich ein dynamischer Typ wie ein Objekttyp
- Der Compiler prüft bei Methodenaufrufen einer dynamischen Variable nicht, ob die Methode zum Typ der Variable passt
  - ist das nicht der Fall, wird eine Exception geworfen
- Die Umwandlung von dynamischen in statische Typen findet implizit statt und jeder statische Typ kann auch in einen dynamischen kovertiert werden 

## Code

Dynamische Variablen:
```cs
dynamic value1 = "Test"; 
dynamic value2 = 123234; 
dynamic value3 = 2132.55; 
dynamic value4 = false;
```

## Quellen

ankita_saini, 2019. Dynamic Type in C#. [online] GeeksforGeeks. Available at: <https://www.geeksforgeeks.org/dynamic-type-in-c-sharp/> [Accessed 30 May 2024].

Microsoft, 2023. Using type dynamic - C#. [online] Available at: <https://learn.microsoft.com/en-us/dotnet/csharp/advanced-topics/interop/using-type-dynamic> [Accessed 30 May 2024].

Mozilla, 2023. Dynamic typing - MDN Web Docs Glossary: Definitions of Web-related terms | MDN. [online] Available at: <https://developer.mozilla.org/en-US/docs/Glossary/Dynamic_typing> [Accessed 30 May 2024].