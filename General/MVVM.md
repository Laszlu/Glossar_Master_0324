# MVVM

## Definition

MVVM, or Model-View-ViewModel, is a design pattern for software architecture that divides the responsibilities within the code into three main components: Model, View, and ViewModel.
The Model represents the storage location for the processed data and all the corresponding logic for this storage and any validation that may be required.
The View defines the structure and visual presentation of the app for the user and is typically written in a markup language, such as HTML or XAML.
The ViewModel acts as the intermediary layer between the Model and the View.
It primarily consists of properties and commands to which data from the View can be bound to and notifies the View of changes through events.

## Additional Information

- MVVM is simplest to implement using frameworks that already provide necessary interfaces (e.g., INotifyPropertyChanged) or events
- The separation of data, UI, and business logic makes it significantly easier to modify and maintain individual components
- Unit tests for the ViewModel and Model can be created without the need for a View
- MVVM is primarily used in the design of desktop or mobile applications, especially in conjunction with WPF, .NET MAUI, or Xamarin

## Graphics

### Representation of the MVVM architecture:

![Image](https://learn.microsoft.com/en-us/dotnet/architecture/maui/media/mvvm-pattern.png)

Source: https://learn.microsoft.com/en-us/dotnet/architecture/maui/media/mvvm-pattern.png

## Sources

Microsoft, 2012. The MVVM Pattern. [online] Available at: <https://learn.microsoft.com/en-us/previous-versions/msp-n-p/hh848246(v=pandp.10)> [Accessed 30 May 2024].

Microsoft, 2022. Model-View-ViewModel - .NET. [online] Available at: <https://learn.microsoft.com/en-us/dotnet/architecture/maui/mvvm> [Accessed 30 May 2024].