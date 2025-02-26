---
id: printf-format-id
title: Printf
desc: 'Java printf for formatted output'
updated: 1740600000000
created: 1740600000000
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

# Java printf() Method

## Overview

The `printf()` method in Java allows for formatted output using format specifiers. It's available in both `System.out` and `PrintStream` classes. This method is inspired by the C language's printf function and provides powerful text formatting capabilities.

## Basic Syntax

```java
System.out.printf(format, arguments...);
```

Where:
- `format` is a string containing text and format specifiers
- `arguments` are the values to be formatted and inserted into the format string

## Format Specifiers

The general syntax for format specifiers is:
```
%[flags][width][.precision]conversion-character
```

### Common Conversion Characters

| Character | Description | Example |
|-----------|-------------|---------|
| `%d` | Integer (decimal) | `%d` → `123` |
| `%f` | Floating-point number | `%f` → `123.456000` |
| `%s` | String | `%s` → `Hello` |
| `%c` | Character | `%c` → `A` |
| `%b` | Boolean | `%b` → `true` |
| `%x` | Integer (hexadecimal) | `%x` → `7b` |
| `%o` | Integer (octal) | `%o` → `173` |
| `%e` | Scientific notation | `%e` → `1.234560e+02` |
| `%n` | Platform-specific line separator | `%n` → newline |
| `%%` | Literal percent sign | `%%` → `%` |

### Flags

| Flag | Description | Example |
|------|-------------|---------|
| `-` | Left-justify | `%-10s` → `"Hello     "` |
| `+` | Include sign | `%+d` → `+123` |
| `0` | Zero padding | `%05d` → `00123` |
| `,` | Group separator | `%,d` → `1,234,567` |
| `(` | Negative in parentheses | `%(d` → `(123)` for negative values |
| ` ` (space) | Space before positive numbers | `% d` → ` 123` |

### Width and Precision

- Width: Minimum number of characters to output
  ```java
  System.out.printf("%10s", "Hello"); // "     Hello"
  ```

- Precision: For floating point, it controls decimal places
  ```java
  System.out.printf("%.2f", 123.456789); // "123.46"
  ```

## Examples

### Basic Examples

```java
int age = 30;
String name = "John";
double height = 1.75;

System.out.printf("Name: %s, Age: %d, Height: %.2f meters%n", name, age, height);
// Output: Name: John, Age: 30, Height: 1.75 meters
```

### Formatting Numbers

```java
System.out.printf("Integer: %d%n", 1234);
System.out.printf("With commas: %,d%n", 1234567);
System.out.printf("Leading zeros: %010d%n", 1234);
System.out.printf("Negative with parentheses: %(d%n", -1234);
```

### Formatting Strings

```java
System.out.printf("Right-aligned: %20s%n", "Hello");  // "               Hello"
System.out.printf("Left-aligned: %-20s%n", "Hello");  // "Hello               "
```

### Formatting Dates

```java
import java.time.LocalDate;

LocalDate today = LocalDate.now();
System.out.printf("Date: %tF%n", today);  // ISO-formatted date (yyyy-MM-dd)
System.out.printf("Date: %tB %te, %tY%n", today, today, today);  // Month day, year
```

## String.format

The same formatting can be applied to create formatted strings without printing:

```java
String formatted = String.format("Name: %s, Age: %d", "John", 30);
```

## Common Use Cases

### Tables

```java
System.out.printf("%-15s %-10s %10s%n", "Product", "Quantity", "Price");
System.out.printf("%-15s %-10d %10.2f%n", "Apple", 5, 0.99);
System.out.printf("%-15s %-10d %10.2f%n", "Orange", 10, 1.49);
System.out.printf("%-15s %-10d %10.2f%n", "Banana", 8, 0.59);

// Output:
// Product         Quantity        Price
// Apple           5                 0.99
// Orange          10                1.49
// Banana          8                 0.59
```

### Money Formatting

```java
double money = 1234.56;
System.out.printf("Amount: $%,.2f%n", money);  // Amount: $1,234.56
```

## Best Practices

> Choose appropriate format specifiers for your data types

> Use `%n` instead of `\n` for platform independence

> Consider creating format strings as constants for reuse

> For complex formatting needs, consider using `java.text.DecimalFormat` or `java.text.NumberFormat`

## Related Links

- [[java.string.format-specifiers]]
- [[java.text.decimal-format]]
- [[java.io.scanner]]
