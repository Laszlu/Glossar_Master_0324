# Reflection

## Definition

#### Allgemein

Reflection ist die Fähigkeit einer Programmiersprache, während der Laufzeit eines Programms die eigenen Konstrukte zu untersuchen.
Damit kann beispielsweise eine Klasse dynamisch aus einer Assembly geladen, ein Typ nach einem bestimmten Member untersucht oder sogar dynamisch Code erstellt werden.
Ein wichtiger Anwendungsbereich für Reflection sind Unit Tests.

#### Sprachenspezifisch

In C# sind verschiedene Klassen und Funktionen integriert um Reflection zu ermöglichen.
Unter anderem kann mit GetType() oder TypeOf der Typ eines Objekts geprüft und im weiteren Verlauf des Codes verwendet werden.
Allerdings ist Reflection in C# relativ langsam, weshalb es nur in Szenarien verwendet werden sollte, in denen traditionelle Techniken nicht ausreichen.

## Code

Einsatz von GetType():
```cs
int i = 42;
System.Type type = i.GetType();
System.Console.WriteLine(type);

// Output:
System.Int32
```

Erstellung eines Objekts aus einer dynamisch geladenen Assembly:

```cs
// Calculator Class in seperate assembly Test.dll
namespace Test
{
    public class Calculator
    {
        public Calculator() { ... }
        private double _number;
        public double Number { get; set; }
    }
}

// Load Assembly
Assembly testAssembly = Assembly.LoadFile(@"c:\Test.dll");

// Create Instance
Type calcType = testAssembly.GetType("Test.Calculator");
object calcInstance = Activator.CreateInstance(calcType);

// Access Members
PropertyInfo numberPropertyInfo = calcType.GetProperty("Number");
double value = (double)numberPropertyInfo.GetValue(calcInstance, null);
numberPropertyInfo.SetValue(calcInstance, 10.0, null);
```


## Quellen

Altvater, A., 2023. How C# Reflection Works With Code Examples. [online] Stackify. Available at: <https://stackify.com/what-is-c-reflection/> [Accessed 30 May 2024].

Microsoft, 2024. Reflection in .NET. [online] Available at: <https://learn.microsoft.com/en-us/dotnet/fundamentals/reflection/reflection> [Accessed 30 May 2024].