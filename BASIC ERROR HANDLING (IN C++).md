# Introduction to Exceptions

When programs run, things don't always go as planned. Files might not exist, users might enter invalid input, or calculations might fail. These unexpected situations are called **exceptions**, and they can cause your program to crash if not handled properly.

Exception handling is a programming technique that allows you to gracefully respond to errors instead of letting your program terminate unexpectedly. Rather than crashing when something goes wrong, you can catch these errors and decide how to handle them - whether that's showing a helpful message to the user, trying an alternative approach, or safely shutting down.

Consider what happens when you try to convert invalid text to a number, or when you attempt to access a file that doesn't exist. Without exception handling, these situations would cause your program to stop abruptly. With proper error handling, you can anticipate these problems and provide a smooth user experience even when things go wrong.

C++ provides a structured way to handle exceptions using the `try-catch` mechanism, which allows you to separate your normal program logic from your error-handling code. This makes your programs more robust and user-friendly, essential qualities for any reliable software.

# The 'try' and 'catch' Blocks

==The `try` and `catch` blocks work together to create a safety net for your code. You place potentially risky code inside a `try` block, and if an exception occurs, the program jumps to the corresponding `catch` block to handle the error gracefully.

Here's the basic syntax structure:

```cpp
try {    // Code that might throw an exception} catch (exception_type e) {    // Code to handle the exception}
```

A practical example involves converting strings to numbers using `std::stoi`, which can throw an `std::invalid_argument` exception if the string contains non-numeric characters:

```cpp
try {    std::string input = "abc";    
int number = std::stoi(input);  
// This will throw an exception    
std::cout << "Number: " << number << std::endl;
} catch (std::invalid_argument& e) {    
std::cout << "Invalid input! Please enter a valid number." << std::endl;
}
```

When the exception occurs in the `try` block, the program immediately stops executing the remaining code in that block and jumps to the `catch` block. This prevents your program from crashing and allows you to provide meaningful feedback to users when things go wrong.

# The 'throw' Keyword

Sometimes you need to signal that an error has occurred in your own code, rather than just catching exceptions thrown by other functions. The `throw` keyword allows you to manually trigger an exception when your program detects a problem.

You can throw different types of values as exceptions - integers, strings, or even custom objects. Here's the basic syntax:

```cpp
if (someErrorCondition) {    
throw "Error message";  // Throws a string literal}
```

When you use `throw`, the program immediately stops executing the current function and looks for a `catch` block that can handle the thrown value. This is particularly useful for validating input or checking conditions that shouldn't occur during normal program execution.

Here's a practical example of throwing an exception when detecting invalid input:

```cpp
void checkAge(int age) {
    if (age < 0) {        
    throw "Age cannot be negative!";
        }    std::cout << "Age is valid: " << age << std::endl;
        }
```

The `throw` keyword gives you control over when and how errors are reported in your programs, making your functions more robust and predictable when dealing with invalid conditions.

# Different Exception Types

Real-world programs often encounter different types of errors that require different handling approaches. Instead of using a single `catch` block for all exceptions, you can create multiple `catch` blocks to handle specific exception types differently.

When you have multiple `catch` blocks, C++ will check them in order from top to bottom and execute the first one that matches the thrown exception type:

```cpp
try {    
// Code that might throw different types of exceptions} 
catch (std::invalid_argument& e) {    
std::cout << "Invalid input format!" << std::endl;
} catch (std::out_of_range& e) {    
std::cout << "Number is too large!" << std::endl;
} catch (const char* msg) {    
std::cout << "Custom error: " << msg << std::endl;
}
```

This approach allows you to provide specific, meaningful responses to different error conditions. For example, when converting user input to numbers, you might catch `std::invalid_argument` for non-numeric text and `std::out_of_range` for numbers that are too large to fit in the target data type.

The order of `catch` blocks matters - place more specific exception types first, followed by more general ones. This ensures that each exception is handled by the most appropriate block, giving users clear feedback about what went wrong and how they might fix it.
