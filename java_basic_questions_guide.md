# Java Basic Questions - Complete Guide

## Table of Contents
1. [Basic Syntax & Data Types](#basic-syntax--data-types)
2. [Control Structures](#control-structures)
3. [Arrays](#arrays)
4. [Methods](#methods)
5. [Object-Oriented Programming](#object-oriented-programming)
6. [Exception Handling](#exception-handling)
7. [Collections](#collections)
8. [Strings](#strings)
9. [File I/O](#file-io)
10. [Common Algorithms](#common-algorithms)

---

## Basic Syntax & Data Types

### Question 1: Write a program to demonstrate all primitive data types
```java
public class DataTypes {
    public static void main(String[] args) {
        // Integer types
        byte byteVar = 127;          // 8-bit, range: -128 to 127
        short shortVar = 32767;      // 16-bit, range: -32,768 to 32,767
        int intVar = 2147483647;     // 32-bit, range: -2^31 to 2^31-1
        long longVar = 9223372036854775807L; // 64-bit, range: -2^63 to 2^63-1
        
        // Floating point types
        float floatVar = 3.14f;      // 32-bit IEEE 754
        double doubleVar = 3.14159;  // 64-bit IEEE 754
        
        // Character type
        char charVar = 'A';          // 16-bit Unicode character
        
        // Boolean type
        boolean boolVar = true;      // true or false
        
        System.out.println("byte: " + byteVar);
        System.out.println("short: " + shortVar);
        System.out.println("int: " + intVar);
        System.out.println("long: " + longVar);
        System.out.println("float: " + floatVar);
        System.out.println("double: " + doubleVar);
        System.out.println("char: " + charVar);
        System.out.println("boolean: " + boolVar);
    }
}
```
**Topics**: Primitive data types, variable declaration, literals, type suffixes (L for long, f for float)

### Question 2: Variable scope and initialization
```java
public class VariableScope {
    static int staticVar = 100;     // Class variable
    int instanceVar = 200;          // Instance variable
    
    public static void main(String[] args) {
        int localVar = 300;         // Local variable
        
        VariableScope obj = new VariableScope();
        System.out.println("Static variable: " + staticVar);
        System.out.println("Instance variable: " + obj.instanceVar);
        System.out.println("Local variable: " + localVar);
        
        // Block scope
        {
            int blockVar = 400;
            System.out.println("Block variable: " + blockVar);
        }
        // blockVar is not accessible here
    }
}
```
**Topics**: Variable scope, static vs instance variables, local variables, block scope

---

## Control Structures

### Question 3: If-else statements and ternary operator
```java
public class ConditionalStatements {
    public static void main(String[] args) {
        int number = 25;
        
        // If-else if-else
        if (number > 0) {
            System.out.println("Positive number");
        } else if (number < 0) {
            System.out.println("Negative number");
        } else {
            System.out.println("Zero");
        }
        
        // Ternary operator
        String result = (number % 2 == 0) ? "Even" : "Odd";
        System.out.println("Number is: " + result);
        
        // Nested if
        if (number > 0) {
            if (number % 2 == 0) {
                System.out.println("Positive even number");
            } else {
                System.out.println("Positive odd number");
            }
        }
    }
}
```
**Topics**: Conditional statements, boolean expressions, ternary operator, nested conditions

### Question 4: Loop structures
```java
public class LoopExamples {
    public static void main(String[] args) {
        System.out.println("For loop:");
        for (int i = 1; i <= 5; i++) {
            System.out.print(i + " ");
        }
        
        System.out.println("\nWhile loop:");
        int j = 1;
        while (j <= 5) {
            System.out.print(j + " ");
            j++;
        }
        
        System.out.println("\nDo-while loop:");
        int k = 1;
        do {
            System.out.print(k + " ");
            k++;
        } while (k <= 5);
        
        System.out.println("\nEnhanced for loop:");
        int[] numbers = {1, 2, 3, 4, 5};
        for (int num : numbers) {
            System.out.print(num + " ");
        }
        
        // Break and continue
        System.out.println("\nBreak and continue:");
        for (int i = 1; i <= 10; i++) {
            if (i == 5) continue;  // Skip 5
            if (i == 8) break;     // Exit at 8
            System.out.print(i + " ");
        }
    }
}
```
**Topics**: For loops, while loops, do-while loops, enhanced for loops, break, continue

### Question 5: Switch statement
```java
public class SwitchExample {
    public static void main(String[] args) {
        char grade = 'B';
        
        switch (grade) {
            case 'A':
                System.out.println("Excellent!");
                break;
            case 'B':
                System.out.println("Good!");
                break;
            case 'C':
                System.out.println("Average");
                break;
            case 'D':
                System.out.println("Below Average");
                break;
            default:
                System.out.println("Invalid grade");
        }
        
        // Switch with multiple cases
        int dayOfWeek = 3;
        switch (dayOfWeek) {
            case 1:
            case 2:
            case 3:
            case 4:
            case 5:
                System.out.println("Weekday");
                break;
            case 6:
            case 7:
                System.out.println("Weekend");
                break;
            default:
                System.out.println("Invalid day");
        }
    }
}
```
**Topics**: Switch statements, case labels, break statements, default case, fall-through behavior

---

## Arrays

### Question 6: Array declaration and operations
```java
public class ArrayOperations {
    public static void main(String[] args) {
        // Array declaration and initialization
        int[] numbers1 = new int[5];              // Declaration with size
        int[] numbers2 = {1, 2, 3, 4, 5};        // Declaration with values
        int[] numbers3 = new int[]{6, 7, 8, 9, 10}; // Alternative syntax
        
        // Accessing and modifying array elements
        numbers1[0] = 10;
        numbers1[1] = 20;
        numbers1[2] = 30;
        numbers1[3] = 40;
        numbers1[4] = 50;
        
        System.out.println("Array length: " + numbers1.length);
        
        // Iterating through array
        System.out.println("Using traditional for loop:");
        for (int i = 0; i < numbers1.length; i++) {
            System.out.print(numbers1[i] + " ");
        }
        
        System.out.println("\nUsing enhanced for loop:");
        for (int num : numbers2) {
            System.out.print(num + " ");
        }
        
        // Finding maximum element
        int max = numbers2[0];
        for (int num : numbers2) {
            if (num > max) {
                max = num;
            }
        }
        System.out.println("\nMaximum element: " + max);
    }
}
```
**Topics**: Array declaration, initialization, indexing, length property, iteration, array algorithms

### Question 7: Multidimensional arrays
```java
public class MultidimensionalArrays {
    public static void main(String[] args) {
        // 2D array declaration and initialization
        int[][] matrix = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };
        
        // Alternative declaration
        int[][] matrix2 = new int[3][3];
        
        // Filling the matrix
        int value = 1;
        for (int i = 0; i < matrix2.length; i++) {
            for (int j = 0; j < matrix2[i].length; j++) {
                matrix2[i][j] = value++;
            }
        }
        
        // Printing the matrix
        System.out.println("Matrix:");
        for (int i = 0; i < matrix.length; i++) {
            for (int j = 0; j < matrix[i].length; j++) {
                System.out.print(matrix[i][j] + " ");
            }
            System.out.println();
        }
        
        // Jagged array
        int[][] jaggedArray = new int[3][];
        jaggedArray[0] = new int[2];
        jaggedArray[1] = new int[3];
        jaggedArray[2] = new int[4];
        
        System.out.println("Jagged array lengths:");
        for (int i = 0; i < jaggedArray.length; i++) {
            System.out.println("Row " + i + " length: " + jaggedArray[i].length);
        }
    }
}
```
**Topics**: 2D arrays, multidimensional arrays, jagged arrays, nested loops

---

## Methods

### Question 8: Method overloading and parameters
```java
public class MethodExamples {
    // Method with no parameters
    public static void greet() {
        System.out.println("Hello!");
    }
    
    // Method with parameters
    public static void greet(String name) {
        System.out.println("Hello, " + name + "!");
    }
    
    // Method overloading
    public static int add(int a, int b) {
        return a + b;
    }
    
    public static double add(double a, double b) {
        return a + b;
    }
    
    public static int add(int a, int b, int c) {
        return a + b + c;
    }
    
    // Method with return value
    public static int multiply(int x, int y) {
        return x * y;
    }
    
    // Method with array parameter
    public static int findSum(int[] numbers) {
        int sum = 0;
        for (int num : numbers) {
            sum += num;
        }
        return sum;
    }
    
    // Varargs method
    public static int sum(int... numbers) {
        int total = 0;
        for (int num : numbers) {
            total += num;
        }
        return total;
    }
    
    public static void main(String[] args) {
        greet();
        greet("Alice");
        
        System.out.println("Add int: " + add(5, 3));
        System.out.println("Add double: " + add(5.5, 3.2));
        System.out.println("Add three: " + add(1, 2, 3));
        
        System.out.println("Multiply: " + multiply(4, 5));
        
        int[] arr = {1, 2, 3, 4, 5};
        System.out.println("Array sum: " + findSum(arr));
        
        System.out.println("Varargs sum: " + sum(1, 2, 3, 4, 5));
    }
}
```
**Topics**: Method declaration, parameters, return types, method overloading, varargs, static methods

### Question 9: Recursion
```java
public class RecursionExamples {
    // Factorial using recursion
    public static int factorial(int n) {
        if (n <= 1) {
            return 1;  // Base case
        }
        return n * factorial(n - 1);  // Recursive case
    }
    
    // Fibonacci using recursion
    public static int fibonacci(int n) {
        if (n <= 1) {
            return n;  // Base cases: fib(0) = 0, fib(1) = 1
        }
        return fibonacci(n - 1) + fibonacci(n - 2);
    }
    
    // Binary search using recursion
    public static int binarySearch(int[] arr, int target, int left, int right) {
        if (left > right) {
            return -1;  // Element not found
        }
        
        int mid = left + (right - left) / 2;
        
        if (arr[mid] == target) {
            return mid;
        } else if (arr[mid] > target) {
            return binarySearch(arr, target, left, mid - 1);
        } else {
            return binarySearch(arr, target, mid + 1, right);
        }
    }
    
    public static void main(String[] args) {
        System.out.println("Factorial of 5: " + factorial(5));
        
        System.out.println("Fibonacci series:");
        for (int i = 0; i < 10; i++) {
            System.out.print(fibonacci(i) + " ");
        }
        System.out.println();
        
        int[] sortedArray = {1, 3, 5, 7, 9, 11, 13, 15};
        int target = 7;
        int result = binarySearch(sortedArray, target, 0, sortedArray.length - 1);
        System.out.println("Binary search result: " + result);
    }
}
```
**Topics**: Recursion, base cases, recursive calls, stack overflow, recursive algorithms

---

## Object-Oriented Programming

### Question 10: Classes and objects
```java
// Class definition
class Student {
    // Instance variables (attributes)
    private String name;
    private int age;
    private double gpa;
    
    // Constructor
    public Student(String name, int age, double gpa) {
        this.name = name;
        this.age = age;
        this.gpa = gpa;
    }
    
    // Default constructor
    public Student() {
        this.name = "Unknown";
        this.age = 0;
        this.gpa = 0.0;
    }
    
    // Getter methods
    public String getName() {
        return name;
    }
    
    public int getAge() {
        return age;
    }
    
    public double getGpa() {
        return gpa;
    }
    
    // Setter methods
    public void setName(String name) {
        this.name = name;
    }
    
    public void setAge(int age) {
        if (age > 0) {
            this.age = age;
        }
    }
    
    public void setGpa(double gpa) {
        if (gpa >= 0.0 && gpa <= 4.0) {
            this.gpa = gpa;
        }
    }
    
    // Instance method
    public void displayInfo() {
        System.out.println("Name: " + name + ", Age: " + age + ", GPA: " + gpa);
    }
    
    // Method to check if student is honor roll
    public boolean isHonorRoll() {
        return gpa >= 3.5;
    }
}

public class ClassObjectExample {
    public static void main(String[] args) {
        // Creating objects
        Student student1 = new Student("Alice", 20, 3.8);
        Student student2 = new Student();
        
        // Using objects
        student1.displayInfo();
        student2.displayInfo();
        
        // Setting values using setters
        student2.setName("Bob");
        student2.setAge(19);
        student2.setGpa(3.2);
        
        student2.displayInfo();
        
        // Using methods
        System.out.println(student1.getName() + " is on honor roll: " + student1.isHonorRoll());
        System.out.println(student2.getName() + " is on honor roll: " + student2.isHonorRoll());
    }
}
```
**Topics**: Classes, objects, constructors, instance variables, encapsulation, getters/setters, this keyword

### Question 11: Inheritance
```java
// Base class (Parent/Superclass)
class Animal {
    protected String name;
    protected int age;
    
    public Animal(String name, int age) {
        this.name = name;
        this.age = age;
    }
    
    public void eat() {
        System.out.println(name + " is eating");
    }
    
    public void sleep() {
        System.out.println(name + " is sleeping");
    }
    
    public void displayInfo() {
        System.out.println("Name: " + name + ", Age: " + age);
    }
}

// Derived class (Child/Subclass)
class Dog extends Animal {
    private String breed;
    
    public Dog(String name, int age, String breed) {
        super(name, age);  // Call parent constructor
        this.breed = breed;
    }
    
    // Method specific to Dog
    public void bark() {
        System.out.println(name + " is barking");
    }
    
    // Method overriding
    @Override
    public void displayInfo() {
        super.displayInfo();  // Call parent method
        System.out.println("Breed: " + breed);
    }
}

// Another derived class
class Cat extends Animal {
    private boolean isIndoor;
    
    public Cat(String name, int age, boolean isIndoor) {
        super(name, age);
        this.isIndoor = isIndoor;
    }
    
    public void meow() {
        System.out.println(name + " is meowing");
    }
    
    @Override
    public void displayInfo() {
        super.displayInfo();
        System.out.println("Indoor cat: " + isIndoor);
    }
}

public class InheritanceExample {
    public static void main(String[] args) {
        Dog dog = new Dog("Buddy", 3, "Golden Retriever");
        Cat cat = new Cat("Whiskers", 2, true);
        
        dog.displayInfo();
        dog.eat();
        dog.bark();
        
        System.out.println();
        
        cat.displayInfo();
        cat.sleep();
        cat.meow();
        
        // Polymorphism - treating derived objects as base objects
        Animal animal1 = new Dog("Rex", 4, "German Shepherd");
        Animal animal2 = new Cat("Mittens", 1, false);
        
        animal1.eat();  // Works for both Dog and Cat
        animal2.sleep(); // Works for both Dog and Cat
    }
}
```
**Topics**: Inheritance, extends keyword, super keyword, method overriding, @Override annotation, polymorphism

### Question 12: Abstract classes and interfaces
```java
// Abstract class
abstract class Shape {
    protected String color;
    
    public Shape(String color) {
        this.color = color;
    }
    
    // Abstract method - must be implemented by subclasses
    public abstract double calculateArea();
    
    // Concrete method - can be inherited as-is
    public void displayColor() {
        System.out.println("Color: " + color);
    }
}

// Interface
interface Drawable {
    void draw();  // Implicitly public and abstract
    
    // Default method (Java 8+)
    default void display() {
        System.out.println("Displaying shape");
    }
}

// Class implementing interface and extending abstract class
class Circle extends Shape implements Drawable {
    private double radius;
    
    public Circle(String color, double radius) {
        super(color);
        this.radius = radius;
    }
    
    @Override
    public double calculateArea() {
        return Math.PI * radius * radius;
    }
    
    @Override
    public void draw() {
        System.out.println("Drawing a circle");
    }
}

class Rectangle extends Shape implements Drawable {
    private double length;
    private double width;
    
    public Rectangle(String color, double length, double width) {
        super(color);
        this.length = length;
        this.width = width;
    }
    
    @Override
    public double calculateArea() {
        return length * width;
    }
    
    @Override
    public void draw() {
        System.out.println("Drawing a rectangle");
    }
}

public class AbstractInterfaceExample {
    public static void main(String[] args) {
        Circle circle = new Circle("Red", 5.0);
        Rectangle rectangle = new Rectangle("Blue", 4.0, 6.0);
        
        circle.displayColor();
        circle.draw();
        circle.display();
        System.out.println("Circle area: " + circle.calculateArea());
        
        System.out.println();
        
        rectangle.displayColor();
        rectangle.draw();
        rectangle.display();
        System.out.println("Rectangle area: " + rectangle.calculateArea());
        
        // Polymorphism with interfaces
        Drawable[] drawables = {circle, rectangle};
        for (Drawable drawable : drawables) {
            drawable.draw();
        }
    }
}
```
**Topics**: Abstract classes, abstract methods, interfaces, implements keyword, default methods, multiple inheritance

---

## Exception Handling

### Question 13: Try-catch-finally blocks
```java
public class ExceptionHandling {
    public static void main(String[] args) {
        // Basic try-catch
        try {
            int result = 10 / 0;  // This will throw ArithmeticException
            System.out.println("Result: " + result);
        } catch (ArithmeticException e) {
            System.out.println("Error: Division by zero");
            System.out.println("Exception message: " + e.getMessage());
        }
        
        // Multiple catch blocks
        try {
            int[] numbers = {1, 2, 3};
            System.out.println(numbers[5]);  // ArrayIndexOutOfBoundsException
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Array index out of bounds: " + e.getMessage());
        } catch (Exception e) {
            System.out.println("General exception: " + e.getMessage());
        }
        
        // Try-catch-finally
        try {
            String str = null;
            System.out.println(str.length());  // NullPointerException
        } catch (NullPointerException e) {
            System.out.println("Null pointer exception caught");
        } finally {
            System.out.println("Finally block always executes");
        }
        
        // Try-with-resources
        try (java.util.Scanner scanner = new java.util.Scanner("Hello World")) {
            while (scanner.hasNext()) {
                System.out.println(scanner.next());
            }
        } catch (Exception e) {
            System.out.println("Exception in try-with-resources: " + e.getMessage());
        }
    }
}
```
**Topics**: Exception handling, try-catch-finally, multiple catch blocks, try-with-resources

### Question 14: Custom exceptions and throws
```java
// Custom exception class
class InvalidAgeException extends Exception {
    public InvalidAgeException(String message) {
        super(message);
    }
}

class BankAccount {
    private double balance;
    private String accountNumber;
    
    public BankAccount(String accountNumber, double initialBalance) {
        this.accountNumber = accountNumber;
        this.balance = initialBalance;
    }
    
    // Method that throws checked exception
    public void withdraw(double amount) throws Exception {
        if (amount > balance) {
            throw new Exception("Insufficient funds. Balance: " + balance);
        }
        balance -= amount;
        System.out.println("Withdrawn: $" + amount + ". New balance: $" + balance);
    }
    
    // Method that throws custom exception
    public void setAge(int age) throws InvalidAgeException {
        if (age < 0 || age > 150) {
            throw new InvalidAgeException("Invalid age: " + age + ". Age must be between 0 and 150.");
        }
        System.out.println("Age set to: " + age);
    }
    
    public double getBalance() {
        return balance;
    }
}

public class CustomExceptionExample {
    public static void main(String[] args) {
        BankAccount account = new BankAccount("12345", 1000.0);
        
        // Handling checked exception
        try {
            account.withdraw(500.0);  // This should work
            account.withdraw(600.0);  // This should throw exception
        } catch (Exception e) {
            System.out.println("Transaction failed: " + e.getMessage());
        }
        
        // Handling custom exception
        try {
            account.setAge(25);   // Valid age
            account.setAge(-5);   // Invalid age
        } catch (InvalidAgeException e) {
            System.out.println("Age validation failed: " + e.getMessage());
            e.printStackTrace();
        }
        
        // Demonstrating finally with return
        System.out.println("Final balance: $" + getFinalBalance(account));
    }
    
    public static double getFinalBalance(BankAccount account) {
        try {
            return account.getBalance();
        } finally {
            System.out.println("Getting final balance...");
        }
    }
}
```
**Topics**: Custom exceptions, throws keyword, checked vs unchecked exceptions, exception propagation

---

## Collections

### Question 15: ArrayList and LinkedList
```java
import java.util.*;

public class ListExamples {
    public static void main(String[] args) {
        // ArrayList example
        ArrayList<String> arrayList = new ArrayList<>();
        arrayList.add("Apple");
        arrayList.add("Banana");
        arrayList.add("Cherry");
        arrayList.add(1, "Orange");  // Insert at index 1
        
        System.out.println("ArrayList: " + arrayList);
        System.out.println("Size: " + arrayList.size());
        System.out.println("Element at index 2: " + arrayList.get(2));
        
        // Iterating through ArrayList
        System.out.println("Iterating with enhanced for loop:");
        for (String fruit : arrayList) {
            System.out.println(fruit);
        }
        
        // Iterator
        System.out.println("Iterating with Iterator:");
        Iterator<String> iterator = arrayList.iterator();
        while (iterator.hasNext()) {
            System.out.println(iterator.next());
        }
        
        // LinkedList example
        LinkedList<Integer> linkedList = new LinkedList<>();
        linkedList.add(10);
        linkedList.add(20);
        linkedList.add(30);
        linkedList.addFirst(5);   // Add at beginning
        linkedList.addLast(40);   // Add at end
        
        System.out.println("LinkedList: " + linkedList);
        System.out.println("First element: " + linkedList.getFirst());
        System.out.println("Last element: " + linkedList.getLast());
        
        // Removing elements
        arrayList.remove("Banana");
        arrayList.remove(0);  // Remove by index
        System.out.println("ArrayList after removal: " + arrayList);
        
        linkedList.removeFirst();
        linkedList.removeLast();
        System.out.println("LinkedList after removal: " + linkedList);
        
        // Converting to array
        String[] fruitsArray = arrayList.toArray(new String[0]);
        System.out.println("Array from ArrayList: " + Arrays.toString(fruitsArray));
    }
}
```
**Topics**: ArrayList, LinkedList, List interface, generics, iterators, collection methods

### Question 16: HashMap and HashSet
```java
import java.util.*;

public class MapSetExamples {
    public static void main(String[] args) {
        // HashMap example
        HashMap<String, Integer> scores = new HashMap<>();
        scores.put("Alice", 95);
        scores.put("Bob", 87);
        scores.put("Charlie", 92);
        scores.put("Diana", 88);
        
        System.out.println("HashMap: " + scores);
        System.out.println("Alice's score: " + scores.get("Alice"));
        System.out.println("Contains Bob: " + scores.containsKey("Bob"));
        System.out.println("Contains score 90: " + scores.containsValue(90));
        
        // Iterating through HashMap
        System.out.println("Iterating through HashMap:");
        for (Map.Entry<String, Integer> entry : scores.entrySet()) {
            System.out.println(entry.getKey() + ": " + entry.getValue());
        }
        
        // Alternative iteration methods
        System.out.println("Keys: " + scores.keySet());
        System.out.println("Values: " + scores.values());
        
        // HashSet example
        HashSet<String> uniqueNames = new HashSet<>();
        uniqueNames.add("John");
        uniqueNames.add("Jane");
        uniqueNames.add("Bob");
        uniqueNames.add("John");  // Duplicate - won't be added
        
        System.out.println("HashSet: " + uniqueNames);
        System.out.println("Size: " + uniqueNames.size());
        System.out.println("Contains Jane: " + uniqueNames.contains("Jane"));
        
        // Converting List to Set (removes duplicates)
        List<Integer> numbersWithDuplicates = Arrays.asList(1, 2, 3, 2, 4, 1, 5);
        Set<Integer> uniqueNumbers = new HashSet<>(numbersWithDuplicates);
        System.out.println("Original list: " + numbersWithDuplicates);
        System.out.println("Unique numbers: " + uniqueNumbers);
        
        // TreeMap and TreeSet (sorted collections)
        TreeMap<String, Integer> sortedScores = new TreeMap<>(scores);
        System.out.println("TreeMap (sorted by keys): " + sortedScores);
        
        TreeSet<String> sortedNames = new TreeSet<>(uniqueNames);
        System.out.println("TreeSet (sorted): " + sortedNames);
    }
}
```
**Topics**: HashMap, HashSet, Map interface, Set interface, key-value pairs, TreeMap, TreeSet

---

## Strings

### Question 17: String manipulation
```java
public class StringExamples {
    public static void main(String[] args) {
        // String creation
        String str1 = "Hello";
        String str2 = new String("World");
        String str3 = "Hello";  // String literal pool
        
        System.out.println("str1 == str3: " + (str1 == str3));  // true (same reference)
        System.out.println("str1 == str2: " + (str1 == str2));  // false (different references)
        System.out.println("str1.equals(str2): " + str1.equals(str2));  // false (different content)
        
        // String methods
        String text = "Java Programming Language";
        System.out.println("Length: " + text.length());
        System.out.println("Character at index 5: " + text.charAt(5));
        System.out.println("Substring: " + text.substring(5, 16));
        System.out.println("Index of 'Pro': " + text.indexOf("Pro"));
        System.out.println("Last index of 'a': " + text.lastIndexOf("a"));
        
        // String comparison
        System.out.println("Equals 'java programming language': " + 
                          text.equals("java programming language"));
        System.out.println("Equals ignore case: " + 
                          text.equalsIgnoreCase("java programming language"));
        System.out.println("Starts with 'Java': " + text.startsWith("Java"));
        System.out.println("Ends with 'Language': " + text.endsWith("Language"));
        
        // String modification (returns new string)
        System.out.println("Uppercase: " + text.toUpperCase());
        System.out.println("Lowercase: " + text.toLowerCase());
        System.out.println("Replace 'a' with '@': " + text.replace('a', '@'));
        System.out.println("Replace 'Java' with 'Python': " + text.replace("Java", "Python"));
        
        String spacedText = "  Hello World  ";
        System.out.println("Trimmed: '" + spacedText.trim() + "'");
        
        // String splitting
        String csvData = "apple,banana,cherry,date";
        String[] fruits = csvData.split(",");
        System.out.println("Split result: " + Arrays.toString(fruits));
        
        // String joining (Java 8+)
        String joined = String.join(" | ", fruits);
        System.out.println("Joined: " + joined);
    }
}
```
**Topics**: String class, string literals, string pool, string methods, immutability

### Question 18: StringBuilder and StringBuffer
```java
public class StringBuilderExample {
    public static void main(String[] args) {
        // StringBuilder (not thread-safe, better performance)
        StringBuilder sb = new StringBuilder();
        sb.append("Hello");
        sb.append(" ");
        sb.append("World");
        sb.append("!");
        
        System.out.println("StringBuilder result: " + sb.toString());
        System.out.println("Length: " + sb.length());
        System.out.println("Capacity: " + sb.capacity());
        
        // StringBuilder with initial capacity
        StringBuilder sb2 = new StringBuilder(50);
        sb2.append("Java");
        sb2.insert(4, " Programming");  // Insert at position 4
        System.out.println("After insert: " + sb2.toString());
        
        sb2.delete(4, 16);  // Delete from index 4 to 15
        System.out.println("After delete: " + sb2.toString());
        
        sb2.reverse();
        System.out.println("Reversed: " + sb2.toString());
        
        // StringBuffer (thread-safe, synchronized)
        StringBuffer sbf = new StringBuffer("Thread-safe");
        sbf.append(" string manipulation");
        System.out.println("StringBuffer result: " + sbf.toString());
        
        // Performance comparison
        long startTime, endTime;
        
        // String concatenation (inefficient)
        startTime = System.currentTimeMillis();
        String result = "";
        for (int i = 0; i < 10000; i++) {
            result += "a";
        }
        endTime = System.currentTimeMillis();
        System.out.println("String concatenation time: " + (endTime - startTime) + "ms");
        
        // StringBuilder (efficient)
        startTime = System.currentTimeMillis();
        StringBuilder efficientSb = new StringBuilder();
        for (int i = 0; i < 10000; i++) {
            efficientSb.append("a");
        }
        String efficientResult = efficientSb.toString();
        endTime = System.currentTimeMillis();
        System.out.println("StringBuilder time: " + (endTime - startTime) + "ms");
    }
}
```
**Topics**: StringBuilder, StringBuffer, mutable strings, performance optimization, thread safety

---

## File I/O

### Question 19: File reading and writing
```java
import java.io.*;
import java.nio.file.*;
import java.util.*;

public class FileIOExamples {
    public static void main(String[] args) {
        String fileName = "sample.txt";
        
        // Writing to file using FileWriter
        try (FileWriter writer = new FileWriter(fileName)) {
            writer.write("Hello, World!\n");
            writer.write("This is a sample file.\n");
            writer.write("Java File I/O example.\n");
            System.out.println("File written successfully");
        } catch (IOException e) {
            System.out.println("Error writing file: " + e.getMessage());
        }
        
        // Reading from file using FileReader
        try (FileReader reader = new FileReader(fileName);
             BufferedReader bufferedReader = new BufferedReader(reader)) {
            
            System.out.println("Reading file using BufferedReader:");
            String line;
            while ((line = bufferedReader.readLine()) != null) {
                System.out.println(line);
            }
        } catch (IOException e) {
            System.out.println("Error reading file: " + e.getMessage());
        }
        
        // Using Scanner to read file
        try (Scanner scanner = new Scanner(new File(fileName))) {
            System.out.println("Reading file using Scanner:");
            while (scanner.hasNextLine()) {
                System.out.println(scanner.nextLine());
            }
        } catch (FileNotFoundException e) {
            System.out.println("File not found: " + e.getMessage());
        }
        
        // Using Files class (Java 7+)
        try {
            // Write all lines at once
            List<String> lines = Arrays.asList(
                "Line 1 from Files.write",
                "Line 2 from Files.write",
                "Line 3 from Files.write"
            );
            Files.write(Paths.get("files_example.txt"), lines);
            
            // Read all lines at once
            List<String> readLines = Files.readAllLines(Paths.get("files_example.txt"));
            System.out.println("Reading using Files.readAllLines:");
            for (String line : readLines) {
                System.out.println(line);
            }
            
            // Read entire file as string
            String content = new String(Files.readAllBytes(Paths.get(fileName)));
            System.out.println("Entire file content:\n" + content);
            
        } catch (IOException e) {
            System.out.println("Error with Files operations: " + e.getMessage());
        }
        
        // File information
        File file = new File(fileName);
        System.out.println("File exists: " + file.exists());
        System.out.println("File size: " + file.length() + " bytes");
        System.out.println("Can read: " + file.canRead());
        System.out.println("Can write: " + file.canWrite());
        System.out.println("Is file: " + file.isFile());
        System.out.println("Is directory: " + file.isDirectory());
        
        // Clean up
        try {
            Files.deleteIfExists(Paths.get(fileName));
            Files.deleteIfExists(Paths.get("files_example.txt"));
        } catch (IOException e) {
            System.out.println("Error deleting files: " + e.getMessage());
        }
    }
}
```
**Topics**: File I/O, FileReader, FileWriter, BufferedReader, Scanner, Files class, Path class

---

## Common Algorithms

### Question 20: Sorting and searching algorithms
```java
import java.util.Arrays;

public class AlgorithmExamples {
    // Bubble Sort
    public static void bubbleSort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {
            for (int j = 0; j < n - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    // Swap elements
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }
    }
    
    // Selection Sort
    public static void selectionSort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {
            int minIndex = i;
            for (int j = i + 1; j < n; j++) {
                if (arr[j] < arr[minIndex]) {
                    minIndex = j;
                }
            }
            // Swap minimum element with first element
            int temp = arr[minIndex];
            arr[minIndex] = arr[i];
            arr[i] = temp;
        }
    }
    
    // Linear Search
    public static int linearSearch(int[] arr, int target) {
        for (int i = 0; i < arr.length; i++) {
            if (arr[i] == target) {
                return i;
            }
        }
        return -1;  // Not found
    }
    
    // Binary Search (requires sorted array)
    public static int binarySearch(int[] arr, int target) {
        int left = 0;
        int right = arr.length - 1;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            
            if (arr[mid] == target) {
                return mid;
            } else if (arr[mid] < target) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        return -1;  // Not found
    }
    
    // Find maximum element
    public static int findMax(int[] arr) {
        if (arr.length == 0) return Integer.MIN_VALUE;
        
        int max = arr[0];
        for (int i = 1; i < arr.length; i++) {
            if (arr[i] > max) {
                max = arr[i];
            }
        }
        return max;
    }
    
    // Calculate sum of array elements
    public static int arraySum(int[] arr) {
        int sum = 0;
        for (int num : arr) {
            sum += num;
        }
        return sum;
    }
    
    // Reverse array
    public static void reverseArray(int[] arr) {
        int left = 0;
        int right = arr.length - 1;
        
        while (left < right) {
            int temp = arr[left];
            arr[left] = arr[right];
            arr[right] = temp;
            left++;
            right--;
        }
    }
    
    public static void main(String[] args) {
        int[] originalArray = {64, 34, 25, 12, 22, 11, 90};
        
        // Bubble Sort
        int[] bubbleArray = originalArray.clone();
        System.out.println("Original array: " + Arrays.toString(bubbleArray));
        bubbleSort(bubbleArray);
        System.out.println("Bubble sorted: " + Arrays.toString(bubbleArray));
        
        // Selection Sort
        int[] selectionArray = originalArray.clone();
        selectionSort(selectionArray);
        System.out.println("Selection sorted: " + Arrays.toString(selectionArray));
        
        // Arrays.sort() - built-in sorting
        int[] builtInSorted = originalArray.clone();
        Arrays.sort(builtInSorted);
        System.out.println("Built-in sorted: " + Arrays.toString(builtInSorted));
        
        // Linear Search
        int target = 25;
        int linearResult = linearSearch(originalArray, target);
        System.out.println("Linear search for " + target + ": " + linearResult);
        
        // Binary Search (requires sorted array)
        int binaryResult = binarySearch(builtInSorted, target);
        System.out.println("Binary search for " + target + ": " + binaryResult);
        
        // Built-in binary search
        int builtInBinaryResult = Arrays.binarySearch(builtInSorted, target);
        System.out.println("Built-in binary search for " + target + ": " + builtInBinaryResult);
        
        // Other operations
        System.out.println("Maximum element: " + findMax(originalArray));
        System.out.println("Sum of elements: " + arraySum(originalArray));
        
        int[] reverseArray = originalArray.clone();
        reverseArray(reverseArray);
        System.out.println("Reversed array: " + Arrays.toString(reverseArray));
    }
}
```
**Topics**: Sorting algorithms, searching algorithms, time complexity, array manipulation

---

## Summary

This guide covers the fundamental Java concepts that every beginner should master:

1. **Basic Syntax**: Data types, variables, operators
2. **Control Structures**: Conditionals, loops, switch statements
3. **Arrays**: Single and multidimensional arrays
4. **Methods**: Parameters, return types, overloading, recursion
5. **OOP**: Classes, objects, inheritance, polymorphism, abstraction, encapsulation
6. **Exception Handling**: Try-catch-finally, custom exceptions
7. **Collections**: Lists, Sets, Maps and their implementations
8. **Strings**: String manipulation, StringBuilder/StringBuffer
9. **File I/O**: Reading and writing files
10. **Algorithms**: Basic sorting and searching algorithms

Each example demonstrates practical usage while explaining the underlying concepts. Practice these examples and modify them to deepen your understanding of Java programming.