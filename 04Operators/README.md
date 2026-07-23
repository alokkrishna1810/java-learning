# Operators

**Operators** are special symbols or keywords used to perform specific mathematical, logical, or data manipulation operations on variables and values.

The values that an operator acts upon are called **operands**.

**Types of Operators:**

1. Arithmetic operators: `+`, `-`, `*`, `/`, `%`, `+=`, `-=`, `*=`, `/=`, `%=`, `++`, `--`
2. Relational operators: `==`, `!=`, `<`, `>`, `<=`, `>=`
3. Bitwise operators: `&`,`|`, `^`, `~`, `>>`, `<<`, `>>>`, `&=`, `|=`, `^=`, `>>=`, `<<=`, `>>>=`
4. Logical operators: `&&`, `||`, `!`
5. Assignment operator: `=`
6. Ternary operator: `? :`

## Arithmetic Operators

```java
// Arithmetic operators

int a = 5;
int b = 10;

int c = a + b // addition: c = 10 + 5 = 15
int d = a - b // substraction: d = 5 - 10 = -5
int e = a * b; // multiplication: e = 5 * 10 = 50
int f = b / a; // division: f = 10 / 5 = 2
int g = b % a; // modulo / remainder: g = 10 % 5 = 2

int h = a + 2; // h = 5 + 2 = 7
h = h + 2; // h = 7 + 2 = 9

h += 2; // h = h + 2 = 9 + 2 = 11
h -= 2; // h = h - 2 = 11 - 2 = 9
h *= 3; // h = h * 3 = 9 * 3 = 27
h /= 5; // h = h / 5 = 27 / 5 = 5
h %= 3; // h = h % 3 = 5 % 3 = 2

int i = 6;

i++; // Postfix Increment: increase by 1 => i = 7
++i; // Prefix Increment: increase by 1 => i = 8

i--; // Postfix Decrement: decrease by 1 => i = 7
--i; // Prefix Decrement: decrease by 1 => i = 6

int j = 7;

// Postfix Increment / Decrement
// => first use, then increase / decrease
int k = j++; // k = 7, j = 8
int l = j--; // l = 8, j = 7

// Prefix Increment / Decrement
// => first increase / decrease, then use
k = ++j; // j = 8, k = 8
l = --j; // j = 7, l = 7

System.out.println(++j); // j = 8, print 8
System.out.println(j++); // print 8, j = 9
System.out.println(--j); // j = 8, print 8
System.out.println(j--); // print 8, j = 7
```

## Relational Operators

```java
// Relational Operators

int a = 5;
int b = 10;

boolean c = (a == b); // does a equal b? false
boolean d = (a != b); // doesn a not equal b? true
boolean e = (a < b); // is a less than b? true
boolean f = (a > b); // is a greater than b? false
boolean g = (a <= b); // is a less than or equal to b? true
boolean h = (a >= b); // is a greater than or equal to b? false
```

## Bitwise Operators

**Truth Table:**

| Bit `A` | Bit `B` | `A & B` | `A \| B` | `A ^ B` |
|---|---|---|---|---|
| `0` | `0` | `0` | `0` | `0` |
| `0` | `1` | `0` | `1` | `1` |
| `1` | `0` | `0` | `1` | `1` |
| `1` | `1` | `1` | `1` | `0` |

| Bit `A` | `~A` |
|---|---|
| `0` | `1` |
| `1` | `0` |

```java
// Bitwise Operators

int a = 2; // a => 00000000 00000000 00000000 00000010
int b = 3; // b => 00000000 00000000 00000000 00000011

int c = a & b; // bitwise AND: 00000000 00000000 00000000 00000010 => 2
int d = a | b; // bitwise OR: 00000000 00000000 00000000 00000011 => 3
int e = a ^ b; // bitwise Exclusive OR or XOR: 00000000 00000000 00000000 00000001 => 1
int f = ~a; // bitwise NOT: 11111111 11111111 11111111 11111101 => -3 
```

```java
/* Left shift (<<)
    => shifts all bits to left by a given value and put 0s in vacant spaces
    => equivalent to multiplication by 2^n, if shifted by n
*/

int i = 1;

i = i << 1;

/* Shift all bits to left by 1 and the put 0s in vacant space
    00000000 00000000 00000000 00000001 => 1
    0000000 00000000 00000000 00000001

    00000000 00000000 00000000 00000010 => 2 = 1 * 2^1
*/

i = i << 2;

/* Shift all bits to left by 2 and the put 0s in vacant space
    00000000 00000000 00000000 00000010 => 2
    000000 00000000 00000000 00000010

    00000000 00000000 00000000 00001000 => 8 = 2 * 2^2
*/

byte j = 1;

j = (byte) (j << 7);

/* Shift all bits to left by 7 and the put 0s in vacant space
    j = 1 => 00000001
    By type promotion, j becomes int.

    00000000 00000000 00000000 00000001 => 1
    0 00000000 00000000 00000001

    00000000 00000000 00000000 10000000 => 128 = 1 * 2^7

    Now, from explicit type conversion:
    j => 10000000 => -128
*/
```

