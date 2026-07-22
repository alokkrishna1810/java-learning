# Basic Flow of a Java Program

- We have a source code `Demo.java`.
- The source code is compiled by Java compiler.

    ```bash
    javac Demo.java
    ```

- We get _bytecode_, i.e., `Demo.class`.
- We run Java with the help of **JRE**.

    ```bash
    java Demo
    ```

- The **JRE** with the help of **JVM** which contains the _interpreter_ and the _JIT compiler_, converts the bytecode into machine code.
- The machine code gives instructions to the CPU and it gives output.

## Hello World! Program

```java
public class Demo {
    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
```

This program when compiled and run, gives the following output:

```
Hello World!
```

For now consider the below code block as black box and just focus on what is inside this block. Later on, we will understand everything:

```java
public class Demo {
    public static void main(String[] args) {
        ...
        ...
        ...
    }
}
```