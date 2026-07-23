# Variables and Data Types

## Variable

When you store something in the computer's memory, the name of the memory location is called a **variable**.

A **Variable** is a container that stores data values during the execution of a program.

Let's say you are adding two numbers by taking input. You have to store the two numbers so that you will add and give the output. Supppose:

- `firstNum` = `2`
- `secondNum` = `3`

Then, the output will be like: `firstNum` `+` `secondNum`.

Here `firstNum` and `secondNum` are _variables_.

### Literals

A **literal** is a fixed, constant value written directly into the source code that does not change during program execution.

In the above example, `2` and `3` are _literals_.

### Identifiers

**Variables** are **identifiers**.

**Identifiers** are unique names used to identify programming elements like _variables_, _methods_, _classes_, _packages_, _interfaces_, and _labels_.

### Mandatory Rules for Defining Identifiers

These rules are strictly enforced by the Java compiler:

- **Allowed Characters**: only alphanumeric (`A`-`Z`, `a`-`z`, `0`-`9`), underscore (`_`), and dollar sign (`$`) are permitted.
- **First Character**: must start with a letter, underscore, or dollar sign.
- **Case Sensitivity:** `myVar`, `MyVar`, and `MYVAR` are completely different identifiers.
- **No Reserved Keywords:** cannot use Java predefined keywords as names.

### Reserved Keywords

**Reserved keywords** are predefined, lowercase words that carry a specific meaning for the Java compiler.

There are `68` _keywords_ in Java out which there are `51` **reserved keywords** and `17` **contextual keywords**.

**Reserved Keywords:**
| | | |
|---|---|---|
| `abstract` | `assert` | `boolean` |
| `break` | `byte` | `case` |
| `catch` | `char` | `class` |
| `continue` | `default` | `do` |
| `double` | `else` | `enum` |
| `extends` | `final` | `finally` |
| `float` | `for` | `if` |
| `implements` | `import` | `instanceof` |
| `int` | `interface` | `long` |
| `native` | `new` | `package` |
| `private` | `protected` | `public` |
| `return` | `short` | `static` |
| `super` | `switch` | `sychronized` |
| `this` | `throw` | `throws` |
| `transient` | `try` | `void` |
| `volatile` | `while` | `_` |
| `const` | `goto` | `strictfp` |

> `const` and `goto` are unused keywords, `_` became a keyword since Java 9 and cannot be used an identifier anymore, and `strictfp` is obsolete now.

> **Note:** `true`, `false`, and `null` are not keywords, they are _literals_.

**Contextual keywords:** These keywords can be used as identifiers, but are restricted in some contexts.

| |
|---|
| `exports` |
| `module` |
| `non-sealed` |
| `open` |
| `opens` |
| `permits` |
| `provides` |
| `record` |
| `requires` |
| `sealed` |
| `to` |
| `transitive` |
| `uses` |
| `var` |
| `when` |
| `with` |
| `yield` |

### Naming conventions for Identifiers

These are not enforced by the compiler but they keep code organized and maintainable:

- **Classes and Interfaces:** Use _PascalCase_. **For example**, `EmployeeRecord`, `DataProcessor`, etc.
- **Variables and Methods:** Use _camelCase_. **For example**, `employeeSalary`, `calculateBonus()`, etc.
- **Constants:** Use _All\_UPPERCASE\_WITH\_UNDERSCORES_. **For example**, `MAX_LOGIN_ATTEMPTS`, `PI`, etc.
- **Packages:** Completely _lowercase.with.dots_. **For example**, `com.company.project.utility`.

## Syntax of a variable

### Declaration only

Allocate a name and type but stores no initial data:

```java
<dataType> <variableName>;
```

### Declaration and Initialization

Declares the variable and assigns a value immediately:

```java
<dataType> <variableName> = <value>;
```

### Multiple Declarations

Declares multiple variables of the same data type on a single line, separated by commas:

```java
<dataType> <variableA> = <value1>, <variableB> = <value2>;
```

## Data type

A **data type** specifies the size and type of values that can be stored in a variable.

> In Java, you have to define the _data type_ before declaring a variable. For this reason, Java is a **statically-typed language**.

There are two kinds of data types:

- Primitive
- Non-primitive

We shall discuss _non-primitive Data types_ later.

**Primitive Data types:**

- Integer: `byte`, `short`, `int`, `long`
- Real numbers: `float`, `double`
- Character: `char`
- Boolean: `boolean`

