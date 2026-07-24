# Conditional Statements

## Flow of Control

**Flow of control** refers to the order in which individual elements, instructions, or function calls are executed within a program.

By default, a Java program executes sequentially from top to bottom, following the exact line-by-line sequence in which the code is written.

However, Java provides **control flow statements** to break this default linear execution, enabling:
- decision-making (**Selection**),
- looping (**Iteration**),
- and jumping across code blocks (**Jumping**).

**Selection:** These statements allow your program to choose different execution paths based on the outcome of an expression or condition. These include `if`statements, `if-else` statements, `if-else-if` ladder, and `switch` statements.

**Iteration:** Loops tell the program to repeat a specific block of code as long as a particular condition remains `true`. These include `for` loops, enhanced `for` (`for-each`) loops, `while` loops, and `do-while` loops.

**Jumping:** Branching statements immediately transfer control to another part of your code without checking conditions directly. These include `break`, `continue`, and `return`.

## `if` statement

**Syntax:**

```java
if (expression) {
    // do something
}
```

The _expression_ must evaluate to a `boolean` value, i.e., either `true` or `false`. If the expression evaluates to `true`, the code block inside `if` executes, otherwise it is skipped.

```java
// if statements

int i = 5;

if (i == 5) { // true => so this block executes
    System.out.println("i is 5.");
}

if (i == 6) { // false => so this block does not excute
    System.out.println("i is 6.");
}
```

## `if-else` statement

**Syntax:**

```java
if (expression) {
    // do something
}
else {
    // do something
}
```

The _expression_ must evaluate to a `boolean` value, i.e., either `true` or `false`. If the expression evaluates to `true`, the code block inside `if` executes, otherwise the code block inside `else` executes.

> **Note:** If there is a single line of code in the code block, you can omit the curly braces (`{}`), but it is mandatory for multiple lines of codes in the code block. It's always a good practice to include the braces whether you have single or multiple lines of code.

```java
// if-else statements

int i = 6;

if (i == 5) { // false => so this block does not execute
    System.out.println("i is 5.");
}
else { // This block executes
    System.out.println("i is not 5.");
}

if (i > 5 && i < 10) { // true => so this block executes
    System.out.println("i is greater than 5 and less than 10");
}
else { // This block is skipped
    System.out.println("i is less than or equal to 5 OR i is greater than or equal to 10");
}

// check if i is odd or even

if (i % 2 == 0) { // true => so this block executes
    System.out.println("i is even.");
}
else { // this block is skipped
    System.out.println("i is odd.");
}
```

## Nested-if statements

You can also use _nested_-`if` statements, i.e.,`if` statement(s) inside an `if` statement to any level. Although it is not recommended to nest more than 3 levels for good readability. Each `if` may or may not have an `else` block.

```java
// Nested-if statements

int i = 8;

if (i > 5) {
    if (i < 10) {
        if (i == 7) {
            System.out.println("i is 7.");
        }
    }
    else {

    }
}
else {

}
```

## `if-else-if` ladder

**Syntax:**

```java
if (expression1) {

}
else if (expression2) {

}
...
...
else if (expressionN) {

}
else { // if required

}
```

In this, the code block will execute whose expression evaluates to `true` first. The `else` block (if there) is always at the end and it executes only when all the expression evaluated to `false`.

```java
// if-else-if ladder

int i = 8;

if (i == 5) { // false, check next condition
    System.out.println("i is 5.");
}
else if (i == 6) { // false, check next condition
    System.out.println("i is 6.");
}
else if (i == 7) { // false, check next condition
    System.out.println("i is 7.");
}
else if (i == 8) { // true, execute this block and exit ladder
    System.out.println("i is 8.");
}
else if (i == 9) {
    System.out.println("i is 9.");
}

int age = 50;

if (age > 80) { // false, check next condition
    System.out,println("You are very old.");
}
else if (age > 60) { // false, check next condition
    System.out,println("You are old.");
}
else if (age > 40) { // true, execute this and exit ladder
    System.out,println("You are becoming old.");
}
else if (age > 20) {
    System.out,println("You are young.");
}
else {
    System.out,println("You are a child");
}


if (age > 80) { // false, skip this block
    System.out,println("You are very old.");
}
if (age > 60) { // false, skip this block
    System.out,println("You are old.");
}
if (age > 40) { // true, execute this block
    System.out,println("You are becoming old.");
}
if (age > 20) { // true, execute this block and exit if-else
    System.out,println("You are young.");
}
else {
    System.out,println("You are a child");
}
```

