> Migrated from Davin-X/tech-notes@a1e8fb480b45d6e7f32735f69337c10be32f04a9 (java/java_essentials.md) — preserved as a getting-started reference.

# Java Essentials

**Core Java concepts for object-oriented programming**

---

## 1. Variables & Data Types

```java
// Primitive Data Types
int age = 25;                    // Integer (-2^31 to 2^31-1)
long bigNumber = 123456789L;     // Long integer (with L)
double pi = 3.14159;             // Double precision floating point
float price = 19.99f;            // Single precision (with f)
boolean isActive = true;         // Boolean (true/false)
char grade = 'A';                // Single character
byte smallNumber = 127;          // Byte (-128 to 127)
short mediumNumber = 32000;      // Short integer

// Reference Types
String name = "Alice";           // String (immutable)
int[] numbers = {1, 2, 3};       // Array
ArrayList<String> list = new ArrayList<>();

// Type casting
double d = 9.78;
int i = (int) d;  // 9 (explicit narrowing)

// Wrapper classes
Integer intObj = Integer.valueOf(42);      // Integer object
Double doubleObj = Double.valueOf(3.14);   // Double object
String str = Integer.toString(42);         // "42"

// Constants
final int MAX_USERS = 100;      // Constant (with final)
final String APP_NAME = "MyApp"; // String constant

System.out.println("Name: " + name + ", Age: " + age);
```

## 2. Operators & Expressions

```java
// Arithmetic Operators
int a = 10, b = 3;
System.out.println("Addition: " + (a + b));        // 13
System.out.println("Subtraction: " + (a - b));     // 7
System.out.println("Multiplication: " + (a * b));  // 30
System.out.println("Division: " + (a / b));       // 3 (integer division)
System.out.println("Modulus: " + (a % b));        // 1
System.out.println("Increment: " + (++a));        // 11
System.out.println("Decrement: " + (--b));        // 2

// Comparison Operators
System.out.println("Equal: " + (a == b));         // false
System.out.println("Not equal: " + (a != b));     // true
System.out.println("Greater than: " + (a > b));   // true
System.out.println("Less than: " + (a < b));      // false
System.out.println("Greater or equal: " + (a >= b)); // true
System.out.println("Less or equal: " + (a <= b));    // false

// Logical Operators
boolean x = true, y = false;
System.out.println("AND: " + (x && y));        // false
System.out.println("OR: " + (x || y));         // true
System.out.println("NOT: " + (!x));            // false

// Bitwise Operators
int p = 60, q = 13;  // 60 = 0011 1100, 13 = 0000 1101
System.out.println("AND: " + (p & q));          // 12  (0000 1100)
System.out.println("OR: " + (p | q));           // 61  (0011 1101)
System.out.println("XOR: " + (p ^ q));          // 49  (0011 0001)
System.out.println("Complement: " + (~p));       // -61
```

## 3. Control Flow

```java
// If-Else statements
int score = 85;
String grade;
if (score >= 90) {
    grade = "A";
} else if (score >= 80) {
    grade = "B";
} else if (score >= 70) {
    grade = "C";
} else {
    grade = "F";
}
System.out.println("Grade: " + grade);

// Switch statement
int day = 3;
String dayName;
switch (day) {
    case 1: dayName = "Monday"; break;
    case 2: dayName = "Tuesday"; break;
    case 3: dayName = "Wednesday"; break;
    case 4: dayName = "Thursday"; break;
    case 5: dayName = "Friday"; break;
    case 6: dayName = "Saturday"; break;
    case 7: dayName = "Sunday"; break;
    default: dayName = "Invalid day"; break;
}
System.out.println("Day " + day + " is " + dayName);

// Switch with arrow syntax (Java 14+)
String result = switch (day) {
    case 1, 2, 3, 4, 5 -> "Weekday";
    case 6, 7 -> "Weekend";
    default -> "Invalid";
};
System.out.println("It's a " + result);

// Ternary operator
boolean isAdult = (age >= 18) ? true : false;
String status = age >= 18 ? "Adult" : "Minor";
```

## 4. Loops

