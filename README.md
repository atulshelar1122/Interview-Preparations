# Interview-Preparations
# OOPS

Classes and Objects
Class: Blueprint that defines structure and behavior
Object: Instance of a class with its own state and behavior
Members: Fields, properties, methods, events, etc.
Instantiation: Creating objects using the new keyword

Four Pillars of OOP

1. Encapsulation
•	Bundling data and methods within a class
•	Restricting access to implementation details
•	Using access modifiers to control visibility
•	Properties with getters/setters to control access to fields
•	Protecting data from invalid states

Example 

public class Person
{
    // Private fields - hidden from outside access
    private string _name;
    private int _age;
    
    // Public properties - controlled access to private fields
    public string Name
    {
        get { return _name; }
        set { _name = value; }
    }
    
    // Property with validation
    public int Age
    {
        get { return _age; }
        set 
        {
            if (value >= 0 && value <= 120)
                _age = value;
            else
                throw new ArgumentException("Age must be between 0 and 120");
        }
    }
    
    // Auto-implemented property (shorthand)
    public string Email { get; set; }
    
    // Read-only property
    public bool IsAdult
    {
        get { return _age >= 18; }
    }
    
    // Constructor
    public Person(string name, int age)
    {
        Name = name;
        Age = age;
    }
    
    // Public method that uses private data
    public string GetDetails()
    {
        return $"{_name} is {_age} years old.";
    }
}
