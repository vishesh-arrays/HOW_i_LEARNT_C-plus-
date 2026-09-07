Hello World!

The **"Hello World!"** is a simple program that outputs `Hello World!` to the screen.

In C++, we use `std::cout` to print output to the console. The text to be printed is placed within double quotes and followed by the insertion operator `<<`.

Before we can use `std::cout`, we need to include the `iostream` library at the top of our file. This is done with `#include <iostream>`. The `iostream` library provides the tools needed for input and output — without it, `std::cout` would not be available.

Let's take a look at the "Hello World!" program in C++:

```cpp
#include <iostream>int main() {   
 std::cout << "Hello World!";    
 return 0;}
```


# Comments

**Comments** are notes you write inside your code. The compiler completely ignores them - they exist only to help humans understand the code.

To write a single-line comment, use `//`. Everything after `//` until the end of the line is ignored:

```cpp
// This is a commentstd::cout << "Hello, World!";
```

A comment can also be written at the end of a line, after the code:

```cpp
std::cout << "Hello, World!"; // This prints Hello, World!
```

For comments that span several lines, use `/*` to start and `*/` to end:

```cpp
/* This is a multi-line comment.   The compiler ignores all of it. */std::cout << "Welcome!";
```

Comments can also temporarily **disable** a line of code without deleting it. This is called **commenting out**:

```cpp
// std::cout << "This line will NOT run";std::cout << "This line will run";
```

# Basic Program Structure