```java
// For loop
System.out.println("For loop:");
for (int i = 0; i < 5; i++) {
    System.out.print(i + " ");
}
System.out.println();

// Enhanced for loop
int[] numbers = {10, 20, 30, 40, 50};
System.out.println("Enhanced for loop:");
for (int num : numbers) {
    System.out.print(num + " ");
}
System.out.println();

// While loop
System.out.println("While loop:");
int counter = 0;
while (counter < 5) {
    System.out.print(counter + " ");
    counter++;
}
System.out.println();

// Do-while loop
System.out.println("Do-while loop:");
int count = 0;
do {
    System.out.print(count + " ");
    count++;
} while (count < 3);
System.out.println();

// Break and continue
System.out.println("Break example:");
for (int i = 0; i < 10; i++) {
    if (i == 5) {
        break;  // Exit loop
    }
    System.out.print(i + " ");
}
System.out.println();

System.out.println("Continue example:");
for (int i = 0; i < 5; i++) {
    if (i == 2) {
        continue;  // Skip iteration
    }
    System.out.print(i + " ");
}
System.out.println();
```

## 5. Methods & Functions

```java
// Method definition
public static int add(int a, int b) {
    return a + b;
}

// Method with multiple parameters
public static void printInfo(String name, int age, String city) {
    System.out.println("Name: " + name + ", Age: " + age + ", City: " + city);
}

// Method with default parameters (achieved through method overloading)
public static void greet(String name) {
    greet(name, "Hello");
}

public static void greet(String name, String greeting) {
    System.out.println(greeting + ", " + name + "!");
}

// Variable arguments (varargs)
public static int sum(int... numbers) {
    int total = 0;
    for (int num : numbers) {
        total += num;
    }
    return total;
}

// Recursive method
public static int factorial(int n) {
    if (n <= 1) {
        return 1;
    } else {
        return n * factorial(n - 1);
    }
}

// Method calls
System.out.println("Addition: " + add(5, 3));                    // 8
printInfo("Alice", 25, "NYC");                                 // Name: Alice, Age: 25, City: NYC
greet("Bob");                                                 // Hello, Bob!
greet("Charlie", "Hi");                                       // Hi, Charlie!
System.out.println("Sum: " + sum(1, 2, 3, 4, 5));             // 15
System.out.println("Factorial 5: " + factorial(5));           // 120

// Lambda expressions (Java 8+)
interface Calculator {
    int operate(int a, int b);
}

// Without lambda
Calculator addCalc = new Calculator() {
    public int operate(int a, int b) {
        return a + b;
    }
};

// With lambda
Calculator multiplyCalc = (a, b) -> a * b;
Calculator divideCalc = (a, b) -> a / b;

System.out.println("Lambda addition: " + addCalc.operate(3, 4));        // 7
System.out.println("Lambda multiplication: " + multiplyCalc.operate(3, 4)); // 12
```

## 6. Classes & OOP

```java
// Class definition
class Person {
    // Instance variables (fields)
    private String name;
    private int age;

    // Static variable (class variable)
    private static int population = 0;

    // Constructor
    public Person() {
        this("Unknown", 0);
    }

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
        population++;  // Increment population
    }

    // Getter methods
    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }

    // Setter methods
    public void setName(String name) {
        if (name != null && !name.trim().isEmpty()) {
            this.name = name;
        }
    }

    public void setAge(int age) {
        if (age >= 0 && age <= 150) {
            this.age = age;
        }
    }

    // Instance method
    public String greet() {
        return "Hello, I'm " + name + " and I'm " + age + " years old.";
    }

    // Static method
    public static int getPopulation() {
        return population;
    }

    // toString method override
    @Override
    public String toString() {
        return "Person{name='" + name + "', age=" + age + "}";
    }

    // equals method override
    @Override
    public boolean equals(Object obj) {
        if (this == obj) return true;
        if (obj == null || getClass() != obj.getClass()) return false;

        Person person = (Person) obj;
        return age == person.age && name.equals(person.name);
    }

    // hashCode method override
    @Override
    public int hashCode() {
        return Objects.hash(name, age);
    }
}

// Usage
Person alice = new Person("Alice", 25);
Person bob = new Person("Bob", 30);

System.out.println(alice.greet());                    // Hello, I'm Alice and I'm 25 years old.
System.out.println(bob.toString());                   // Person{name='Bob', age=30}
System.out.println("Population: " + Person.getPopulation()); // Population: 2
```

## 7. Inheritance

