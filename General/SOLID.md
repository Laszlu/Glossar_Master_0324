# SOLID

## Definition

#### Allgemein

SOLID ist ein Acronym für eine Sammlung von 5 Prinzipien von Robert C. Martin, die die Grundlage für moderne Software-Architektur in objektorientierter Programmierung bilden.
Die 5 Prinzipien sind die Folgenden:
- Single Responsibility Principle (1):
  - A class should have one and only one reason to change, meaning that a class should have only one job
- Open-Closed Principle (2):
  - Objects or entities should be open for extension but closed for modification.
- Liskov Substitution Principle (3):
  - Let q(x) be a property provable about objects of x of type T. Then q(y) should be provable for objects y of type S where S is a subtype of T.
- Interface Segregation Principle (4):
  - A client should never be forced to implement an interface that it doesn’t use, or clients shouldn’t be forced to depend on methods they do not use.
- Dependancy Inversion Principle (5):
  - Entities must depend on abstractions, not on concretions. It states that the high-level module must not depend on the low-level module, but they should depend on abstractions.

Das Ziel dieser 5 Prinzipien ist es, objektorientierten Code verständlicher, flexibler und wartbarer zu machen.

## Zusatzinformationen

Seit der Aufstellung von SOLID hat sich die Software Industrie stark verändert, und viele der aktuell genutzten Sprachen können die originalen Prinzipien nicht mehr 1 zu 1 umsetzen.
Daher gibt es neuere Definitionen für die 5 Prinzipien, damit auch funktionale Programmierung oder andere Herangehensweisen abgedeckt werden.
- (1) Each module should do one thing and do it well
- (2) You should be able to use and add to a module without rewriting it
- (3) You should be able to substitute one thing for another if those things are declared to behave the same way
- (4) Don't show your clients more than they need to see
- (5) Depend upon abstractions, not concretions

## Quellen

Oloruntoba, S. and Walia, A.S., 2024. SOLID: The First 5 Principles of Object Oriented Design | DigitalOcean. [online] Available at: <https://www.digitalocean.com/community/conceptual-articles/s-o-l-i-d-the-first-five-principles-of-object-oriented-design> [Accessed 31 May 2024].

Orner, D., 2021. Why SOLID principles are still the foundation for modern software architecture - Stack Overflow. [online] Available at: <https://stackoverflow.blog/2021/11/01/why-solid-principles-are-still-the-foundation-for-modern-software-architecture/> [Accessed 31 May 2024].

Wikipedia, 2024. SOLID. In: Wikipedia. [online] Available at: <https://en.wikipedia.org/w/index.php?title=SOLID&oldid=1226113447> [Accessed 31 May 2024].