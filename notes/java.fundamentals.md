---
id: 5z0mquc9f3uofi0tai3hx7i
title: Fundamentals
desc: ''
updated: 1740595925057
created: 1739571858911
---

<!--#region styles-->
<style>
    * {
        font-size: 18px;
    }
    h1 {
        color: red;
        font-weight: bold;
        border-bottom: 2px solid red;
        font-family: 'Algerian';
        text-align: center;
        font-size: 2em;
    }
    h2 {
        color: crimson;
        font-weight: bold;
        font-family: 'Algerian';
        border-bottom: 2px solid crimson;
        font-size: 1.5em;
    }
    h3 {
        color: rgb(255, 0, 127);
        font-weight: bold;
        text-decoration: underline;
        font-size: 1.2em;
        font-size: 1.2em;
    }
    h4 {
        color: rgb(0, 255, 255);
        font-weight: bold;
        text-decoration: underline;
        font-size: 1em;
    }
    h5 {
        color: darkblue;
        font-weight: bold;
        font-style: italic;
        font-size: 0.9em;
    }
    code {
        font-family: 'Cascadia Code';
        border: 1px solid #282a36;
        border-radius: 4px;
        padding: 1px 4px;
    }
    pre {
        font-family: 'Cascadia Code';
        border: 1px solid #282a36;
        border-radius: 4px;
        padding: 1px 4px;
    }
    p {
        font-style: 'Cascadia Code';
        color: white;
    }
    li {
        margin-bottom: 10px;
        font-style: italic;
        font-weight: bold;
        color: orange;
    }
    ul {
        margin-bottom: 10px;
        font-style: italic;
        font-weight: bold;
        color: orange;
    }
    b {
        font-weight: bold;
        color: rgb(255, 0, 0);
    }
    u {
        text-decoration: underline;
        font-weight: bold;
        font-style: italic;
    }
    a {
        color: #98c379;
        text-decoration: none;
    }
    a:hover {
        text-decoration: underline;
    }
    i {
        font-style: italic;
        color: yellow;
    }
    blockquote {
        background: rgba(255, 0, 127, 0.1); /* Light pink background */
        border-left: 5px solid rgb(255, 0, 127); /* Bold pink left border */
        padding: 10px 15px;
        margin: 10px 0;
        font-style: italic;
        font-weight: bold;
        color: white;
    }
</style>
<!--#endregion-->

# Java Fundamentals

## Definitions

### String Concatenation

String concatenation is the operation of joining two or more strings together. In Java, this is performed using the `+` operator between string variables or literals.

```java
String firstName = "John";
String lastName = "Doe";
String fullName = firstName + " " + lastName; // "John Doe"
```

## Syntax Examples

### Scanner Object

```java
// Import the Scanner class from java.util package
import java.util.Scanner;

// Create a Scanner object
Scanner scanner = new Scanner(System.in);

// Get user input
String name = scanner.nextLine();
int age = scanner.nextInt();
boolean isStudent = scanner.nextBoolean();

// Always close the scanner when done
scanner.close();
```

### Random Object

```java
// Import the Random class
import java.util.Random;

// Create a Random object
Random random = new Random();

// Generate random values
int randomInt = random.nextInt(100); // 0-99
double randomDouble = random.nextDouble(); // 0.0-1.0
```

## Topic References

### Data Types

-   [[java.core_concepts.data_types.primitive]]
-   [[java.core_concepts.data_types.reference]]

### Input/Output

-   [[java.io.scanner]] - Scanner object and methods
-   [[java.io.printf]] - Output formatting
-   [[java.string.format-specifiers]] - Format specifiers: %[flags][width][.precision][format-specifiers]

### Operators

-   [[java.core_concepts.operators.assignment]] - Assignment operators
-   [[java.core_concepts.operators.augmented-assignment]] - Augmented assignment operators
-   [[java.core_concepts.operators.increment-decrement]] - Increment and decrement operators
-   [[java.core_concepts.operators.precedence]] - PEMDAS and operator precedence

### Control Flow

-   [[java.core_concepts.conditionals.if-statements]] - If statements

### Utility Classes

-   [[java.util.random]] - Random number generation
-   [[java.math]] - Math methods (.pow(), .abs(), .sqrt(), etc.)
-   [[java.string.methods]] - String methods including .isEmpty()

## Key Points

> To use the scanner object, it must be imported using the util package: `import java.util.Scanner`

> It's good practice to close the scanner after using it with `scanner.close()`

> When accepting strings after integers with Scanner, the newline character can cause issues. Fix by adding an extra `scanner.nextLine()` after reading integers.

> PI and E are static properties (fields) of the Math class: `Math.PI` and `Math.E`

> In Java classes, members consist of methods and fields (both represent the class's functionality and state)

> TIP: To use superscript in VSCode, use Numlock + Alt + 0178 for ² or Alt + 0179 for ³

> Format specifiers in printf/String.format use % as placeholders before the variables they represent

## Related Resources

-   [Oracle Java Documentation](https://docs.oracle.com/en/java/javase/17/docs/api/index.html)
-   [Java Scanner Class Documentation](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/Scanner.html)
-   [Java Math Class Documentation](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/Math.html)
