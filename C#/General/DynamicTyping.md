# Dynamic Typing

## Definition

#### General

Programming languages determine the types of variables either at compile-time or dynamically at runtime.
Scripting languages like JavaScript or Python are not compiled, so variable types can only be checked at runtime.
In compiled languages like C# or C++, types are checked during the compilation process, but there are built-in techniques to bypass this check.

#### Language-specific

In C# version 4.0, the `dynamic` type was introduced, allowing the type check to be bypassed at compile-time.
Instead, the actual type of a `dynamic` variable is determined at runtime.
In combination with reflection, the type can be queried through the code.

## Additional Information

- In most cases, a dynamic type behaves like an object type
- The compiler does not check if the method call on a dynamic variable matches the type of the variable
  - If it does not match, an exception is thrown
- Conversion from dynamic to static types happens implicitly, and any static type can also be converted to a dynamic type

## Code

Dynamic Variables:
```cs
dynamic value1 = "Test"; 
dynamic value2 = 123234; 
dynamic value3 = 2132.55; 
dynamic value4 = false;
```

## Sources

ankita_saini, 2019. Dynamic Type in C#. [online] GeeksforGeeks. Available at: <https://www.geeksforgeeks.org/dynamic-type-in-c-sharp/> [Accessed 30 May 2024].

Microsoft, 2023. Using type dynamic - C#. [online] Available at: <https://learn.microsoft.com/en-us/dotnet/csharp/advanced-topics/interop/using-type-dynamic> [Accessed 30 May 2024].

Mozilla, 2023. Dynamic typing - MDN Web Docs Glossary: Definitions of Web-related terms | MDN. [online] Available at: <https://developer.mozilla.org/en-US/docs/Glossary/Dynamic_typing> [Accessed 30 May 2024].