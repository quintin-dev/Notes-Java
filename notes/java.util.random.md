---
id: random-util-id
title: Random
desc: 'Java Random utility class for generating random values'
updated: 1740595879005
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

# Java Random Class

## Overview

The `Random` class in Java provides methods for generating pseudo-random numbers of various types. It's part of the `java.util` package and is used when you need to introduce randomness into your applications.

## Basic Usage

```java
// Import the Random class
import java.util.Random;

// Create a Random object
Random random = new Random();

// Use the random object to generate random values
```

## Common Methods

### .nextInt()

```java
// Generate a random integer (can be positive or negative)
int randomNumber = random.nextInt();

// Generate a random integer from 0 (inclusive) to bound (exclusive)
int randomInRange = random.nextInt(10); // 0-9
```

### .nextInt() with Range

To generate a random integer within a specific range (min to max):

```java
// Generate random number between min (inclusive) and max (inclusive)
int min = 5;
int max = 10;
int randomInRange = random.nextInt(max - min + 1) + min; // 5-10
```

### .nextDouble()

```java
// Generate a random double between 0.0 (inclusive) and 1.0 (exclusive)
double randomDouble = random.nextDouble();

// Generate a random double within a specific range
double min = 5.0;
double max = 10.0;
double randomDoubleInRange = min + (max - min) * random.nextDouble();
```

### .nextBoolean()

```java
// Generate a random boolean (true or false)
boolean randomBoolean = random.nextBoolean();
```

### .nextLong()

```java
// Generate a random long value (can be positive or negative)
long randomLong = random.nextLong();
```

### .nextFloat()

```java
// Generate a random float value between 0.0 (inclusive) and 1.0 (exclusive)
float randomFloat = random.nextFloat();
```

## Seeding the Random Number Generator

You can initialize a Random object with a specific seed value to produce a repeatable sequence of random numbers, which is useful for testing:

```java
// Create a Random object with a specific seed
long seed = 123456;
Random random = new Random(seed);

// This will generate the same sequence of numbers every time
// when using the same seed
```

## Common Use Cases

### Random Element from Array

```java
String[] options = {"Apple", "Banana", "Cherry", "Date"};
String randomFruit = options[random.nextInt(options.length)];
```

### Simulating Dice Roll

```java
// Simulate rolling a six-sided die (1-6)
int dieRoll = random.nextInt(6) + 1;
```

### Generating Random Strings

```java
public static String generateRandomString(int length) {
    String characters = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789";
    StringBuilder result = new StringBuilder(length);
    Random random = new Random();

    for (int i = 0; i < length; i++) {
        result.append(characters.charAt(random.nextInt(characters.length())));
    }

    return result.toString();
}

// Generate a random string of length 10
String randomString = generateRandomString(10);
```

## Best Practices

> For cryptographic purposes, use `SecureRandom` instead of `Random`

> When seeding is not needed for security, create one Random instance and reuse it

> For simple random operations, consider using `Math.random()` which returns a double between 0.0 and 1.0

## Related Links

-   [[java.math]]
-   [[java.security.secure-random]]
