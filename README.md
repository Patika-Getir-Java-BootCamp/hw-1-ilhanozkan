# HW#1

## 1 – Why we need to use OOP ? Some major OOP languages ?
We use OOP (Object-Oriented Programming) to organize, simplify, and manage programs by modeling them after real-world objects.

OOP consists of four main concepts:

- Abstraction
- Encapsulation
- Polymorphism
- Inheritance

These concepts were developed by software experts to make programming more cost-effective and easier to maintain.

### Explanation of OOP Concepts

- `Abstraction` allows developers to hide complex implementation details, exposing only the essential features. This reduces complexity and makes the program easier to work with.

- `Encapsulation` improves code reliability by bundling data and methods together, restricting direct access to certain parts of the program to prevent unintended modifications.

- `Polymorphism` enables the same method or function to behave differently depending on the object it is applied to. This makes code more flexible and reusable.

- `Inheritance` allows properties and methods to be passed from a parent class to a child class. In Java, a class can inherit from only one other class, but we can use interfaces or abstract classes to incorporate additional functionality.

### Major OOP Languages
Some of the most widely used OOP languages include:

- C++
- Java
- C#
- Python
- Ruby
- Swift

## 2 – Interface vs Abstract class ?

- **Interface:** An interface in Java is a blueprint of a class that contains only method signatures (no body). However, Java 8+ allows default and static methods. It supports multiple inheritance.

- **Abstract class:** An abstract class can have method implementations and supports single inheritance. It can contain both abstract and concrete methods and is used when classes share behavior but also require customization.

Both of those can not be instantiated.

Use an interface when multiple classes share functionality but don’t need shared implementation. Use an abstract class when you want to provide default behavior.

## 3 – Why we need equals and hashcode ? When to override ?

equals() and hashCode() are methods used to compare objects in Java. The equals() method determines whether two objects are logically equal based on their properties, while the hashCode() method generates a unique numerical representation of an object.

### When to override ?

If we need to check whether two objects are equal, we override the equals() method to specify which properties should be considered for equality. Additionally, when overriding equals(), we must also override hashCode() to ensure that objects considered equal produce the same hash code, which is important for hash-based collections like HashMap and HashSet.

## 4 – Diamond problem in Java ? How to fix it?

The Diamond Problem occurs in Java when a class attempts to inherit from multiple classes, leading to confusion about which method should be executed if the same method exists in multiple parent classes. Since Java does not support multiple inheritance for classes, this issue is avoided by allowing multiple inheritance only through interfaces.

Java allows a class to extend only one parent class. However, in some cases, we may need to inherit functionalities from multiple classes.

For example, suppose we want to create an ElectricSuvCar class that extends both ElectricCar and SuvCar. In Java, this is not possible using the extends keyword, as Java does not support multiple inheritance with classes. This limitation is known as the Diamond Problem.

### How to fix it?

To resolve the Diamond Problem, we can use interfaces. Unlike classes, a Java class can implement multiple interfaces, allowing us to achieve multiple inheritance in a controlled manner.

## 5 – Why we need Garbagge Collector ? How does it run ?

In Java, memory management is handled automatically by the Garbage Collector (GC). We need a Garbage Collector to remove unused objects from memory, preventing memory leaks and optimizing application performance.

The Garbage Collector cleans up objects in the heap memory that are no longer referenced by any part of the program. This process helps free up memory and ensures efficient resource management.

### How does it run?

The Garbage Collector runs periodically in the background. It identifies objects that are no longer in use and automatically removes them. The most common way Java detects unused objects is through reachability analysis—if an object cannot be reached by any active thread or static reference, it becomes eligible for garbage collection.

Different Garbage Collection algorithms (such as Serial GC, Parallel GC, G1 GC, and ZGC) manage memory in different ways, optimizing for performance based on application needs.

Garbage Collection usually runs automatically, but developers can suggest it by calling `System.gc()`. However, this is only a request, and the JVM may choose to ignore it.

## 6 – Java ‘static’ keyword usage ?

`static` keyword can be used for variables, methods, blocks, nested classes and imports in Java.

### Static Variables:

- A static variable is shared across all instances of a class.
- It is initialized only once when the class is loaded.

### Static Methods:

- A static method belongs to the class and can be called without creating an instance.
- It cannot access instance (non-static) variables or methods directly.

### Static Blocks:

- Used to initialize static variables before the class is used.
- Executes only once when the class is loaded.

### Static Classes (Nested Classes):

- A static nested class does not need an instance of the outer class to be instantiated.

### Static Imports:

- Allows direct access to static members of a class without using the class name.

## 7 – Immutability means ? Where, How and Why to use it ?

Immutability in Java means that an object's state cannot be changed after it is created. Once an immutable object is initialized, its fields cannot be modified, ensuring that it remains constant throughout its lifetime.

### Where to use it?

- Multithreading & Concurrency
- Caching & Performance Optimization
- Security
- Key Objects in Collections

### How to use it?

We can provide immutability to variables with using `final` keyword. Immutability can save the value without any changes of a variable until programme finished.

**Creating an Immutable Class**

To make a class immutable, follow these best practices:

- Declare the class as final – Prevents subclassing.
- Make fields private and final – Prevents direct access and modification.
- Provide only a parameterized constructor – Ensures values are set only once.
- Do not provide setter methods – Prevents modification after creation.
- Return copies of mutable fields – Ensures the internal state is not exposed.

### Why to use it?