The computer memory stores everything into binary numbers, i.e., `0`s and `1`s. Each data type have some size and therefore have a range of values that a variable of particular data type can store.

### Integer

| Name | Size (in bits) | Range |
|---------|---------|---------|
| `long` | `64` | `-9,223,372,036,854,775,808` to `9,223,372,036,854,775,807` |
| `int` | `32` | `-2,147,483,648` to `2,147,483,647` |
| `short` | `16` | `-32,768` to `32,767` |
| `byte` | `8` | `-128` to `127` |

Every number is signed in Java. So, the MSB is reserved as the _sign bit_. `1` represents negative and `0` represents positive.

If an integer data type has a size of `n` bits and the MSB is reserved as the _sign bit_, the range of the data type will be from $-(2)^{\text{n} - 1}$ to $2^{\text{n} - 1} - 1$.

> To represent `long` numbers, you can put an optional `l` or `L`.

```java
// Integers

// byte
byte b = 5;

// short
short s = 10;

// int
int i = 4000;

// long
long l = 10000; // or 10000l or 10000L

// Print all
System.out.printn("Integer values --> " + b + ", " + s + ", " + i + ", " + l + ".");
```

### Real Numbers

These data types represents decimal numbers. For example, `5.23`.

| Name | Size (in bits) | Range |
|---------|---------|---------|
| `double` | `64` | `4.9e-324` to `1.8e+308` |
| `float` | `32` | `1.4e-045` to `3.4e+038` |

`float` is known for _single precision_ and `double` is known for _double precision_. In production, `float` is not preferred and `double` is preferred.

> By default, a decimal number is a `double` type. For `float` type, you have to write an `f` or `F` after the decimal number without spaces. For `double`, a `d` or `D` after the decimal number is optional.

> **Scientific Notation**: To represent numbers like $6.022 \times 10^{-23}$, we can just write `6.022e-23` or `6.022E-23`.

> **Note:** To make large numbers readable, you can use one or more underscores (`_`) between any two digits. The compiler will ignore these underscores. But you cannot place them in start, end, before or after non-digits in any numeber system. **For example**, `341256789.79` can be written as `34_12_56_789.79`.

```java
// Real numbers

// float
float f1 = 10.54; // error
float f2 = 10.54f; // or 10.54F

// double
double d = 23.0987; // or 23.0987d or 23.0987D

// Print all
System.out.printn("Real values --> " + f2 + ", " + d + ".");
```

### Character

`char` represents _unicode characters_.

> A character means a single character. A character is always written inside a single quote(`' '`). **For example**, `'a'`, `'2'`, etc.

Earlier languages used _ASCII_ standard to represent characters. **ASCII** covers characters like `a`-`z`, `A`-`Z`, `0`-`9` and some other symbols.

Characters cannot be represented in binary numbers, i.e., `0`s and `1`s. So, we assign each character an integer value and is represented in the binary form of the integer. The decoder then identifies through `char` data type and returns a character.

**For example**, `'a'` is assigned an integer value of `65` and when it is stored in a variable, the `char` data type ensures that it will return `a`.

_ASCII_ uses `8` bits and has a limited range. _Unicode_ uses `16` bits and covers about every symbol used in almost every language.

```java
// Characters

// char
char c = 'a'; // 'a' --> Integer --> binary --> store

// Print all
System.out.printn("Character value --> " + c + ".");
```

### Boolean

`boolean` represents only two values: `true` and `false`.

> In C/C++, any non-zero number represents `true` and `0` represents `false`. But this is not valid in Java. In Java, booleans and numbers are never related.

```java
// Boolean

// boolean
boolean bool = false;

// Print all
System.out.printn("Boolean value --> " + bool + ".");
```

## Comments

These are something that are ignored to be compiled.

For a single line comment:

```java
// this is a single line comment.
```

For multiple lines comment:

```java
/*
this
is
multiple
lines
comment
*/
```

They are mainly used for humans to understand or take notes of the code.

## Number systems in Java

By default, every number written in code is considered as an ordinary base-10 number. We can use some notations to treat them different.

- **Binary:** `0b101` or `0B101` for `5`
- **Octal:** `017` for `15`
- **Hexadecimal:** `0xF` or `0XF` for `15`

## How Java stores negative and floating numbers

### Negative Numbers

For negative numbers, Java stores the `2`'_s complement_ of the number.

**For example**,

```java
byte b = -42;
```

