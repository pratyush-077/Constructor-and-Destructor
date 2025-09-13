# Experiment 12 – Constructors and Destructors in C++
Name: Pratyush Saha
PRN: 24070123078
Class: ENTC A3
Experiment Number: 12
Title: Implementation of Constructors and Destructors in C++

# Theory
Constructors in C++
A constructor in C++ is a special member function of a class that is executed automatically when an object of the class is created. Its primary purpose is to initialize the data members of an object so that the object starts in a well-defined state.

Key Properties of Constructors:
The name of the constructor must be the same as the class name.
It does not have a return type (not even void).
It is called automatically when the object is created.
Constructors can be overloaded (multiple constructors with different parameters).
If no constructor is defined, the compiler provides a default constructor.
Types of Constructors:
Default Constructor

Takes no parameters.
Initializes objects with default values or user-defined inputs.
Parameterized Constructor

Accepts parameters to initialize objects with specific values.
Provides flexibility to set values during object creation.
Copy Constructor

Initializes an object as a copy of another object.
Syntax: ClassName (const ClassName &obj) { ... }
Useful in scenarios like passing objects by value, returning objects from functions, or duplicating objects.
Advantages of Constructors:
Automatic initialization of objects.
Improves readability and maintainability of code.
Reduces redundant function calls for initialization.
Supports polymorphism through overloading (different forms of constructors).
Limitations of Constructors:
Cannot be virtual.
Cannot return values.
Cannot be inherited, though base class constructors can be invoked using derived class initializer lists.
Cannot be explicitly called like normal functions (only indirectly via object creation).
Constructors are the foundation of object-oriented programming in C++:
They ensure automatic, safe, and flexible initialization of objects.
Provide different forms like default, parameterized, copy, dynamic, and conversion.
Support overloading and delegation.
Widely used in real-world applications for resource management.
Destructors in C++
A destructor is a special member function that is automatically invoked when an object goes out of scope or is explicitly deleted. Its purpose is to free resources such as memory, file handles, or network connections that were acquired during the object’s lifetime.

It has the same name as the class preceded by a tilde ~.
It does not take any arguments and does not return any value.
Only one destructor can exist per class (no overloading).
Key Properties of Destructors:
Has the same name as the class but preceded with a tilde ~.
Takes no arguments and does not return any value.
Only one destructor per class is allowed (cannot be overloaded).
Called automatically in the reverse order of object creation (last created object is destroyed first).
Uses of Destructors:
Free dynamically allocated memory.
Close open files.
Release locks or network resources.
Print debug/logging information to track object lifetimes.
Advantages of Destructors:
Automatic Resource Cleanup
Frees memory, file handles, or network connections when the object goes out of scope.
Code Simplicity
No need to explicitly call cleanup functions.
Smart pointers and modern C++ designs rely on destructors for safe memory management.
Improves Program Stability
Prevents memory leaks and dangling resources.
Encapsulation of Cleanup
Keeps cleanup logic inside the class, avoiding redundancy.
Limitations of Destructors:
Execution Order in Inheritance
Called in reverse order of construction, which can cause resource issues if not carefully managed.
No Overloading
Unlike constructors, destructors cannot be overloaded.
Uncertainty for Global/Static Objects
Destructor call order across multiple files is undefined.
Performance Overhead
Heavy cleanup tasks can slow down object destruction.
Exception Safety
Destructors should never throw exceptions (can cause program termination).
Codes Algorithms and summary:
Constructors Programs
1. Constructor Inside the Class
Code Summary:
In this program, the Student class has a constructor defined inside the class. It is called automatically when an object is created and takes input for fields like name, PRN, branch, division, and fee. The display() function then shows the details. This demonstrates how constructors simplify initialization directly at object creation.

Algorithm:

Start the program.
Define Student class with private data members.
Write a constructor inside the class that takes input for all details.
Write display() to print values.
In main(), create object s → constructor is invoked automatically.
Call display() to show stored details.
End.
2. Constructor Outside the Class
Code Summary:
Here, the constructor of the Student class is declared inside but defined outside the class using the scope resolution operator. The functionality is the same, but this method improves code clarity and organization, especially in large programs.

Algorithm:

Start.
Declare class Student with constructor prototype and display() function.
Define Student::Student() outside the class.
Take input for student details in constructor.
In main(), create object s.
Constructor is automatically invoked.
Display details using display().
End.
3. Parameterized Constructor
Code Summary:
In this code, the Practice class uses a parameterized constructor that accepts values when the object is created. For example, Practice p(7,8); directly initializes data members. This removes the need for separate input and provides flexible initialization.

Algorithm:

Start.
Define class Practice with integer variables.
Define constructor with two parameters (m, n) and assign values.
Create method display() to print a and b.
In main(), create object p(7, 8) → constructor initializes values.
Call display().
End.
4. Copy Constructor (Student Example)
Code Summary:
In the student class, the attributes are name and age. The parameterized constructor initializes the first object (s1), and then another object (s2) is created using the copy constructor (student s2 = s1;). The copy constructor not only copies the values but also prints "Copy Constructor Called." along with a message indicating that the output is from the copy constructor. Both s1 and s2 display the same data, proving that the copy constructor successfully duplicated the original object.

Algorithm:

Start.
Define class student with data members name and age.
Define parameterized constructor.
Define copy constructor that copies details and prints a message.
Create object s1 using parameterized constructor.
Create object s2 as a copy of s1 → copy constructor called.
Display details of both objects.
End.
5. Copy Constructor (Car Example)
Code Summary:
This program defines a Car class with attributes Car_name, Manufacturer, and Price. A parameterized constructor initializes the first object (c1). Then, the copy constructor is explicitly defined to copy the values of one object into another (Car copyC(c1);). When the copy constructor is invoked, it prints "copy constructor called!!" and then the new object (copyC) displays the same details as the original. This shows how copy constructors duplicate objects while providing custom actions (like printing a message).

Algorithm:

Start.
Define class Car with data members.
Define parameterized constructor to initialize details.
Define copy constructor → copies all values from existing object.
Display details of the original object.
Create new object using copy constructor and display details.
End.
Destructor Programs
6. Destructor (Date Example)
Code Summary:
The Date class demonstrates a destructor, which is called automatically when an object goes out of scope. It prints a message when invoked. This shows how destructors are used for cleanup tasks like freeing resources or closing files.

Algorithm:

Start.
Define class Date with destructor ~Date().
In main(), create multiple objects of Date.
Use loop to create temporary objects inside scope.
Observe destructor calls.
End.
7. Destructor (Object Counter Example)
Code Summary:
Here, constructors and destructors track the number of objects using a count variable. Each constructor call increases the count, and each destructor decreases it. This program shows the lifecycle of objects and how destructors handle resource management automatically.

Algorithm:

Start.
Define class destruct with constructor and destructor.
Increment counter in constructor and display creation message.
Decrement counter in destructor and display destruction message.
In main(), create multiple objects.
Create a block scope and destroy one object explicitly.
End.
# Final Conclusion
Constructors simplify object initialization by automating the setup process when objects are created.
They can be default, parameterized, or copy constructors, allowing flexible object creation.
Destructors are equally important as they release resources when objects are destroyed.
Together, constructors and destructors provide robust object lifecycle management in C++.
These concepts form the backbone of Object-Oriented Programming (OOP) in C++, ensuring cleaner, safer, and more efficient code.