- Thread Safety – No synchronization needed in concurrent applications.
- Reliable Caching – Can be safely cached and shared across the application.
- Predictability – Once created, the object's state is fixed, preventing unintended side effects.
- Better Hashing – Ideal for using as HashMap keys, ensuring consistency.

## 8 – Composition and Aggregation means and differences ?

Composition and Aggregation are relations between entities in object-oriented programming.
They define how objects are connected and interact with each other.

Composition and Aggregation are types of association between classes.
Composition is a strong association where the child object cannot exist without the parent object.
Aggregation is a weak association where the child object can exist independently of the parent object.

### Composition:

- **Strong association** between classes.
- Child object cannot exist without the parent object.
- Child object is created and destroyed with the parent object.
- Represented by a **"has-a"** relationship.
- Example: A car has an engine. If the car is destroyed, the engine is also destroyed.

### Aggregation:

- **Weak association** between classes.
- Child object can exist independently of the parent object.
- Child object is not created or destroyed with the parent object.
- Represented by a **"part-of"** relationship.
- Example: A university has departments. Departments can exist independently of the university.

## 9 – Cohesion and Coupling means and differences ?

Cohesion and Coupling are design principles in software engineering that describe how classes or components are interconnected and interact with each other.

### Coupling:

- Coupling refers to the degree of interdependence between classes or components.
- High coupling means that classes are closely connected and depend on each other. Changes in one class may affect other classes. This can lead to maintenance issues. If we use a class in another class directly, it is called high (tight) coupling.
- Low coupling means that classes are more independent and can be modified without affecting other classes. This improves maintainability and flexibility. If we use an interface, it is called low (loose) coupling.

### Cohesion:

- Cohesion refers to the degree to which the elements within a module or class are related to each other.
- High cohesion means that the elements within a module are closely related and work together to achieve a common goal.
- Low cohesion means that the elements within a module are loosely related and perform different tasks.

## 10 - Heap and Stack means and differences ?

Stack and Heap are two memory areas used by the Java Virtual Machine (JVM) to store data during program execution.

Stack stores method calls and local variables (often stores primitive data types and object references. Only one time variable can be stored in the stack. If a method is called, it is stored in the stack and when the method is finished, it is removed from the stack.), while Heap stores objects and their instance variables. Heap is a dynamic memory area where objects are allocated and deallocated during runtime.

### Stack:

- Stores method calls and local variables.
- Follows the Last In First Out (LIFO) principle.
- Memory is allocated and deallocated automatically.
- Limited in size and faster access.
- Used for static memory allocation.

### Heap:

- Stores objects and their instance variables.
- Memory is allocated and deallocated manually.
- Dynamic in size and slower access.
- Used for dynamic memory allocation.

## 11 – Exception means ? Type of Exceptions ?

An exception in Java is an event that disrupts the normal flow of a program. Exceptions can occur during runtime due to various reasons, such as invalid input, file not found, or network issues.

### Types of Exceptions:

**Built-in Exceptions:**

- **Checked Exceptions:** These exceptions are checked at compile time and must be handled using try-catch blocks or declared in the method signature using the `throws` keyword. Examples include `IOException`, `SQLException`, and `ClassNotFoundException`.

- **Unchecked Exceptions (Runtime Exceptions):** These exceptions are not checked at compile time and can be handled or ignored. Examples include `NullPointerException`, `ArrayIndexOutOfBoundsException`, and `ArithmeticException`.

**Custom Exceptions:**

- Developers can create custom exceptions by extending the `Exception` class or one of its subclasses. Custom exceptions are useful for handling application-specific errors.

**Error:**

- Errors are exceptional conditions that are not expected to be caught or handled by the application. Examples include `OutOfMemoryError`, `StackOverflowError`, and `NoClassDefFoundError`.

## 12 – How to summarize ‘clean code’ as short as possible ?

Clean code is code that is easy to read, understand, and maintain. It follows best practices and coding standards to improve readability and reduce complexity. Clean code should be self-explanatory, well-organized, and free of unnecessary clutter.

## 13 - What is the method of hiding in Java ?

In Java, the concept of "hiding" typically refers to field hiding (also known as variable hiding or name hiding). This occurs when a subclass declares a field with the same name as a field in its superclass.

### Key points about field hiding:

- Unlike method overriding, field hiding is based on the reference type, not the object's actual type.
- The hidden field from the parent class is still accessible using super keyword.
- Field hiding is generally considered a poor practice as it can lead to confusing code.

### Example:

```java
class Parent {
    public int value = 10;
}

class Child extends Parent {
    public int value = 20; // This hides Parent's value field
}
```

```java
Parent p = new Parent();
System.out.println(p.value);  // Outputs 10

Child c = new Child();
System.out.println(c.value);  // Outputs 20

Parent pc = new Child();
System.out.println(pc.value); // Outputs 10, not 20!
```

`pc.value` accesses the parent's field because the reference type is Parent, even though the object is a Child.

## 14 - What is the difference between abstraction and polymorphism in Java ?

Abstraction and Polymorphism are two fundamental concepts in object-oriented programming that help in designing and implementing complex systems.

### Differences:

- **Abstraction** focuses on hiding implementation details, while **Polymorphism** focuses on providing multiple behaviors.
- Abstraction is achieved through abstract classes and interfaces, while Polymorphism is achieved through method overriding and method overloading.
- Abstraction defines a blueprint for classes, while Polymorphism allows objects to take on multiple forms.
