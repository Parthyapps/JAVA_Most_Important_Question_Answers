# JAVA_Most_Important_Question_Answers

    Thread: Use a background thread to download images so the UI thread isn’t blocked.
    Thread Pool: Use a thread pool to manage multiple image downloads efficiently.
    String: Store image URLs as strings.
    String Pool: Reuse identical URLs stored in the string pool.
    Multithread Management: Multithreading in Java is a feature that allows concurrent execution of two or more threads, enabling a program to perform multiple tasks simultaneously

   - Object-Oriented Programming (OOP) in Java is a programming style that revolves around objects and their interactions. Here are the four main OOP concepts explained simply with examples:

    ✔️ Encapsulation → Repository class hides API logic. Encapsulation ensures data is not directly accessed. Instead, the Repository class handles all API logic.
    ✔️ Inheritance → ViewModel inherits common logic from BaseViewModel.
    ✔️ Polymorphism → Retrofit interface allows multiple API functions.
    ✔️ Abstraction → NewsDataSource hides API implementation details.shows only neccessary action.

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

Garbage Collection (GC) is the process of automatically freeing up memory by removing objects that are no longer in use. Java handles this automatically, so developers don’t need to manually manage memory.
    Object Creation: When you create an object (e.g., new String("Hello")), it’s allocated in the heap memory.

    Reference Tracking: The JVM keeps track of all object references.
    Unreferenced Objects: Objects that are no longer referenced by any part of the program are considered "garbage."
    Garbage Collection Process:
        The JVM runs the Garbage Collector periodically.
        The GC identifies unreferenced objects and frees up their memory.
        The freed memory can then be reused for new objects.
