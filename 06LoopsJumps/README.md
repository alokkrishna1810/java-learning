# Loops and Jumps

## Iteration (Loop Statements)

**Iteration** is the process of executing a set of instructions repeatedly, usually to loop through numbers of traverse elements within collections and arrays.

**Scenario:** Print numbers from 1 to 10.

```java
int i = 1;

System.out.println(i); // 1
i++;
System.out.println(i); // 2
i++;
System.out.println(i); // 3
i++;
System.out.println(i); // 4
i++;
System.out.println(i); // 5
i++;
System.out.println(i); // 6
i++;
System.out.println(i); // 7
i++;
System.out.println(i); // 8
i++;
System.out.println(i); // 9
i++;
System.out.println(i); // 10

// Loops make it easy and short.
```

## `while` loop

**Syntax:**

```java
while (condition) {
    // do something
}
```

The loops starts as:
1. check the condition (must be `boolean`), if `false`, exit
2. Execute code block.
3. Repeat step 1.

```java
// while loop

// Print numbers from 1 to 10
int i = 1;

while (i <= 10) { // 1. check the condition, exit if false
    System.out.println(i); // 2. print i and start new line
    i++; // 3. increase i by 1
} // 4. repeat step 1

// Print numbers from 10 to 1
i = 10;

while (i >= 1) { // 1. check the condition, exit if false
    System.out.println(i); // 2. print i and start new line
    i--; // 3. decrease i by 1
} // 4. repeat step 1

// Print numbers from 1 to 10
i = 0;

while (i++ < 10) { // 1. check i < 10, increase i by 1, exit if false
    System.out.println(i); // 2. print i
} // 3. repeat step 1
```

> **Note:** If the condition never evaluates to `false`, the program will be trapped in an **infinite loop**.

> The story of curly braces (`{}`) in loops is same as that of conditional statements.

## `-do-while` loop

**Syntax:**

```java
do {
    // do something
} while (condition);
```

The loops starts as:
1. Execute the code block.
2. check the condition (must be `boolean`), exit if `false`.
3. Repeat step 1.

> **Note:** `do-while` loop guarantees at least one iteration.

```java
// do-while loop

// Print numbers from 1 to 10
int i = 1;

do {
    System.out.println(i); // 1. print i and start a new line
    i++; // 2. Increase i by 1
} while (i <= 10); // 3. check the condition, exit if false
// 4. Repeat step 1
```

## `for` loop

**Syntax:**

```java
for (intialization; condition; update) {
    // do something
}
```

The loops starts as:
1. Initialize a value. _Runs only once_.
2. check condition (must be `boolean`). Exit if `false`.
3. Execute the block.
4. Update.
5. Repeat step 2.

```java
// for loop

// Print numbers from 1 to 10
for (int i = 1; i <= 10; i++) {
    System.out.println(i);
}

/* Flow:
1. Initialize i = 1
2. Check i <= 10. Exit if false.
3. print i and start new line
4. increase i by 1
5. Repeat step 2.
*/

// Print numbers from 10 to 1
for (int i = 10; i >= 1; i--) {
    System.out.println(i);
}

/* Flow:
1. Initialize i = 10
2. Check i >= 1. Exit if false.
3. print i and start new line
4. decrease i by 1
5. Repeat step 2.
*/
```

> `for-each` loop will be discussed later.

## Special cases

```java
// This is a correct code and infinite loop
int i = 1;

while (i < 10) {

}

// This is also an infinite loop
for (int j = 0; ; j++) {
    System.out.println("Hello");
}

// This is also an infinite loop
for (; ; i++) {
    System.out.println("Hello");
}

// This is also an infinite loop
for (; ;) {
    System.out.println("Hello");
}

// Comma separated variation of for loop
// You can initialize or update as many variables separated with commas
for (int j = 1, k = 1; j <= 10; j++, k += 2) {
    System.out.println(j * k);
}

/* Flow:
1. Initialize j = 1, k = 1
2. Check j <= 10. Exit if false
3. print j * k and start a new line.
4. Increase j by 1 and increase k by 2
5. Repeat step 2.
*/
```

## Nested loops

You can nest a loop inside any loop.

**For example:**

```java
// Nested loops

for (int i = 1; i <= 5; i++) {
    for (int j = 1; j <= 5; j++) {
        // do something
    }
}

/* Flow:
1. Initialize i = 1.
2. Check i <= 5. Exit if false.
3.
    a. Initialize j = 1.
    b. Check j <= 5. Return to step 4 if false.
    c. do something
    d. Increase j by 1.
    e. Repeat step b.
4. Increase i by 1.
5. Repeat step 2.
*/

/* Print pattern:

*
* *
* * *
* * * *
* * * * *

*/

for (int i = 1; i <= 5; i++) {
    for (int j = 1; j <= i; j++) {
        System.out.print("* "); // prints and stays in the same line
    }

    System.out.println(); // print nothing and starts a new line
}

/* Flow:
1. Initialize i = 1.
2. Check i <= 5. Exit if false.
3.
    a. Initialize j = 1.
    b. Check j <= i. Return to step 4 if false.
    c. Print "* "
    d. Increase j by 1.
    e. Repeat step b.
4. Print nothing and start a new line.
5. Increase i by 1.
6. Repeat step 2.
*/
```

## Jumping (Jump statements)

| Jump Statement | Scope of Use | Primary Effect |
|---|---|---|
| `break` | Inside loops and `switch` blocks | Terminates a loop or switch completely. |
| `continue` | Inside loops only | Skips the remaining code of current iteration and jumps to the next iteration. |
| `return`| Anywhere inside a method. | Terminates the method and transfers back to the caller (with or without a value depending on data type of method). |

```java
// break

for (int i = 1; i <= 10; i++) {
    System.out.println(i);

    if (i > 5) {
        break;
    }

    System.out.println("i is not greater than 5.");
}

/* Flow:
1. Initialize i = 1.
2. Check i <= 10. Exit if false.
3. Print i and start a new line.
4. Check i > 5. Skip if-block if false and go to step 6.
5.
    a. Exit the loop.
6. Print "i is not greater than 5." and start a new line.
7. Repeat step 2.
*/

// continue

for (int i = 1; i <= 10; i++) {
    if (i % 2 == 0) {
        continue;
    }

    System.out.println(i);
}

/* Flow:
1. Initialize i = 1.
2. Check i <= 10. Exit if false.
3. Check i % 2 == 0. Skip if-block if false and go to step 5.
4.
    a. Skip the remaining code and go to step 2.
5. Print i and start a new line.
6. Repeat step 2.
*/

// Labels

outer: for (int i = 1; i <= 10; i++) {
    inner: for (int j = 1; j <= i; j++) {
        System.out.println("* ");

        if (j >= 5) {
            break outer; // this exits for loop labelled as outer.
            // also applicable for continue
        }
    }

    System.out.println();
}

// We can also label code blocks into braces
// But this is of no use right now

first: {
    second: {
        third: {
            System.out.println("Hello");
            break first;
        }
    }
}
```