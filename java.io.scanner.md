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

# Java Scanner Class

## Overview

The Scanner class in Java is used to read input data from various sources like input streams, files, or strings. It is part of the `java.util` package.

## Basic Usage

```java
// Import the Scanner class
import java.util.Scanner;

// Create a Scanner object for reading from standard input
Scanner scanner = new Scanner(System.in);

// Use scanner to read input
// ...

// Close the scanner when done
scanner.close();
```

## Common Methods

### .nextLine()

```java
String fullLine = scanner.nextLine();
```

-   Reads a complete line of input (including spaces)
-   Returns the input as a String
-   Advances the scanner past the current line

### .next()

```java
String nextWord = scanner.next();
```

-   Reads the next token (word) up to a whitespace
-   Returns the token as a String
-   Useful for reading single words

### .nextInt()

```java
int number = scanner.nextInt();
```

-   Reads the next token as an integer
-   Throws InputMismatchException if the next token is not a valid integer
-   **Note:** Leaves the newline character in the input buffer

### .nextBoolean()

```java
boolean flag = scanner.nextBoolean();
```

-   Reads the next token as a boolean value
-   Returns true for "true" and false for "false" (case-insensitive)
-   Throws InputMismatchException if the next token is not a valid boolean

## Common Issues and Solutions

### The Newline Character Problem

When mixing `nextInt()` or other primitive reading methods with `nextLine()`, you may encounter an issue where `nextLine()` reads the leftover newline character:

```java
// Problematic code
int age = scanner.nextInt();
System.out.print("Enter your name: ");
String name = scanner.nextLine(); // This will immediately return an empty string!
```

Solution:

```java
int age = scanner.nextInt();
scanner.nextLine(); // Consume the leftover newline
System.out.print("Enter your name: ");
String name = scanner.nextLine(); // Now this works correctly
```

## Best Practices

> Always close the Scanner when done to prevent resource leaks

> Import the Scanner class explicitly with `import java.util.Scanner;`

> Use `scanner.hasNext()` or similar methods to check if more input is available

> When reading mixed types of data, be aware of the newline character issue

## Example: Complete Input Program

```java
import java.util.Scanner;

public class UserInputExample {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter your name: ");
        String name = scanner.nextLine();

        System.out.print("Enter your age: ");
        int age = scanner.nextInt();
        scanner.nextLine(); // Consume newline

        System.out.print("Enter your city: ");
        String city = scanner.nextLine();

        System.out.print("Are you a student? (true/false): ");
        boolean isStudent = scanner.nextBoolean();

        System.out.println("\nUser Information:");
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("City: " + city);
        System.out.println("Student: " + isStudent);

        scanner.close();
    }
}
```

## Related Links

-   [[java.io.printf]]
-   [[java.data-types.primitive]]
-   [[java.exceptions]]
