# Pass by Reference

When you pass arguments to functions, C++ normally creates copies of the values. This means changes inside the function don't affect the original variables. Pass by reference changes this behavior by allowing functions to work directly with the original variables.

To pass by reference, add the `&` symbol after the parameter type in your function declaration:

```cpp
void doubleValue(int& number) {    
number = number * 2;  // Modifies the original variable}
```

==When you call this function, any changes made to the parameter inside the function will directly modify the original variable that was passed in. This is particularly useful when you want a function to modify its arguments or when working with large objects where copying would be inefficient.

Pass by reference eliminates the overhead of copying data, making your programs faster and more memory-efficient, especially with complex data structures like vectors or maps.

# Intro Lambda Expressions

Lambda expressions are a powerful C++ feature that allows you to create small, anonymous functions right where you need them. Think of them as mini-functions that you can define and use without having to write a separate function declaration.

**==The basic syntax for a lambda expression follows this pattern: `[](){}`. The square brackets `[]` are called the **capture clause**, the parentheses `()` hold parameters (just like regular functions), and the curly braces `{}` contain the function body.

  
The capture clause controls which variables from the surrounding scope the lambda can use. The most common forms are:  
  
==`[=]` — capture all local variables **by value** (the lambda gets its own copy)  
`[&]` — capture all local variables **by reference** (the lambda accesses the originals)  
`[]` — capture nothing (the lambda cannot use any outside variables)

Here's how to create and call a simple lambda:

```cpp
auto myLambda = []() {    std::cout << "Hello from Lambda!" << std::endl;
};
myLambda();  // Call the lambda function
```

You can also define and execute a lambda immediately without storing it in a variable:

```cpp
[]() {    std::cout << "Immediate execution!" << std::endl;
}();
```

Lambda expressions are particularly useful for short, one-time functions that you don't want to define separately. They make your code more concise and keep related logic close together.


# Lambdas with Parameters

Now that you understand basic lambda syntax, let's make lambdas more useful by adding parameters. Just like regular functions, lambdas can accept input values to work with.

To add parameters to a lambda, place them inside the parentheses after the capture clause:

```cpp
auto addNumbers = [](int a, int b) {    
std::cout << "Sum: " << (a + b) << std::endl;
};
addNumbers(5, 3);  // Prints: Sum: 8
```

The parameter syntax works exactly like regular function parameters - you specify the type followed by the parameter name. You can have multiple parameters separated by commas, just as shown above.

You can also call a lambda with parameters immediately without storing it:

```cpp
[](int x, int y) {    
std::cout << "Product: " << (x * y) << std::endl;
}(4, 7);  // Prints: Product: 28
```

This ability to accept parameters makes lambdas much more flexible and reusable, allowing you to create small functions that can process different input values each time they're called.

# Lambdas with Return Values

Lambda expressions become much more powerful when they can return values back to the calling code. Instead of just performing actions, lambdas can calculate results and pass them back, just like regular functions.

To specify a return type for a lambda, use the arrow syntax `-> type` after the parameter list:

```cpp
auto multiply = [](int a, int b) -> int {    
return a * b;};
int result = multiply(4, 5);  // result is 20
```

The return type specification is optional when the compiler can deduce it automatically, but it's good practice to include it for clarity. You can store the returned value in a variable or use it directly in expressions.

This capability makes lambdas perfect for small calculations that you need to perform inline without creating separate functions. Whether you're computing mathematical operations, string manipulations, or simple data transformations, returning values from lambdas keeps your code concise and readable.


# Introduction to Recursion

Recursion is a programming technique where a function calls itself to solve a problem. Instead of using loops, recursive functions break down complex problems into smaller, similar subproblems until they reach a simple case that can be solved directly.

Every recursive function must have two essential components. The **base case** is a condition that stops the recursion - without it, the function would call itself forever. The **recursive step** is where the function calls itself with modified parameters, moving closer to the base case with each call.

Here's a simple countdown example that demonstrates recursion:

```cpp
void countdown(int n) {    if (n <= 0) {          
 // Base case: stop when n reaches 0        
 std::cout << "Done!" << std::endl;        
 return;    }        
 std::cout << n << std::endl;
     countdown(n - 1);       // Recursive step: call with n-1}
```

When you call `countdown(3)`, it prints 3, then calls `countdown(2)`, which prints 2, then calls `countdown(1)`, and so on until it reaches the base case. Each function call waits for the next one to complete before finishing, creating a chain of calls that eventually unwinds back to the original caller.

# Recursive Factorial

The factorial of a number is a perfect example to demonstrate recursion in action. The factorial of n (written as n!) is the product of all positive integers from 1 to n. For example, 5! = 5 × 4 × 3 × 2 × 1 = 120.

What makes factorial ideal for recursion is that it can be defined in terms of itself: n! = n × (n-1)!. This means to calculate 5!, you multiply 5 by 4!, and to calculate 4!, you multiply 4 by 3!, and so on.

Here's how a recursive factorial function looks:

```cpp
int factorial(int n) {    
if (n <= 1) {          
 // Base case: 0! and 1! both equal 1        
 return 1;    }        
 return n * factorial(n - 1); 
  // Recursive step: n! = n × (n-1)!}
```

The base case stops the recursion when n reaches 1 or 0, returning 1. The recursive step multiplies the current number by the factorial of the next smaller number. When you call `factorial(4)`, it calculates 4 × 3 × 2 × 1 by making successive calls until it reaches the base case, then multiplies all the results together as the calls return.