## `switch` statements

This evaluates an expression and matches its result against multiple predefined `case` constants to execute specific code block.

It provides a clean, highly structured alternative to long `if-else-if` ladders when testing a single variable for equality against discrete values.

```java
// switch statements

int i = 3;

switch (i) {
    case 1:
        System.out.println("i is 1.");
        break;
    case 2:
        System.out.println("i is 2.");
        break;
    case 3: // value matched, execute this
        System.out.println("i is 3.");
        break; // exit switch
    default:
        System.out.println("i is greater than 3.");
        break;
}
```

**Components:**

- **The expression:** The variable or calculation inside the `switch()` parenthesis. Supported types include _primitives_ (`byte`, `short`, `char`, `int`), their corresponding _Wrapper classes_ (`Byte`, `Short`, `Character`, `Integer`), `String` (after **JDK 7**) objects, and `enum` types.
- **`case` constant:** The specific literal value to match against. It must be a _compile-time constant_ or _literal expression_ of the exact same type as the main switch variable. Variables or runtime parameters cannot be used as case values.
- **`break` statement:** A control flow terminator. When reached, it breaks out of the switch block entirely. If omitted, the execution continues directly into subsequent cases regardless of whether they match or not (known as **fall-through** behavior).
- **`default` block:** An optional catch-all block that executes if none of the provided case literals match the expression value.

> You can reorder or mix up the position of `case` labels and the `default` block. The compiler does not care about the physical order. Java first scans the entire switch block from top to bottom looking _only_ for an exact matching `case`. The `default` block is ignored during this initial phase, even if it is sitting at the very top. If no exact match is found, execution jumps straight to `default` block.

```java
/*
Once a entry point (case or default) is triggered, execution moves strictly downward until a break or the closing brace (}) is encountered.
*/

int value = 2;

switch (value) {
    case 1:
        System.out.println("One.");
        break;
    case 2: // match found, so execute this
        System.out.println("Two.");
        // Missing break!, so executes subsequent block
    case 3:
        System.out.println("Three.");
        break; // break found, exit switch
    default:
        System.out.println("Default.");
        break;
}

/* Output:
Two.
Three.
*/

value = 99;

switch (value) {
    default: // no match found, so execute this block
        System.out.println("Default");
        // Missing break!, so executes subsequent block
    case 1:
        System.out.println("One.");
        break; // break found, exit switch
    case 2:
        System.out.println("Two.");
        break;
}

/* Output:
Default
One.
*/
```

### Differences between `if-else-if` ladder and `switch` statement

| Feature | `switch` statement | `if-else-if` ladder |
|---|---|---|
| **Condition Types** | Evaluates a **single expression** against constant values. | Evaluates **arbitrary boolean conditions**. |
| **Data Types** | Limited to `int`, `char`, `byte`, `short`, `String`, and `enum`. | Works with **any data type** or object reference comparision. |
| **Underlying Mechanism** | Uses a **jump table** or **binary search** (`lookupswitch` / `tableswitch`). | Executes **sequential checks** line-by-line from top to bottom. |
| **Performance** | $\text{O}(1)$ **constant time** for large numbers of cases | $\text{O}(\text{N})$ **linear time** as performance degrades with more conditions. |
| **Readability** | Clean, tabular, and highly structured for discrete options. | Can become cluttered ("spaghetti code") with deep nesting. |

### Modern Switch Expressions (Java 14+)

This upgraded version **eliminates** the risk of accidental **fall-through** using arrow syntax (`->`) and allows the switch block to return a direct value.

```java
// Modern switch expression

String fruit = "Apple"

int price = switch (fruit) {
    case "Apple", "Pear" -> 3; // supports multiple values per line
    case "Mango" -> 5;
    default -> 0; // Exhaustive matching is required here
};

System.out.println(price); // prints 3

String mode = "dark";

String hexColor = switch (mode) {
    case "light" -> "#FFFFFF";
    case "dark" -> {
        System.out.println("Applying dark mode filter...");
        String color = "#000000";
        yield color; // Returns the value and exits the block
    }
    default -> throw new IllegalArgumentException("Unknown mode");
}
```

For complex, multi-line logic blocks inside a modern switch expression that needs to return a value, the block uses the `yield` keyword instead of `break`.

> You can also nest `switch` statements.