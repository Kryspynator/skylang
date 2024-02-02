# The Sky Programming Language

## Introduction

Sky combines the safety and solidness of languages like C# and Kotlin with the flexibility and simplicity of Python and JavaScript

Sky is built for for IDEs and readability. Unlike many other programming languages, it doesn't try to reduce in what is typed, or give the language a more english like syntax, but it strives for clear visual separation between parts of code. The goal is for any programmer slightly familiar with the language to understand the flow of any program at a glance.

Sky is a multi-paradigm programming languages, incorporating functional elements along with object oriented elements.

Every variable, parameter, result, element is an object. Every object has a type. Types inherit from each other in complex relationships, and every type inherits from "Object".

Every action done in the code in one way or another is a function or uses a function. All if statements and loops are actually function in disguise, and you can even replace any normal input () with {} that represent a lambda function that returns the same types.

## Hello World

Here is a simple program that prints "Hello, world!":

```kotlin
println("Hello, world!")
```

`println()` and `print()` functions print their arguments to standard output

Simple, ins't it?

Heres another approach:

```kotlin
func main() {
    println("Hello, world!")
}
```

In this approach we create a function using the keyword `func`.

The `main()` function is where your program starts from.

The body of a function is written within curly braces `{}`.

We write code within the body of the function.

Heres another approach:

```kotlin
class Program {
    static func main(args: Array<String>) {
        println("Hello, world!")
    }
}
```

## Variables & Basic Types

## Strings & Interpolation

## Data Types & Collections

## Control flow

### If Statements

Basic readable if statements:

```kotlin
if (something) {
    // Do Something...
} else {
    // Do Something...
}
```

Simple one line if statements:

```kotlin
if (isComplete) then (runAnimation = false) else (count++);
```

```kotlin
val value = if (input == 0) then (1) else (-1);
```

```kotlin
return if (input > 0) then (1) else (-1);
```

Turning any value input into a anonymous function using braces:

```kotlin
if {
    // Do Something...
    return (something); // Using a anonymous function that returns a bool!
} then {
    // Do Something...
    return (something); // Return a value just like one line if statements/
} else {
    // Do Something...
    root.return (something);
    // Return a value from the containing function instead of from the 'if' itself.
}
```

### When statements

Instead of switch case, we have when else:

```kotlin
when (numberText) {
    ("one") => (/* Do Something... */)
    ("two") => {
        // Do Something...
        // Do Multiple Things...
    }
    (numberText.length > 3) => {
        // Do Something...
        return (something);
    }
    // Default statement
    else -> (root.return (something))
}
```

### Loops

foreach

```kotlin
foreach (user in users) {
    // Do Something...
}
```

index and value in array and lists

```kotlin
foreach ({ user, index } in users) {
    // Do Something...
}
```

key and value in maps

```kotlin
foreach ({ key, value } in myMap) {
    // Do Something...
}
```

ranges

```kotlin
foreach (number in Range(1, 5)) {
    println(number * number);
}
```

while

```kotlin
while (count < foo.length) {
    // Do something
}
```

do while

```kotlin
do {
    // Do something
} while (count < foo.length)
```

while do

```kotlin
while {
    // Do something...
    return (count < foo.length);
} do {
    // Do something...
}
```

## Functions

You declare functions in sky using the `func` keyword.

```kotlin
func hello() {
    println("Hello, world!");
}

func main() {
    hello();
}
```

Use the `return` keyword to exit or return something from a function.

```kotlin
func sum(x: Int, y: Int): Int {
    return x + y;
}

func divide(x: Int, y:Int) {
    return x / y;
}

func main() {
    println(sum(1, 2));
}
```

Every function accepts and returns an anonymous object `{a: Type, b:Type ...}`, meaning that you can have multiple inputs and outputs. This won't cause any confusion, though, because the object you receive from the outputs will have to either fit those standards or the program won't compile. same thing if you have two different return statements in a function where the types don't match up. this eliminates the need for "out" like in C#.

```kotlin
func something(a: Type, b: Type) {
    return {a, b}
}

// Set an instance of that anonymous object to a value:
val value = something(a, b);
// Or, set two separate values to the values the anonymous object has:
{ val a, val b } = something(a, b);
// You can also can input with the same anonymous object type instead of two separate values:
something(value); // Works!
```

Also unlike in kotlin function return types can be assumed and don't have to be explicitly stated.

## Classes & Objects

## Null Safety

## Async

## Technical Info

Sky code files use the .sky file ending.

## Example Project

```kotlin
// Example code goes here...
```
