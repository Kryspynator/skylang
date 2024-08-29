# The Sky Programming Language

## Introduction

Sky combines the safety and solidity and safety of languages like kotlin with the simplicity and flexibility of languages like javascript. In a way, you can think of it at another attempt to create typescript.

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

### Variables

Here is how you create a basic variable in sky.

```kotlin
var num = 3;
```

In this example, you create a variable called `num`. You define it to hold the value of `3`, which is an integer number. In sky, every variable has a type that cannot be changed from it's creation. Here, we imply that the number is an `Int32` or simply `Integer`. In sky, you can also explicitly declare the variable type. You can learn more about classes and objects

```kotlin
var num: Integer = 3;
```

It is also possible to declare a variable, and only set it to a value later.

```kotlin
var num: Integer;

num = 3;
```

### Values / Constants

Just like variables, values (or you can think of them as 'constant variables') can be set to different values. Unlike variables, they cannot be changed. In sky, this is made easy as constant values are put on the same level as other variables and are equally easy to type (unlike langues like C#). The reason behind this, is to encourage the use of the concept of immutability, where values of variables are not changed, just modified into a different variable. This mindset tends to reduce errors where two parts of the code accidentally modify the same value.

```kotlin
val implicitNum = 3; // Works! ✔️

val explicitNum: Integer = 3; // Works! ✔️

val unsetNum: Integer; unsetNum = 3; // Doesn't work! ✖️
```

### Basic Types

Here are some basic types included in the standard library. Strings will be discussed more in [string & interpolation](#strings--interpolation). To understand more about these types, learn about more types, and how to create more types, go to [classes & objects](#classes--objects)

| Numbers              |                                                                                                                      |
| -------------------- | -------------------------------------------------------------------------------------------------------------------- |
| **_Integer_**        |                                                                                                                      |
| `Integer`            | An integer (whole number) value that dynamically switches between Int32 and Int64, and is the default type of number |
| `Int32`              | An integer (whole number) value that takes up 32 bits (4 bytes)                                                      |
| `Int64`              | An integer (whole number) value that takes up 64 bits (8 bytes)                                                      |
| `Int16`              | An integer (whole number) value that takes up 16 bits (2 bytes)                                                      |
| `Int8`               | An integer (whole number) value that takes up 8 bits (1 byte)                                                        |
| **_Floating point_** | _A floating point decimal value_                                                                                     |
| `Float`              | An value that dynamically switches between Float32 and Float64 and is the default value of a decimal number          |
| `Float32`            | An real (decimal number) value that takes up 32 bits (4 bytes)                                                       |
| `Float64`            | An real (decimal number) value that takes up 32 bits (8 bytes)                                                       |

#### Writing Numbers

Here's how you can write numbers in sky

|                      |                                                                     |
| -------------------- | ------------------------------------------------------------------- |
| `var x = 123;`       | a number in base 10 (will default to the type of 'Int32')           |
| `var x = 0b1111011;` | a number in binary (will default to the type of 'Int32')            |
| `var x = 0x7B;`      | a number in binary (will default to the type of 'Int32')            |
| `var x = 0.1;`       | a decimal number in base 10 (will default to the type of 'Float64') |

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

### Basic Data Types

#### Array

#### Immutable Array

#### Map

#### Immutable Map

### Collections

#### List

#### Immutable List

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

In this example, we return a value from the encasing function instead of the the `then` case. This is called a [root return](#root-return)

### Loops

#### This is a `foreach` loop

It iterates over every single item in an [`Iterable`](#iterable) object. The code within the braces will called once for every object within the iterable object.

In this example, we loop over a collection called `users`. We declare that the object that is currently being accessed in the loop as `user`.

```kotlin
foreach (user in users) {
    // Do Something...
}
```

Here we loop over the same collection, but this time we loop over the objects with the index. We use [object destructuring](#object-destructuring) to extract two different objects, one representing the users, and one representing the index.

```kotlin
foreach ({ user, index } in users.withIndex()) {
    // Do Something...
}
```

In maps, when we loop over the map, we get one `KeyValuePair` object. Usually, we'll use [object destructuring](#object-destructuring) here as well to get easy access to both the key and the value.

```kotlin
foreach ({ key, value } in myMap) {
    // Do Something...
}
```

If you want to loop over a range of numbers, you can create a new [`Range` object](#range) and place your lower and upper bounds. If you don't put a lower bound, it will be 0 by default.

```kotlin
foreach (number in new Range(1, 5)) {
    print(number * number);
}
```

```kotlin
foreach (number in new Range(users.size)) {
    // Do something...
}
```

#### This is a `while` loop

It continues to run the code within it's scope while the condition is met (the input at the top is `True`)

```kotlin
while (count < foo.length) {
    // Do something...
}
```

#### This is a `do while` loop

It runs the code within it's scope, and them checks if the condition is still met (the input at the top is `True`)

```kotlin
do {
    // Do something...
} while (count < foo.length)
```

#### This is a `while do` loop

It runs the code within the while statement, and depending on what it returns, it runs the do statement. If the that runs within.

```kotlin
while {
    // Do something...
    return (count < foo.length);
} do {
    // Do something...
}
```

### Root Return

sometimes you exist inside a lambda function

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

#### Returning Multiple Values

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

This is called [object destructuring](#object-destructuring), where you deconstruct an object to its contained values. Object deconstruction is written with curly braces (`{}`), with all of the values you want inside.

Also unlike in kotlin function return types can be assumed and don't have to be explicitly stated.

Anonymous Objects and Object deconstruction are further discussed in the next part (Classes and objects).

#### Partial Functions

```kotlin
func something(x: Int, y: Int) {
    ...
}

val partialSomething = something.partial({x: 3});
```

#### Higher order functions

Functions can also receive other functions as an input, and activate them.

## Classes & Objects

### Objects

Objects are packages for information. Instead of storing data in multiple variables, you can package it into an object and store it in one. Objects are used to store data and actions that are related and should move and change together in the code.

### Object Destructuring

### Object Comparison

In sky, there are number of boolean operators that you can use on objects.

| Operators           | Description                                                                                                             |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| `==` Equals         | Returns true if the objects are equal using the `equals` function                                                       |
| `===` Strict Equals | Returns true if the objects' pointers are equal                                                                         |
| `<=` Lesser Equals  | Returns true if the objects are lesser or equal using the `compare` function inherited from the `Comparable` interface  |
| `<` Lesser than     | Returns true if the objects are lesser using the `compare` function inherited from the `Comparable` interface           |
| `>=` Greater Equals | Returns true if the objects are greater or equal using the `compare` function inherited from the `Comparable` interface |
| `>` Greater than    | Returns true if the objects are greater using the `compare` function inherited from the `Comparable` interface          |

```kotlin
if("Hello" == "Hello") // Returns true
```

```kotlin
if("Hello" === "Hello") // Returns false, because the pointers point to different strings.
```

### Classes

Classes are templates for objects. You can create instances of classes, and the type of that object will be the name of the class. If the variable is the type of class, you can access the objects public properties.

```kotlin
var worker = new Employee("Bob", "Programmer");
```

Here we just create a new employee. Here is the template for an employee.

```kotlin
class Employee(val name: String, var job: String) {
    func doJob(hours: Integer) {
        print()
    }
}
```

In the example above, we created a new employee who's name is "Bob" and job is "Programmer".

#### Extending classes

```kotlin
class Manager(name: String) extends Employee(name,"Manager") {

}
```

### Structs

Structs are the immutable version of classes. Instead of being passed by reference (Where a pointer to the object gets moved between variables, meaning they both reference the same object) the object is passed by value, meaning that the object gets copied every time you do an operation on it.

```kotlin
struct Something {
    // Some code...
}
```

### Member Modifiers

#### `static`

The static modifier modifies the member to be "static" or unchanged by different instances of the class. In a sense, it creates global variables and functions that are tied to a certain class. This is a very powerful, but also dangerous property. It can take up unneeded amounts of memory and create unmanageable code. In general, in programming we want to keep "state", or the idea that we save information and that information influences the codes actions, to a minimum.

#### Access Modifiers

Behind the scenes, "get" and "set" functions are created and called for every single one of the fields.

```kotlin
// For methods...

public var fpo;         // Public is the default access modifier. Allows anyone to access the member.
internal var bar;       // Internal only allows code from the same package to access the member
protected var alice;    // Protected only allows code from the class and classes that inherit to access the member
private var bob;        // Private only allows code from the class to access the member

// For fields...

getOnly var charlie; // Sets the "get" to public, and the "set" to protected
setOnly var dotan; // Sets the "set" to public, and the "get" to protected

// You can set all of this manually for fields get/set methods as well
var temp: Integer {
    internal get() {
        return temp;
    }
    private set(temp: Integer) {
        this.temp = temp;
    }
}
```

#### `val` & `var`

### Sugar Syntaxes

#### Fields

Behind the scenes, "get" and "set" functions are created and called for every single one of the fields, depending on their access modifier. This allows us to limit access for them even further.

```kotlin
var port: Integer(this > 0 & this < 3000);

// Translates too...

var port: Integer {
    get() {
        return port;
    }
    set(port: Integer) {
        if(port > 0 & port < 3000) {
            return true;
        }
        return false;
    }
}
```

### Data Classes & Structs

Data classes and structs are special classes and structs that are made to pass around information, and nothing else. They do not support the addition of private members, as those accessed from outside of that class.

### Abstract & Interfaces

There are no abstract classes in sky, only interfaces. Interfaces are significantly more similar to typescript interfaces than ones in C#.

Interfaces can be seen as templates for classes, in the same way as classes are templates for objects, but interfaces can also be used as an implicit type for an object, where a class is more explicit.

```kotlin
interface Animal {
    readonly val genome: Gene[];
    readonly var Name: String;
    var isAlive: Boolean;
}
```

```kotlin
interface Mammal extends Animal {
    func makeMilk(water: Water) => Milk;
}
```

#### Iterable

`Iterable` is an interface that exists by default.

#### Collection

## Null Safety

## Async

In many programming circles, it is considered best practice to go 'async all the way', meaning if you write any async code, you should write the rest of your code in a way that will accommodate for that asynchronous code when needed.

## Packages

In sky, packages are declared using the `package` keyword. At the top of the

## Program Entry Point

There are two program entry points. Either a main function, or a script. In a script, you specify the file you want to run, and any code written in the top level scope will be run. In larger programs, you'll use a main function and the compiler will automatically find it and run it to start the program. If there are multiple main functions, you'll have to specify which one will be run.

## Style Guide

## Technical Information

Sky code files use the .sky file ending.

## Standard Packages

The standard packages are pre-made packages that anyone can use and import to make their coding faster and more efficient.

You can think of the all of the basic types as types that exist in the standard library that is imported by default. These types do not have a real class or struct implementation anywhere.

### Standard Collections & Iterables

> #### `Range`
>
> an iterable that represents a range of numbers.
>
> Constructors:
>
> ```kotlin
> constructor(endExclusive: Integer)
> ```
>
> `endExclusive` is an integer number that represents the end of the range. The range starts at 0 and ends at the end. The range goes up by 1 every time
>
> ```kotlin
> constructor(
>    startInclusive: Integer,
>    endExclusive: Integer
> )
> ```
>
> `startInclusive` is an integer number that represents the start of the range. `endExclusive` is an integer number that represents the end of the range. The range starts at 0 and ends at the end.
>
> ```kotlin
> constructor(
>    startInclusive: Integer,
>    endExclusive: Integer,
>    step: Integer
> )
> ```
>
> `startInclusive` is an integer number that represents the start of the range. `endExclusive` is an integer number that represents the end of the range. `step` is an integer number that represents how much to jump each time until reaching the end number. The range starts at `startInclusive` and ends before `endExclusive`.
