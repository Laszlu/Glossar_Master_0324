# Reflection

## Definition

#### General

Reflection is the ability of a programming language to examine its own constructs during the runtime of a program.
For example, it allows a class to be dynamically loaded from an assembly, a type to be inspected for a specific member, or even code to be generated dynamically.
An important application area for reflection is Unit Testing.

#### Language-specific

In C#, various classes and functions are integrated to enable reflection.
For example, you can use `GetType()` or `typeof` to check the type of an object and use it later in the code.
However, reflection in C# is relatively slow, so it should only be used in scenarios where traditional techniques are insufficient.

## Code

Usage of GetType():
```cs
int i = 42;
System.Type type = i.GetType();
System.Console.WriteLine(type);

// Output:
System.Int32
```

Creation of an object from a dynamically loaded assembly:

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


## Sources

Altvater, A., 2023. How C# Reflection Works With Code Examples. [online] Stackify. Available at: <https://stackify.com/what-is-c-reflection/> [Accessed 30 May 2024].

Microsoft, 2024. Reflection in .NET. [online] Available at: <https://learn.microsoft.com/en-us/dotnet/fundamentals/reflection/reflection> [Accessed 30 May 2024].