In C++, most executable code is written inside functions. The `main` function is the entry point of a C++ program — when you run a C++ program, the code inside `main` is the first to be executed. Some code, like global declarations and preprocessor directives, can appear outside of functions, and you can also create your own custom functions (we'll cover that in a later lesson).

Here's a simple breakdown of a basic C++ program:

```cpp
#include <iostream>
 // Preprocessor directive for input/outputint main() {
  // Main function    
  std::cout << "This is my first C++ program!";
   // Output statement    
   return 0; 
   // Return statement (good practice)}
```

In C++, the `#include` preprocessor directive is used to include header files, which contain declarations of functions and objects that your program can use. In this case, `#include <iostream>` includes the iostream header, which provides objects like `std::cout` for outputting text to the console.

Let's break down the key parts of the program above:

- **Preprocessor directive (`#include <iostream>`):** This line runs before compilation and tells the compiler to include the iostream header file, giving your program access to input/output tools.
- **Function (`int main() { ... }`):** A function is a named block of code that performs a task. The `int` before `main` indicates the function returns an integer value. The curly braces `{}` define the _scope_ of the function — everything inside them belongs to `main`. Scoping means that code inside a block is contained within it and runs as part of that block.

- **Namespace prefix (`std::`):** The `std::` prefix tells the compiler to look for `cout` inside the standard library namespace. A namespace is a way to group related names and avoid conflicts. We'll explore namespaces more in a later lesson.
- **Output statement (`std::cout`):** This prints text to the console.
- **Return statement (`return 0;`):** This signals that the program finished successfully. While C++ does not strictly require a return statement in `main`, including it is considered good practice.

Important note: In C++, each statement must end with a semicolon (`;`). The semicolon is mandatory and tells C++ that you've reached the end of a statement. Forgetting to add a semicolon will result in a compilation error. However, note that code blocks enclosed in curly braces `{}` (like function declarations) don't need semicolons.

# Whole Numbers

**Variables** are containers that hold data values. They are used to store, manipulate, and display information within a program.

In short, a variable is like a memory unit that we can access by typing the name of the variable. 

Each variable has a unique **name** and a **value** that can be of different types. C++ has various built-in data types that define the type of value a variable can hold.

Working with variables involves two steps:

- **Declaration** — telling the computer that the variable exists:  
    `int age;`
- **Initialization** — assigning the variable a value:  
    `age = 30;`

These two steps can be combined into one line using the following **format**:

```cpp
variable_type variable_name = value;
```

In C++, **whole numbers** are typically represented using the `int` data type.

`int` is used to store whole numbers without any decimal point. For example:

```cpp
int age = 30;
int temperature = -5;
int count = 100;
```

When declaring variables in C++, you need to specify the type of the variable before the variable name. This is known as **type declaration**. Once a variable is declared with a certain type, it can only hold values of that type.

You can also declare multiple variables of the same type in a single line:

```cpp
int a, b, c;
```

In modern C++, variables can also be initialized using **brace initialization** or **constructor initialization**:

```cpp
int num{0};   // brace initializationint num(0);   // constructor initialization
```

C++ also provides the `auto` keyword, which lets the compiler automatically deduce the type of a variable from its assigned value:

```cpp
auto score = 10;    // deduced as intauto price = 9.99;  // deduced as double
```

# Real Numbers

In C++, **real numbers** are typically represented using two main data types: `float` and `double`.

`float` is used to store numbers with a decimal point. For example:

```cpp
float price = 99.99f;
```

The 'f' (or 'F') at the end of a decimal number is called a literal suffix, and it explicitly tells the compiler that this number should be treated as a float.

`double` is used to store numbers with a decimal point, but with double precision. float typically has 7 decimal digits of precision whereas double typically has 15-17 decimal digits of precision. For example:

```cpp
float f = 3.14159265359;
double d = 3.14159265359;
cout << f << endl; 
// Might print: 3.14159cout << d << endl;
 // Might print: 3.14159265359
```

# Boolean

A **boolean** type has only 2 possible values: `true` or `false`.

To assign a boolean value to a variable, use the keyword `bool` followed by the variable name:

```cpp
bool variable_true = true;
bool variable_false = false;
```

In the above example, two boolean variables named `variable_true` and `variable_false` are initialized with the values `true` and `false`, respectively. When printing a boolean value using `cout`, `true` displays as 1 and `false` displays as 0.

> Booleans are the building blocks for creating logic in the programs we write. We have a whole chapter about logic and conditions.

# Char

A **char** is a single character (For example: 1, 6, %, b, p, ., T, etc.)

The **char** type is a special type that consists of a single character.

To initialize a char value in a variable, enclose it within **single quotation marks**:

```cpp
char c1 = 'h';
```

In the above example, a char variable named `c1` is initialized.

# Constants

A constant is a special type of variable that cannot be changed once it is initialized.

To declare a constant use the keyword `const` followed by the variable type:

```cpp
const int maxValue = 100;
```

In the above example, a constant named `maxValue` is initialized with the value `100`.

If we try to change a constant value:

```cpp
const int maxValue = 100;
maxValue = 200; // This will cause an error
```

It will result in an error because constant values cannot be changed.

In C++, it is a common convention to name constants using **ALL_CAPS** (uppercase letters with underscores between words):

```cpp
const int MAX_VALUE = 100;
const double PI = 3.14159;
```

This makes constants easy to distinguish from regular variables in your code.

# Type Declaration

In C++, once a variable is declared with a certain type, it can only hold values of that type. For instance, an `int` variable can only hold integer values, and a `std::string` variable can only hold text.

For example:

```cpp
int age = 25;          // Can only hold whole numbersstring str = "abc";  // Can only hold text
```

These would cause errors:

```cpp
age = "defg";  // Error: can't put text in an int variablestr = 25;      // Error: can't put a number in a string variable
```

These are valid:

```cpp
age = 26;        // OK: assigning a new integerstr = "Jane";    // OK: assigning a new text string
```

# Naming Conventions

In programming, it's important to follow naming conventions to keep your code readable and maintainable. However, there are some rules and conventions you should follow when naming things in C++:

- Names can contain letters, digits, and underscores.
- Names must begin with a letter or an underscore.

- Names are case-sensitive (`myVariable` and `myvariable` are different).
- Names cannot be C++ keywords (like `int`, `float`, `if`, etc.).

In addition to these rules, there are some common naming conventions that developers use to make their code more consistent and readable:

- **camelCase** — words are joined together, with each word after the first starting with a capital letter (e.g., `totalAmount`, `numberOfStudents`). Commonly used for variable and function names in C++.
- **PascalCase** — similar to camelCase, but the first word also starts with a capital letter (e.g., `TotalAmount`, `MyClass`). Commonly used for class names in C++.

- **snake_case** — words are all lowercase and separated by underscores (e.g., `total_amount`, `number_of_students`). Often used in C++ for file names or in other languages like Python.
- **SCREAMING_SNAKE_CASE** — like snake_case but all uppercase (e.g., `MAX_SIZE`, `TOTAL_AMOUNT`). Typically used for constants and macros in C++.

- Be descriptive and avoid overly short names (e.g., `numberOfStudents` is better than `n`).
- Avoid using single-letter variable names, except for simple counters (e.g., `i`, `j`, `k`).

Here are some examples of good and bad variable names:

```cpp
// Goodint age = 30;double totalPrice = 150.99;     
 // camelCaseint numberOfStudents = 25;      
  // camelCaseconst int MAX_STUDENTS = 100;   
   // SCREAMING_SNAKE_CASE for constants// Badint a = 30; 
    // Too short and uncleardouble TOTAL_PRICE = 150.99; 
     // Uppercase is not for regular variablesint n = 25;
       // Too short and unclear
```

# Type Casting Part 1

Type casting is the process of converting a value from one data type to another.

In C++, we can convert integers to doubles, doubles to integers, and more. There are two types of casting: **implicit** (automatic) and **explicit** (manual) casting.

For example `Integer to Double`:

Implicit (automatic) casting:

```cpp
int number = 5;double decimal = number;
 // automatically becomes 5.0
 // with calculationint x = 7;double result = x / 2.0;
  // result is 3.5
```

**Note:** When dividing two `int` values, C++ performs **integer division** — the decimal part is discarded. For example, `7 / 2` gives `3`, not `3.5`. To get a decimal result, at least one operand must be a `double` (e.g., `7 / 2.0` gives `3.5`).

Explicit (manual) Casting `Double to Integer`:

```cpp
double decimal = 9.7;int number = (int) decimal; 
 // becomes 9 (decimal part is truncated)
 // with calculationdouble price = 19.99;int roundedPrice = (int) price; 
  // becomes 19
```

**Modern C++ preferred style:** Instead of the C-style cast `(int) decimal`, it is better practice to use `static_cast<>()`, which is safer and more explicit about your intent:

```cpp
double decimal = 9.7;int number = static_cast<int>(decimal); 
 // becomes 9 (decimal part is truncated)double price = 19.99;int roundedPrice = static_cast<int>(price);  
 // becomes 19
```

**Note:** Both `(int) value` and `static_cast<int>(value)` produce the same result here, but `static_cast<>()` is the recommended approach in modern C++ as it makes the conversion clearly visible and is checked by the compilers.

# Type Casting Part 2

In C++, we can convert numbers to strings and vice versa. To convert a value to string, we can use the `std::to_string()` function:

```cpp
int number = 789;
bool isValid = true;
string text1 = to_string(number); 
 // becomes "789"string text2 = isValid ? "true" : "false";  // becomes "true"
```

When you convert a double to a string using `to_string()`, it will by default show 6 decimal places, even if the original number doesn't have that many decimal places.

For example:

```cpp
double n1 = 789.0;string text1 = to_string(n1);
// becomes "789.000000"double n2 = 789.5;string text2 = to_string(n2);
// becomes "789.500000"double n3 = 789.123;string text3 = to_string(n3);
// becomes "789.123000"
```
`String to Integer`:

```cpp
string numberText = "123";
int number = stoi(numberText);  // becomes 123
```

`String to Double`:

```cpp
string decimalText = "45.67";
double decimal = stod(decimalText);  // becomes 45.67
```

Note: When converting strings to numbers, these functions read as many valid characters as possible from the **start** of the string. They only throw an error if the string **begins** with an invalid character:

```cpp
string validStart = "42abc";

int number = stoi(validStart); 
 // becomes 42 (trailing letters ignored)string invalidStart = "abc";int number2 = stoi(invalidStart);
   // This will throw an error
```

# Arithmetic Operators

**Operators** are used to perform operations on values.

First we will discuss the most basic **arithmetic operators**, they may be familiar from math classes.

|Operator|Operation|Example|
|---|---|---|
|+|Addition|3 + 2 = 5|
|-|Subtraction|3 - 2 = 1|
|*|Multiplication|3 * 2 = 6|
|/|Division|4 / 2 = 2|

Let's see usage example,

```cpp
int a = 3;
int b = 5;
int c = a + b; // c holds 8
```

When working with decimal numbers in C++, we use the double data type, which can store numbers with decimal points. The same arithmetic operators (+, -, *, /) work with doubles just like they do with integers:

```cpp
double x = 3.3;
double y = 4.1;
double z = x + y; // z holds 7.4
```

# Modulo Operator

The modulo operator `%` gives the remainder of a division. In C++, it's used with a simple syntax:

```cpp
result = dividend % divisor;
```

- **dividend:** The number being divided.
- **divisor:** The number that divides the dividend.
- **result:** The remainder of the division.

For example:

```cpp
result = 10 % 3;
```

Here, 10 is divided by 3. 3 goes into 10 three times, with a remainder of 1. So, `result` will be 1.

Usually modulo is used for checking if a number is even or odd:

- If a number is even, dividing it by 2 will leave a remainder of 0.
- If a number is odd, dividing it by 2 will leave a remainder of 1.

When working with floating-point numbers (doubles) in C++, you cannot use the modulo operator `%` directly. Instead, you need to use the `fmod()` function from the `<cmath>` library. It works similarly to the modulo operator but keeps the decimal precision. For example:

```cpp
#include <cmath>
double result = fmod(5.2, 2.0);
// result is 1.2
```

Here's how it works: 2.0 goes into 5.2 two times (4.0), and the remainder is 1.2 (5.2 - 4.0 = 1.2).

Another example:

```cpp
double result = fmod(7.8, 3.5);// result is 0.8
```

When the divisor is larger than the dividend, the result equals the dividend. This applies to both `%` and `fmod()`.

```cpp
5 % 10 = 53 % 7 = 3fmod(2.5, 8.0) = 2.5
```

Why? The divisor fits zero times, so the entire dividend is the remainder.

# Increment/Decrement

Increment and decrement operators are used to increase or decrease the value of a variable by 1. These operators are widely used in programming, especially in loops and counters.

The increment operator is represented by two plus signs `++`, and the decrement operator is represented by two minus signs `--`.

For example, to increment a variable named `count`, you can use the increment operator like this:

```cpp
int count = 5;
count++; // count is now 6
```

Similarly, to decrement a variable named `value`, you can use the decrement operator like this:

```cpp
int value = 10;
value--; // value is now 9
```

The `++` and `--` operators are special shortcuts that ONLY work for adding or subtracting 1. There is no `**` or similar operator for multiplication.  
For regular arithmetic operations (like multiplication, division, or adding/subtracting by amounts other than 1), you must use the assignment pattern:

```cpp
int count = 5;
count = count + 3; 
 // Add 3: count is now 8count = count * 2; 
  // Multiply by 2: count is now 16count = count -4; 
   // Subtract 4: count is now 12
```

# Post Increment/Decrement

In the previous lesson, we covered the increment (`++`) and decrement (`--`) operators. These operators have two forms: **prefix** and **postfix**.

Knowing which form to use matters in real programs — for example, when tracking a game score, counting loop iterations, or advancing through a list of items.

The prefix form is written before the variable (e.g., `++x` or `--x`), and the postfix form is written after the variable (e.g., `x++` or `x--`).

The difference between the two forms is subtle but important:

- Prefix form: Increments/decrements the variable and then returns the new value.
- Postfix form: Returns the current value of the variable and then increments/decrements it.

Here's an example to illustrate the difference:

```cpp
int x = 5;
int y = x++;
// y = 5, x = 6 (postfix)int a = 5;
int b = ++a;
// b = 6, a = 6 (prefix)
```

In the first case, `y` is assigned the original value of `x` (5), and then `x` is incremented to 6. In the second case, `a` is incremented first, and then its new value (6) is assigned to `b`.

The same logic applies to the decrement operator:

```cpp
int x = 5;
int y = x--;
// y = 5, x = 4 (postfix)int a = 5;
int b = --a;// b = 4, a = 4 (prefix)
```

# Arithmetic Shortcuts

C++ created a cool shortcut for self-arithmetic operations.

For example instead of writing:

```cpp
int a = 5;
a = a + 3; // a holds 8
```

We can simplify it by writing `+=`:

```cpp
int a = 5;
a += 3;
 // a holds 8
```

The `+=` is adding to `a` **itself** the value `3`

This operation is valid for all arithmetic operations:

|Operator|Shortcut|
|---|---|
|+|+=|
|-|-=|
|*|*=|
|/|/=|
|%|%=|

# Comparison Operators

**Comparison operators** are used to compare between two operands.

Sometimes we need to check whether an operand is bigger/smaller/... than another operand. The following table shows possible operators for comparison:

|Operator|Meaning|Example|
|---|---|---|
|==|Equal|1 == 2 returns false|
|!=|Not Equal|1 != 2 returns true|
|>|Greater Than|1 > 2 returns false|
|<|Lower Than|1 < 2 returns true|
|>=|Greater or Equal|1 >= 2 returns false|
|<=|Lower or Equal|1 <= 2 returns true|

  
The comparison operator returns `true` if the comparison is correct or `false` otherwise.

For example:

```cpp
int var1 = 13;
int var2 = 12;
bool var3 = var1 != var2;
```

`var3` will hold `true` because `var1` and `var2` are not equal

> Remember the `bool` type,  `var3` is a bool.

# String Comparison

In C++, comparing strings can be done in multiple ways. Since`std::string` is a class, it has overloaded operators that make string comparison intuitive and straightforward.

The most common way to compare strings is using comparison operators (==, !=, <, >, <=, >=):

```cpp
string str1 = "hello";string str2 = "hello";
string str3 = "Hello";
bool result1 = (str1 == str2);
  // truebool result2 = (str1 == str3);  // false (case-sensitive)bool result3 = (str1 != str3);  // true
```

You can also use the `compare()` method, which returns `0` if strings are equal, a **negative** integer if the first string is lexicographically smaller, and a **positive** integer if it's larger. Note that the exact value is implementation-defined — it is not necessarily `-1` or `1`:

```cpp
string str1 = "a";
string str2 = "b";
string str3 = "c";
cout << str2.compare(str1) << endl;
 // Positive (b comes after a)cout << str2.compare(str3) << endl;
 // Negative (b comes before c)cout << str2.compare(str2) << endl;
 // 0 (equal strings)
```

# Logical Operators Part 1

**Logical operators** are used to check combinations of comparisons that return `true` or `false`.

For example the following statement contains two comparisons: 

Is 5 greater than 3 **and** less than 6?

| Operator | Meaning                                     | Example  |
| -------- | ------------------------------------------- | -------- |
| `&&`     | And - `true` if **all** operands are `true` | `a && b` |
| `\|'     | Or - `true` if **any** operand is `true`    | `a \| b` |
| `!`      | Not - `true` if the operand is `false`      | `!a`     |

Let's see some examples:

5 is greater than 3 and 1 equals 1:

```cpp
bool b1 = (5 > 3) && (1 == 1); // holds true
```

**Explanation**: All of the operands are `true`, so `b1` will hold `true` (`and` operation is `true` if both operands are `true`) .

5 is not equals 4 or 5 equals 2:

```cpp
bool b2 = !(5 == 4) || (5 == 2); // holds true
```

**Explanation**: The first operand (`5 != 4`) is `true` so `b2` is also `true` (`or` operation is `true` if either one of the operands is `true`)

1 is not equals 1 or false:

```cpp
bool b3 = !(1 == 1) || false; // holds false
```

**Explanation**: All of the operands are `false`, so `b3` will hold `false` (`or` operation).

3 is not greater than 4:

```cpp
bool b4 = !(3 > 4); // holds true
```

**Explanation**: The operand is `false`, so `b4` will hold `true` (`not` operation).

5 is not greater than 10 or 5 is not greater than 1:

```cpp
bool b5 = !(5 > 10 || 5 > 1); // holds false
```

**Explanation**: `5 > 10 || 5 > 1` is `true` (one of the operands is `true`), so in total `b5` is `false` (`not` operation.

# Logical Operators Part 2

Logical operators have a special table called "Truth table" that shows what the combination of logical operators returns.

Truth table for the `and` (`&&`) operator:

|a|b|a && b|
|---|---|---|
|false|false|false|
|false|true|false|
|true|false|false|
|true|true|true|

The only way to get a `true` for the `and` (`&&`) operator is if both `a` and `b` are `true`

Truth table for the `or` (`||`) operator:

|a|b|a \| b|
|---|---|---|
|false|false|false|
|false|true|true|
|true|false|true|
|true|true|true|

In this case, to get a `true` result, either `a` or `b` should be `true`.

Truth table for the `not` (`!`) operator:

|a|!a|
|---|---|
|false|true|
|true|false|

Here the value of `a` is reversed. If `a` is `false` then `!a` is `true`

# Logical Operators Part 3

When checking multiple conditions, the computer stops checking as soon as it knows the final answer (This is called short-circuit evaluation).

For example:

```java
int x = 0;
int y = 5;
bool result = x != 0 && y / x > 2;
```

Here `x` equals `0`, therefore it will not evaluate `y / x > 2`. If we were to reverse the order:

```java
bool result = y / x > 2 && x != 0;
```

This will result in an error because `y` will be divided by 0 which is illegal in math.

This technique is used to optimize the evaluation of logical expressions. For example:

```java
int a = 0;int b = 2;int c = 3;int d = 5;bool result = (a > 0 && b < 2) || (c < -5 && d < 10);
```

In this example, `b < 2` and `d < 10` will not be evaluated because `a > 0` and `c < -5` are both false.