- Binary of `42`: `00101010` (_as_ `byte` _size is_ `8` _bits._)
- Invert the bits or `1`'_s complement_: `11010101`
- Add `1` to get `2`'_s complement_: `11010101` `+` `1` = `11010110`

> The MSB `1` represents a negative number. It cannot be a positive number. **For example**, `byte` size is `8` bits, the maximum positive number is `127`, which is `01111111`. Hence, a positive number has MSB `0` and a negative number has MSB `1`.

To retrieve data, MSB `1` represents negative number and find `2`'_s complement_ again to decode the number.

**For example**, `11010110` has MSB `1`, and `2`'_s complement_ is `00101010` which is 42. So, the number is `-42`.

> **Note:** If we had used `1`'_s complement_, then `+0` is `00000000` and `-0` is `11111111` but both are same number. This does not happen when we use `2`'_s complement_.

### Floating numbers

```java
float f1 = 8.125f;
float f2 = 0.7f;

// This prints the number upto 20 decimal places
System.out.printf("%.20f%n", f1); // 8.12500000000000000000
System.out.printf("%.20f%n", f2); // 0.69999998807907100000
```

First convert the floating number to standard binary form (e.g., $1.011 \times 2^{3}$).

According to the **IEEE 754 Standard**, every floating-point number is split into three specific segments:

1. **Sign bit (`1` bit):** Determines if the number is positive or negative.
2. **Exponent:** Determines the magnitude or position of the decimal point. To store negative exponents efficiently, Java applies a "_bias_" (`127` for `float`, `1023` for `double`).
3. **Mantissa / Significand:** Stores the actual numeric digits of the number. Binary scientific notation always normalizes numbers to start with a leading `1` (e.g., $1.011 \times 2^{3}$), this leading `1` is omitted from storage to save a bit.

To retrieve it back, we use the formuala:

$$
(-1)^{\text{sign}} \times (1 + \text{mantissa}) \times 2^{\text{exponent} - \text{bias}}
$$

| Component | `float` | `double` |
|---|---|---|
| **Sign Bit** | `1` bit | `1` bit |
| **Exponent** | `8` bits | `11` bits |
| **Mantisaa** | `23` bits | `52` bits |
| **Bias Value** | `127` | `1023` |

**For example**, `8.125f`

- Binary form: `1000.001`
- Standard form: $1.000001 \times 2^{3}$

Now, we can store it as:

1. Sign bit: `0` (`1` bit)
2. Exponent: `3` + `127` = `130`, which is `10000010` (`8` bits)
3. Mantissa: `000001 00000000000000000` (`23` bits)

So, the value stored is `0 10000010 00000100000000000000000` (`32` bits).

To retrieve:

- Sign bit: `0`, means positive
- Exponent: `10000010`, means `130`
- Mantissa: 0.`00000100000000000000000`, which is $2^{-6}$
- Bias: `127` for `float`

So, the number is: $(-1)^{0} \times (1 + 2^{-6}) \times 2^{130 - 127}$ = `8.125`.

**Take another example**, `0.7f`

- Binary form: `0.1 0110 0110 0110 ...` (_non-terminating repeating_)
- Standard form: $1.0110 0110 0110\text{...} \times 2^{-1}$

We can store it as:

1. Sign bit: `0` (`1` bit)
2. Exponent: `-1` + `127` = `126`, which is `01111110` (`8` bits)
3. Mantissa: `0110 0110 0110 0110 0110 011` (`23` bits)

So, the value stored is `0 01111110 01100110011001100110011` (`32` bits).

To retrieve:

- Sign bit: `0`, means positive
- Exponent: `01111110`, means `126`
- Mantissa: 0.`01100110011001100110011`, which is ($2^{-2} + 2^{-3} +2^{-6} + 2^{-7} + 2^{-10} + 2^{-11} + 2^{-14} + 2^{-15} + 2^{-18} + 2^{-19} + 2^{-22} + 2^{-23}$)
- Bias: `127` for `float`

So, the number is: $(-1)^{0} \times (1 + (2^{-2} + 2^{-3} +2^{-6} + 2^{-7} + 2^{-10} + 2^{-11} + 2^{-14} + 2^{-15} + 2^{-18} + 2^{-19} + 2^{-22} + 2^{-23})) \times 2^{126 - 127}$ = `0.69999998807907104421875`.

> Java also has `BigDecimal` which stores `0.7` as `0.7`.