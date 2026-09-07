# External Files

In C++, code is split across multiple files and connected using `#include` directives.

A separate file `MyClass.h`

```cpp
#include <string>class MyClass {public:    std::string greet() {        return "Hello from MyClass!";    }};
```

Include and use it in your main file

```cpp
#include <iostream>#include 
"MyClass.h"int main() {    
MyClass obj;    
std::cout << obj.greet() << std::endl;    return 0;}
```

Output:

```cpp
Hello from MyClass!
```

Use double quotes `""` for your own files and angle brackets `<>` for system/library headers. The `#include` directive copies the content of the file into your source code before compilation.

# C++ Build & Compilation

C++ builds in three stages: Preprocessing, Compilation, and Linking.

**1. Preprocessing** — `#include` directives are resolved, copying header contents into source files

```cpp
#include <iostream>    // System header#include "my_file.h"   // Your own header
```

**2. Compilation** — Each `.cpp` file is compiled independently into an object file (`.o`)

```cpp
// math_utils.cpp compiles into math_utils.o// main.cpp compiles into main.o
```

**3. Linking** — Object files are combined into the final executable

```cpp
// math_utils.o + main.o → program.exe
```

The header file declares what exists (prototypes). The `.cpp` file provides the actual implementation. The linker connects calls in `main.cpp` to implementations in other `.cpp` files.

# Header Files & Source Files

In C++, code is split into header files (`.h`) for declarations and source files (`.cpp`) for implementations.

Header file with header guards (`helpers.h`)

```cpp
#ifndef HELPERS_H#define HELPERS_H#include <string>std::string greet(std::string name);int addNumbers(int a, int b);#endif
```

Source file with implementations (`helpers.cpp`)

```cpp
#include "helpers.h"std::string greet(std::string name) {    return "Hello, " + name + "!";}int addNumbers(int a, int b) {    return a + b;}
```

Using them in main

```cpp
#include <iostream>#include "helpers.h"int main() {    std::cout << greet("Alice") << std::endl;    std::cout << addNumbers(5, 3) << std::endl;    return 0;}
```

Output:

```cpp
Hello, Alice!8
```

==Header guards (`#ifndef`, `#define`, `#endif`) prevent a header from being included multiple times. The `.h` file declares what exists (prototypes), the `.cpp` file defines how it works (implementations).


# Namespaces & Scope

Namespaces group related code together and prevent naming conflicts. The `::` scope resolution operator accesses items inside a namespace.

Creating a namespace

```cpp
namespace MathTools {    int add(int a, int b) {        return a + b;    }}
```

Accessing with scope resolution `::`

```cpp
int result = MathTools::add(5, 3);  // result = 8
```

Using directive to avoid typing the namespace each time

```cpp
using namespace MathTools;int result = add(5, 3);  // Same as MathTools::add(5, 3)
```

The `std` namespace

```cpp
std::cout << "Hello" << std::endl;// orusing namespace std;cout << "Hello" << endl;
```

**Namespaces organize code and prevent naming collisions. The `std` namespace contains all C++ standard library features like `cout`, `cin`, `string`, and `endl`.

# ==Introduction to OOP in C++

Object-Oriented Programming organizes code into classes that bundle data and behavior together.

A simple class with public members

```cpp
class Dog {public:    std::string name;    int age;        std::string bark() {        return name + " says Woof!";    }};
```

Creating and using an object

```cpp
Dog dog;dog.name = "Buddy";dog.age = 3;std::cout << dog.bark() << std::endl;
```

Output:

```cpp
Buddy says Woof!
```

A class defines the structure — what data it holds and what actions it can perform. An object is a specific instance you create and use. Members under `public:` can be accessed from anywhere.

# Classes vs Objects

A class is a blueprint that defines structure. An object is a specific instance created from that blueprint.

The class (blueprint)

```cpp
class Car {public:    std::string brand;    int year;        std::string getInfo() {        return brand + " (" + std::to_string(year) + ")";    }};
```

Creating multiple objects (instances)

```cpp
Car car1;car1.brand = "Tesla";car1.year = 2023;Car car2;car2.brand = "Honda";car2.year = 2020;std::cout << car1.getInfo() << std::endl;  // Tesla (2023)std::cout << car2.getInfo() << std::endl;  // Honda (2020)
```

Each object is independent. Changing `car1` doesn't affect `car2`. You can create multiple objects from the same class, each holding its own data.


# The 'this' Pointer

In C++, `this` is a pointer to the current object. Use `this->` to access members, especially when parameter names match member names.

Without `this`, the parameter shadows the member

```cpp
void Player::setName(std::string name) {    name = name;  // Assigns parameter to itself! Member unchanged.}
```

Using `this->` to correctly assign values

```cpp
void Player::setName(std::string name) {    this->name = name;  // Assigns parameter to member}
```

Using `this->` in methods

```cpp
std::string Player::getStatus() {    return this->name + " - Score: " + std::to_string(this->score);}
```

The `this` pointer always points to the current object instance. Unlike Java and C# where `this` is a reference, in C++ it's a pointer, so you use `->` instead of `.` to access members.


# Methods (Member Functions)

Member functions define what an object can do. They have a return type, a name, and optional parameters.

Method returning a value

```cpp
class Calculator {public:    int add(int a, int b) {        return a + b;    }};
```

Void method (no return value)

```cpp
class Printer {public:    void printMessage(std::string msg) {        std::cout << msg << std::endl;    }};
```

Method returning bool

```cpp
class Checker {public:    bool isPositive(int num) {        return num > 0;    }};
```

Declaring in header, implementing in source

```cpp
// Calculator.hclass Calculator {public:    int add(int a, int b);};// Calculator.cppint Calculator::add(int a, int b) {    return a + b;}
```

The return type goes before the method name. Use `void` when a method doesn't return anything. The `::` scope resolution operator links implementations to their class.
