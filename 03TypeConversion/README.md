# Type Conversions and Type Promotions

## Type Conversion

**Type conversion** is the process of converting a value of one data type into another data type.

There are two primary categories:

1. Implicit Type Conversion (Widening)
2. Explicit Type Conversion (Narrowing)

### Implicit Type Conversion (Widening)

This is done automatically by the Java compiler.

**Rule:** Destination data type should be wider than source data type. **For example**, `byte` (`8` bits) can be converted into `int` (`32` bits).

```java
// Implicit Type Conversion or Widening

byte b = 30; // b = 30 => 00011110
int i = b; // i = 30 => 00000000 00000000 00000000 00011110

// char (16 bits) value is stored as a number
char c = 'a'; // 97 => 00000000 01100001
int i1 = c; // i1 = 97 => 00000000 00000000 00000000 00110001
```

### Explicit Type Conversion (Narrowing)

This must be done manually by the programmer. This is called **casting**.

This is used when destination data type is narrower than source data type. **For example**, `int` (`32` bits) cannot be converted automatically into `byte` (`8` bits).

> **Narrowing** can be a risky operation and may lead to data or precision loss.

**For example**,

```java
// Explicit Type Conversion or Narrowing

int i = 300; // i = 300 => 00000000 00000000 00000001 00101100
byte b = (byte) i; // b = 44 => 00101100 (data truncated) or 300 & 255 (take lower 8 bits) or simply 300 % 256 = 44
```

> **Note:** There is another type conversion which comes under **Narrowing**. That is called **Truncating Conversion**. This happens when we try to convert _floating_ numbers to _integers_.

```java
// Truncating Conversion
// => chops the decimal part

float f = 16.25f; // 16.25f => 0 10000011 00000100000000000000000 => 01000001 10000010 00000000 00000000
int i = (int) f; // i = 16 => 00000000 00000000 00000000 00010000
```

> **Boolean** data types cannot be converted to any other data type.

## Type Promotions

**Type promotion** is the automatic conversion of a smaller primitive data type into a larger data type.

The Java compiler performs this implicitly during **arithmetic operations** or **method overloading** to prevent data overflow and maintain precision.

**Rules:**

- `byte`, `short` and `char` are promoted to `int`.
- If one operand is `long`, the whole expression will become `long`.
- If one operand is `float`, entire expression will become `float`.
- If one operand is `double`, entire expression will become `double`.

```java
byte b = 50;
b = b * 2 // error as in RHS b promoted to int, so b * 2 is int, so implicit conversion is not possible

b = (byte) (b * 2); // correct as explicit conversion allowed
```

**Practice this to identify the type promotions:**

```java
byte b = 42;
char c = 'a';
short s = 1024;
int i = 50000;
float f = 5.67f;
double d = .1234;

double result = (f * b) + (i / c) - (d * s);

// 238.14 + 515 - 126.3616

/*
(f * b) => float => as f is float and b is promoted to int, so each will convert to float
(i / c) => int => as i is int and c is promoted to int, so each will result is int
(d * s) => double => as d is double and s is promoted to int, so each will convert to double.

(f * b) + (i / c) - (d * s) => double => as float + int - double and each will convert to double.

result => double and expressio => double, so no error.
*/
```