```java
/* Signed Right shift (>>)
    => shifts all bits to right by a given value and replicates the MSB in vacant spaces
    => equivalent to division by 2^n, if shifted by n
*/

int j = 8;

j = (byte) (j >> 1);

/* Shift all bits to right by 1 and the replicate MSB in vacant space
    j = 8 => 00001000
    By type promotion, j becomes int.

    00000000 00000000 00000000 00001000 => 8
     00000000 00000000 00000000 0000100

    00000000 00000000 00000000 00000100 => 4 = 8 / 2^1

    Now, from explicit type conversion:
    j => 00000100 => 4
*/

j = -128;

j = (byte) (j >> 2);

/* Shift all bits to right by 2 and the replicate MSB in vacant space
    j = -128 => 10000000
    By type promotion, j becomes int.

    11111111 11111111 11111111 10000000 => -128
      11111111 11111111 11111111 100000

    11111111 11111111 11111111 11100000 => -32 = 128 / 2^2

    Now, from explicit type conversion:
    j => 11100000 => -32
*/

/* Unsigned Right shift (>>>)
    => shifts all bits to right by a given value and put 0s in vacant spaces irrespective of MSB
*/

j = -128;

j = (byte) (j >>> 2);

/* Shift all bits to right by 2 and the replicate MSB in vacant space
    j = -128 => 10000000
    By type promotion, j becomes int.

    11111111 11111111 11111111 10000000 => -128
      11111111 11111111 11111111 100000

    00111111 11111111 11111111 11100000 => 1073741792

    Now, from explicit type conversion:
    j => 11100000 => -32
*/
```

> **Note:** You can do any type of shift of maximum `31` for `int` and `63` for long. If you try a larger number, Java applies automatically applies a **bitwise mask** to the shift value, i.e., `n & 31` for `int` (take lower `5` bits) and `n & 63` for `long` (take lower 6 bits). These are equivalent to `n % 32` and `n % 64` respectively.

## Logical Operators

**Truth Table:**

| Logic `A` | Logic `B` | `A && B` | `A \|\| B` |
|---|---|---|---|
| `false` | `false` | `false` | `false` |
| `false` | `true` | `false` | `true` |
| `true` | `false` | `false` | `true` |
| `true` | `true` | `true` | `true` |

| Logic `A` | `!A` |
|---|---|
| `false` | `true` |
| `true`| `false` |

```java
// Logical operators

int a = 5;
int b = 10;
int c = 15;

boolean d = (a < b) && (b < c); // true && true => true

a = 25;

d = (a < b) && (b < c); // false && true => false

a = 5;
d = (a < b) || (b < c); // true || true => true
```

> **Short circuit:** For logical AND (`&&`), if any logic evaluates to `false`, then the rest of the expression is not evaluated and the result is `false`. Similary, for logical OR (`||`), if any logic evaluates to `true`, then the rest of the expression is not evaluated and the result is `true`.

> **Note:** You can use bitwise AND (`&`) and bitwise OR (`|`) instead of logical AND (`&&`) AND logical OR (`||`) respectively. But, **short circuiting** only happens for logical operators.

## Assignment Operator

```java
int a = 5; // assign 5 to a => a = 5

int b = c = d = 10; // assignment chaining: assign 10 to d, c, and b
```

## Ternary operator

- **Unary Operator:** requires only one operand
- **Binary Operator:** requires two operands
- **Ternary Operator:** requires three operands

```java
condition ? expression_if_true : expression_if_false
```

> This will be covered in _conditional statements_.

## Operator Precedence

In an expression involving multiple operators, there are precedence rules that Java follows to evaluate the expression.

- Operators with higher precedence are evaluated before operators with lower precedence.
- When operators of equal precedence appear in the same expression, all binary operators except for the assignment operators are evaluated from left to right, assignment operators are evaluated from right to left.

| Operators | Precedence |
|---|---|
| parenthesis | `()` |
| postfix | _expr_`++`, _exp_`--` |
| unary | `++`_expr_, `--`_exp_, `+`_exp_, `-`_exp_, `~`, `!` |
| multiplicative | `*`, `/`, `%` |
| additive | `+`, `-` |
| shift | `<<`, `>>`, `>>>` |
| relational | `<`, `>`, `<=`, `>=`, `instanceof` |
| equality | `==`, `!=` |
| bitwise AND | `&` |
| bitwise exclusive OR | `^` |
| bitwise inclusive OR | `\|` |
| logical AND | `&&` |
| logical OR | `\|\|` |
| ternary | `? :` |
| assignment | `=`, `+=`, `-=`, `*=`, `/=`, `%=`, `^=`, `\|=`, `<<=`, `>>=`, `>>>=` |

> For better readablity and ensure desired outputs, use brackets in complex expressions.