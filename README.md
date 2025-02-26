# JAVA_Most_Important_Question_Answers
   - Object-Oriented Programming (OOP) in Java is a programming style that revolves around objects and their interactions. Here are the four main OOP concepts explained simply with examples:

# 1. Encapsulation

   - Protects data by hiding it behind methods. Ex:getName, setName
   - Encapsulation is the bundling of data (variables) and methods (functions) that operate on the data into a single unit (class). It also restricts direct access to some components to protect the integrity of the data.
   - Private data can only be accessed or modified using public methods.

```kotlin
class Person {
    private String name; // Private variable (hidden from outside)

    // Getter method to access the name
    public String getName() {
        return name;
    }

    // Setter method to set the name
    public void setName(String name) {
        this.name = name;
    }
}

public class Main {
    public static void main(String[] args) {
        Person person = new Person();
        person.setName("John"); // Set the name using a method
        System.out.println(person.getName()); // Access the name using a method
    }
}
```
2.Polymorphism
    
    - One Task is performed in different ways it is know as polymorphism, 
      multiple implementations. Ex:Overloading, Overriding
    - allows you to define one 
    - Polymorphism allows one interface to be used for multiple forms (methods or objects). It is achieved through method overloading and method overriding.
    Key Point: Polymorphism allows flexibility by treating objects differently based on their type.
```kotlin
Example (Method Overloading):
class Calculator {
    // Same method name, different parameters
    int add(int a, int b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }
}

public class Main {
    public static void main(String[] args) {
        Calculator calc = new Calculator();
        System.out.println(calc.add(2, 3)); // Calls the first add method
        System.out.println(calc.add(1, 2, 3)); // Calls the second add method
    }
}
```
```kotlin
class Animal {
    void sound() {
        System.out.println("This animal makes a sound.");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("The dog barks.");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal animal = new Dog();
        animal.sound(); // Calls the overridden method in Dog
    }
}
```
3.Abstraction
    - Hides implementation details, shows only essentials. Ex:Abstract classes
   - Abstraction hides the implementation details and shows only the essential features of an object. It can be achieved using abstract classes or interfaces.
Key Point: Abstract classes cannot be instantiated, and they provide a blueprint for subclasses.
``` kotlin
abstract class Vehicle {
    abstract void start(); // Abstract method (no implementation)

    void stop() {
        System.out.println("Vehicle stopped.");
    }
}

class Car extends Vehicle {
    @Override
    void start() {
        System.out.println("Car starts with a key.");
    }
}

public class Main {
    public static void main(String[] args) {
        Vehicle car = new Car();
        car.start(); // Implementation from Car
        car.stop();  // Implementation from Vehicle
    }
}
```

4.Inheritance
    - Reuse code from a parent class. Ex:Dog inherits Animal
    -Inheritance allows a class (child) to acquire the properties and methods of another class (parent). This helps in code reuse.

 ```kotlin
    // Parent class
class Animal {
    void eat() {
        System.out.println("This animal eats food.");
    }
}

// Child class
class Dog extends Animal {
    void bark() {
        System.out.println("The dog barks.");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.eat(); // Inherited from Animal
        dog.bark(); // Defined in Dog
    }
}
```
# String Pool

The String Pool, also known as the String Intern Pool, is a memory optimization technique in Java. It stores a single copy of each unique string literal in a special memory area within the Heap.
Key Features of the String Pool

    Memory Efficiency: Reduces memory usage by reusing string literals.
    Immutability: Strings are immutable, so they can be safely shared.
    Performance: Faster comparison due to reference equality (==).
    
# Thread
A thread is the smallest unit or part of execution in a program. It allows you to perform multiple tasks concurrently. Java provides support for multithreading to allow concurrent execution of two or more threads.

    Used for tasks like downloading data, processing images, or handling background tasks.
    Avoid direct thread creation for UI updates; use Handler, AsyncTask (deprecated), Coroutines, or Executors.

    public class MyThread extends Thread {
    @Override
    public void run() {
        System.out.println("Thread is running");
    }

    public static void main(String[] args) {
        MyThread thread = new MyThread();
        thread.start(); // Starts the thread
    }
    }

# Thread Pool
A thread pool is a collection of pre-initialized threads that can be reused to execute multiple tasks. It avoids the overhead of creating and destroying threads repeatedly.

    Essential for managing multiple background tasks efficiently in Android.
    The Executors framework or libraries like WorkManager and RxJava internally manage thread pools.
    
    import java.util.concurrent.ExecutorService;
    import java.util.concurrent.Executors;

    public class ThreadPoolExample {
    public static void main(String[] args) {
        // Create a thread pool with 2 threads
        ExecutorService executor = Executors.newFixedThreadPool(2);

        // Submit tasks to the thread pool
        executor.submit(() -> System.out.println("Task 1"));
        executor.submit(() -> System.out.println("Task 2"));

        // Shutdown the thread pool
        executor.shutdown();
    }
    }

String 
A String is an immutable sequence of characters in Java.
    String str = "Hello, World!";
        System.out.println(str);

String Pool:
The String Pool is a special memory area in Java where String literals are stored. It helps save memory by reusing identical strings.

    Reduces memory overhead for string-heavy applications.
    Immutability makes strings safe to use across threads.

    public class StringPoolExample {
    public static void main(String[] args) {
        String str1 = "Hello"; // Stored in String Pool
        String str2 = "Hello"; // Reuses the same object from String Pool
        String str3 = new String("Hello"); // Creates a new object in heap memory

        System.out.println(str1 == str2); // true (same reference)
        System.out.println(str1 == str3); // false (different references)
    }
    }

Multithread Management in Android  
In Android, multithreading is essential to perform background tasks without blocking the main UI thread. Common tools include:

    AsyncTask (Deprecated in API level 30)
    HandlerThread
    Executors
    Coroutines (Kotlin)