```java
// Base class
class Animal {
    protected String name;
    protected int age;

    public Animal(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String makeSound() {
        return "Some sound";
    }

    public void eat() {
        System.out.println(name + " is eating.");
    }

    public final void breathe() {  // Final method
        System.out.println("Breathing...");
    }
}

// Derived class (inheritance)
class Dog extends Animal {
    private String breed;

    public Dog(String name, int age, String breed) {
        super(name, age);  // Call parent constructor
        this.breed = breed;
    }

    @Override
    public String makeSound() {
        return "Woof! Woof!";
    }

    public void fetch() {
        System.out.println(name + " is fetching a ball.");
    }
}

// Another derived class
class Cat extends Animal {
    private String color;

    public Cat(String name, int age, String color) {
        super(name, age);
        this.color = color;
    }

    @Override
    public String makeSound() {
        return "Meow! Meow!";
    }

    public void scratch() {
        System.out.println(name + " is scratching.");
    }
}

// Usage
Animal genericAnimal = new Animal("Generic", 5);
Dog buddy = new Dog("Buddy", 3, "Golden Retriever");
Cat whiskers = new Cat("Whiskers", 2, "Orange");

System.out.println(genericAnimal.makeSound());    // Some sound
System.out.println(buddy.makeSound());            // Woof! Woof!
System.out.println(whiskers.makeSound());         // Meow! Meow!

buddy.fetch();      // Buddy is fetching a ball.
whiskers.scratch(); // Whiskers is scratching.

// Polymorphism
Animal[] animals = {buddy, whiskers};
for (Animal animal : animals) {
    System.out.println(animal.makeSound());  // Different behavior
}
```

## 8. Interfaces & Abstract Classes

```java
// Interface definition
interface Drawable {
    void draw();  // Abstract method (public and abstract by default)

    // Default method (Java 8+)
    default void setColor(String color) {
        System.out.println("Setting color to " + color);
    }

    // Static method (Java 8+)
    static void printInfo() {
        System.out.println("This is the Drawable interface");
    }
}

// Another interface
interface Resizable {
    void resize(double factor);
    double getArea();
}

// Abstract class
abstract class Shape implements Drawable {
    protected String color;
    protected String name;

    public Shape(String name, String color) {
        this.name = name;
        this.color = color;
    }

    // Abstract method
    public abstract double calculateArea();

    // Concrete method
    public String getDescription() {
        return name + " (" + color + ")";
    }

    @Override
    public void setColor(String color) {
        this.color = color;
        System.out.println(name + " color changed to " + color);
    }
}

// Concrete class implementing interface and extending abstract class
class Circle extends Shape implements Resizable {
    private double radius;

    public Circle(String name, String color, double radius) {
        super(name, color);
        this.radius = radius;
    }

    @Override
    public void draw() {
        System.out.println("Drawing a circle with radius " + radius);
    }

    @Override
    public double calculateArea() {
        return Math.PI * radius * radius;
    }

    @Override
    public void resize(double factor) {
        radius *= factor;
        System.out.println("Circle resized. New radius: " + radius);
    }

    @Override
    public double getArea() {
        return calculateArea();
    }

    public double getRadius() {
        return radius;
    }
}

// Usage
Circle circle = new Circle("MyCircle", "Red", 5.0);

System.out.println(circle.getDescription());      // MyCircle (Red)
System.out.printf("Area: %.2f%n", circle.calculateArea());  // Area: 78.54

circle.draw();                                    // Drawing a circle with radius 5.0
circle.setColor("Blue");                          // MyCircle color changed to Blue
circle.resize(1.5);                               // Circle resized. New radius: 7.5

System.out.printf("New area: %.2f%n", circle.getArea());  // New area: 176.71

// Static method call
Drawable.printInfo();  // This is the Drawable interface
```

## 9. Exception Handling

```java
public class ExceptionHandlingDemo {

    // Basic try-catch
    public static void basicTryCatch() {
        try {
            int result = 10 / 0;
            System.out.println("Result: " + result);
        } catch (ArithmeticException e) {
            System.out.println("ArithmeticException caught: " + e.getMessage());
        }
    }

    // Multiple catch blocks
    public static void multipleCatch() {
        try {
            String str = null;
            System.out.println(str.length());  // NullPointerException
        } catch (NullPointerException e) {
            System.out.println("NullPointerException: " + e.getMessage());
        } catch (Exception e) {
            System.out.println("General Exception: " + e.getMessage());
        }
    }

    // Try-catch-finally
    public static void tryCatchFinally() {
        String resource = null;
        try {
            resource = "Some resource";
            int result = Integer.parseInt("not-a-number");
            System.out.println("Result: " + result);
        } catch (NumberFormatException e) {
            System.out.println("NumberFormatException: " + e.getMessage());
        } finally {
            // This always executes
            System.out.println("Finally block executed");
            // Resource cleanup would go here
            resource = null;
        }
    }

    // Custom exception
    static class InvalidAgeException extends Exception {
        public InvalidAgeException(String message) {
            super(message);
        }
    }

    // Method that throws exception
    public static void validateAge(int age) throws InvalidAgeException {
        if (age < 0 || age > 150) {
            throw new InvalidAgeException("Age must be between 0 and 150");
        }
        System.out.println("Age is valid: " + age);
    }

    // Demonstrating checked exceptions
    public static void checkedExceptionDemo() {
        try {
            validateAge(-5);
        } catch (InvalidAgeException e) {
            System.out.println("Custom exception caught: " + e.getMessage());
        }

        try {
            validateAge(25);
        } catch (InvalidAgeException e) {
            System.out.println("This won't print");
        }
    }

    public static void main(String[] args) {
        System.out.println("=== Exception Handling Demo ===\n");

        System.out.println("1. Basic try-catch:");
        basicTryCatch();

        System.out.println("\n2. Multiple catch blocks:");
        multipleCatch();

        System.out.println("\n3. Try-catch-finally:");
        tryCatchFinally();

        System.out.println("\n4. Custom exceptions:");
        checkedExceptionDemo();

        System.out.println("\nDemo completed!");
    }
}

// Usage in main method above
```

