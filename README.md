# The Sky Programming Language

## Introduction

Sky combines the safety and solidness of languages like C# and Kotlin with the flexibility and simplicity of Python and JavaScript.

Sky is built for for IDEs and readability. Sky believes that we have moved past writing code in dumb editors, and have moved into a new era of writing code, where adding curly braces does not effect writing speed.

Unlike many other programming languages, even beloved high level languages such as Python, sky doesn't try to reduce in what is typed, or give the language a more english like syntax, but it strives for clear visual separation between parts of code. The goal is for any programmer slightly familiar with the language to understand the flow of any program at a glance, no matter how complex the code.

Sky is a multi-paradigm programming language, incorporating functional elements along with object oriented elements.

Every variable, parameter, result, element is an object. Every object has a type. Types inherit from each other in complex relationships, and every type inherits from `Object`. See more about this at the section on [classes and objects](#classes--objects).

Every action done in the code in one way or another is a function or uses a function. All if statements and loops are actually function in disguise, and you can even replace any normal input (`()`) with curly braces (`{}`) that represent a lambda function that returns the same types, or even just place replace it with a function. See more about this at the section on [functions](#functions).

## Hello World

Here is a simple program that prints "Hello, world!":

```kotlin
print("Hello, world!")
```

`print()` and `print()` functions print their arguments to standard output.

Simple, ins't it?

Heres another approach:

```kotlin
func main() {
    print("Hello, world!")
}
```

In this approach we create a function using the keyword `func`. See more about this at the section on [functions](#functions). The `main()` function is where your program starts from. The body of a function is written within curly braces `{}`. We write code within the body of the function.

Here's another approach:

```kotlin
class Program {
    public static func main(args: Array<String>) {
        print("Hello, world!")
    }
}
```

Here we create a class, that contains a public static function called `main()`. See more about this at the section on [classes and objects](#classes--objects).

## Variables & Basic Types

## Strings & Interpolation

### Strings

### Char Arrays

### Interpolation

We have three ways to interpolate strings in sky.

```kotlin
$"Hello! {user}"
```

In this first technique, we place a dollar sign (`$`) before the string to imply it is a string we want to interpolate. Any text within curly braces (`{}`) will be interpreted as code. This technique of string interpolation is helpful when you have a large amount of code or variables you want to inject into the string and don't want to waste space with lots of dollar signs.

```kotlin
"Hello! ${user}"
```

In this second, we place the dollar sign before the code we want to inject. This allows us to include curly braces in the string without having to escape them.

```kotlin
"Hello! $user"
```

In this third variant, we place the dollar sign before the name of the variable we want to inject. This allows our string to stay incredibly readable, but doesn't allow us to inject code, only variables.

### Escape Characters

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
if isComplete then (runAnimation = false) else (count++);
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
    print(number * number);
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
func printWithExclamation(text: String) {
    print("${text}!");
}

func main() {
    printWithExclamation("Hello, world");
}
```

In this example we use string interpolation.See more about this at the section on functions [strings and interpolation](#strings--interpolation).

Use the `return` keyword to exit or return something from a function.

```kotlin
func sum(x: Int, y: Int): Int {
    return x + y;
}

func divide(x: Int, y:Int) {
    return x / y;
}

func main() {
    print(sum(1, 2));
}
```

### Recursion

### Advanced Functions

Every function accepts and returns an anonymous object `{a: Type, b:Type ...}`, meaning that you can have multiple inputs and outputs. This won't cause any confusion, though, because the object you receive from the outputs will have to either fit those standards or the program won't compile. same thing if you have two different return statements in a function where the types don't match up. this eliminates the need for "out" like in C#.

```kotlin
func something(a: Type, b: Type) {
    return {a, b}
}
```

```kotlin
// Set an instance of that anonymous object to a value:
val value = something(a, b);
```

Or, set two separate values to the values the output object has.

```kotlin
{ val a, val b } = something(a, b);
// You can also can input with the same anonymous object type instead of two separate values:
something(value); // Works!
```

This is called object deconstruction, where you deconstruct an object to its contained values. Object deconstruction is written with curly braces (`{}`), with all of the values you want inside.

Also unlike in kotlin function return types can be assumed and don't have to be explicitly stated.

Anonymous Objects and Object deconstruction are further discussed in the next part (Classes and objects).

## Classes & Objects

### Objects

### Object Comparison

### Classes

### Structs

Structs are the immutable version of classes. Instead of being passed by reference (Where a pointer to the object gets moved between variables, meaning they both reference the same object) the object is passed by value, meaning that the object gets coppied every time you do an operation on it.

```kotlin
struct Something {
    // Some code...
}
```

### Data Classes & Structs

Data classes and structs are special classes and structs that are made to pass around information, and nothing else. They do not support the addition of any functions or private feilds, but auto generate `toString`

### Abstract & Interfaces

interfaces are

## Null Safety

## Async

In many programming circles, it is considered best practice to go 'async all the way', meaning if you write any async code, you should write the rest of your code in a way that will accommodate for that asynchronous code when needed.

## Technical Info

Sky code files use the .sky file ending.

## Example Project

```kotlin
// Example code goes here...
```
