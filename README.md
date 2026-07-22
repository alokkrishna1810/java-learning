# Java

## Why Java

Before Java, C/C++ were the most famous in 1980/90s. C/C++ was:

- fast
- simple
- low-level (close to hardware)

But there were some problems.

**C/C++ is not portable or C/C++ is platform-dependent.** To run C/C++ code, we need a _compiler_ to convert the code into machine code (`0`s and `1`s). If the code is compiled on platform A, the generated machine code is not executable on platform B.

(_A platform is a combination of a **processor** and an **OS**. Due to different OS, the _binaries_ will be different. Due to different processors, the setups of transistors will be different and the same binaries may produce different results or give an error. Or simply, due to different processors, the ISAs will be different._)

**Java** introduced:

- Portability
- More simplicity
- More security

## How Java is portable?

Java introduced the concept of **bytecode**.

- Install **JVM (Java Virtual Machine)** into target platform. **JVM** is a software.
- The compiler converts the Java source code (`.java` file) into _bytecode_ (`.class` file). The bytecode is an intermediate file.
- This _bytecode_ is executable on all the platforms that have _JVM_.

Hence, I can just _compile_ the source code once and run the _bytecode_ on any platform which has **JVM**. This is called **WORA (Write Once, Run Anywhere).

> **Note:** The **JVM** is platform dependent. The _bytecode_ is platform independent because of **JVM** on a platform.

## Why portability is important?

- At the time when C/C++ was dominant, new technologies were evolving such as _set top box_, _TVs_, etc. So, we needed something so that one application can run on different devices with same efficiency.

- C/C++ is fast with no doubt. But as processors evolved, the speed does not matter now that much. That's why a slower language like Python is used for scientific computations.

- At that time, Internet was also evolving. In a website, there is a _frontend_ and a _backend_. The code will be deployed on a **server**. If we have to use multiple _servers_, then **portability** is a great advantage to avoid compiling on each server.

## How is Java more simple and more secure?

- **Simplicity:** Java discarded the complex things such as _pointers_, _multiple inheritance_, _manual memory allocation / deallocation_.

- **Security:** For backend, Java introduced _servelet_ which is a program that works like an API. Earlier, Java was also used in frontend with the help of _Applets_ which are discontinued since Java 10/11. Applets were lightweight code which can be transmitted over the internet and could be run on user's browser. Misusing applets were easy. Hence, Java introduced **Java Security**. The **JVM** runs the _bytecode_ into a secure environment which restricts the unwanted access. This model is known as **Sandbox model**.

> **Note:** Microsoft tried some experiments to make C/C++ portable but it did not work. Also, C/C++ was not expected for this and was mainly known for its speed and closeness to hardware. Microsoft introduced C# language which is portable. Python is also portable.