## 10. Collections Framework

```java
import java.util.*;

public class CollectionsDemo {

    public static void main(String[] args) {
        System.out.println("=== Collections Framework ===\n");

        // List (ArrayList)
        List<String> names = new ArrayList<>();
        names.add("Alice");
        names.add("Bob");
        names.add("Charlie");
        names.add(1, "Brian");  // Insert at index

        System.out.println("ArrayList: " + names);
        System.out.println("First element: " + names.get(0));
        System.out.println("Contains Bob: " + names.contains("Bob"));

        // Set (HashSet - no duplicates)
        Set<String> uniqueNames = new HashSet<>();
        uniqueNames.add("Alice");
        uniqueNames.add("Bob");
        uniqueNames.add("Alice");  // Duplicate, won't be added
        uniqueNames.add("Diana");

        System.out.println("HashSet: " + uniqueNames);
        System.out.println("Size: " + uniqueNames.size());

        // Map (HashMap)
        Map<String, Integer> ages = new HashMap<>();
        ages.put("Alice", 25);
        ages.put("Bob", 30);
        ages.put("Charlie", 35);

        System.out.println("HashMap: " + ages);
        System.out.println("Alice's age: " + ages.get("Alice"));
        System.out.println("Contains key 'Bob': " + ages.containsKey("Bob"));
        System.out.println("All keys: " + ages.keySet());
        System.out.println("All values: " + ages.values());

        // Iterating through collections
        System.out.println("\nIterating through collections:");

        System.out.println("List iteration:");
        for (String name : names) {
            System.out.print(name + " ");
        }
        System.out.println();

        System.out.println("Set iteration:");
        for (String name : uniqueNames) {
            System.out.print(name + " ");
        }
        System.out.println();

        System.out.println("Map iteration (entries):");
        for (Map.Entry<String, Integer> entry : ages.entrySet()) {
            System.out.println(entry.getKey() + ": " + entry.getValue());
        }

        // Sorting collections
        List<String> sortedNames = new ArrayList<>(names);
        Collections.sort(sortedNames);
        System.out.println("Sorted names: " + sortedNames);

        List<String> reverseSorted = new ArrayList<>(names);
        Collections.sort(reverseSorted, Collections.reverseOrder());
        System.out.println("Reverse sorted: " + reverseSorted);

        // Converting between collection types
        Set<String> nameSet = new HashSet<>(names);
        List<String> nameList = new ArrayList<>(uniqueNames);

        System.out.println("List to Set: " + nameSet);
        System.out.println("Set to List: " + nameList);
    }
}
```

---

## 🔧 Quick Reference

**Access Modifiers:**
- `public` - Visible everywhere
- `protected` - Visible in package and subclasses
- `private` - Visible only in same class
- `(default)` - Visible in same package

**Data Types:**
- **Primitive**: `int`, `double`, `boolean`, `char`, `byte`, `short`, `long`, `float`
- **Reference**: `String`, arrays, objects

**Common Patterns:**
- **Singleton**: Private constructor, static instance method
- **Factory**: Static methods creating objects
- **Builder**: Fluent API for object construction

**Collections:**
- `List` - Ordered, allows duplicates
- `Set` - Unique elements, unordered
- `Map` - Key-value pairs
- `Queue` - FIFO structure
- `Stack` - LIFO structure

**Exception Types:**
- `RuntimeException` - Unchecked (e.g., NullPointerException)
- `Exception` - Checked (e.g., IOException)
- `Error` - Severe problems (e.g., OutOfMemoryError)

**JVM Memory Areas:**
- **Stack**: Method calls, local variables
- **Heap**: Objects, instance variables
- **Method Area**: Class metadata, static variables
- **PC Register**: Current instruction
- **Native Stack**: Native method calls
