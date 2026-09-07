# Declare a Function

A function is a sequence of code that has a name. The purpose of a function is to reuse a piece of code multiple times.

For example, take a look at this code:

```cpp
std::cout << "Welcome to Coddy";
std::cout << "New session...";
std::cout << "Welcome to Coddy";
std::cout << "Another session...";
std::cout << "Welcome to Coddy";
```

We use the same code `std::cout << "Welcome to Coddy";` over and over again. Another issue with this code is that if we wanted to change the message: `Welcome to Coddy` to something different, like `"Welcome aboard"` it would have to change 3 different lines of code. To solve this issue, we will use functions.

To declare a function, we use the following syntax:

```cpp
access_modifier return_type function_name(parameters) {    // code}
```

For our example, we will create a function named `greet` and it will look like this:

```cpp
void greet() {    std::cout << "Welcome to Coddy";
}
```

To use/call/execute the function, we write `greet();`:

```cpp
int main() {    greet();
    std::cout << "New session...";
    greet();    std::cout << "Another session...";    
            greet();    return 0;}
```

This will result in the same output as above.

> **Important!** The function code **must** come before its call/execution

**The `void` keyword indicates the function doesn't return a value.


# Parameters

An argument in a function is a value that you pass into the function when you call it. To add arguments to a function we write them inside the parenthesis `()`:

```cpp
return_type method_name(data_type arg1, data_type arg2, ...) {    // code}
```

We can name the arguments as we want and we can write as many arguments as we need, as long as the names follow standard variable naming rules: they must start with a letter or underscore, and can only contain letters, digits, and underscores — no special characters like `/`, `&`, or `!`.

To call a function and pass arguments to it we write:

```cpp
method_name(value1, value2, value3, ...);
```

> Passing too many arguments to a function that is expecting less arguments will cause the program to fail

Example of usage:

```cpp
void isEven(int number) {    
if (number % 2 == 0) {        
std::cout << number << " is even" << std::endl;
    } else {        
    std::cout << number << " is odd" << std::endl;
        }}int main() {    
        for (int i = 15; i < 34; i++) {
                isEven(i);    }
                    for (int i = 153; i < 219; i++) {        isEven(i);    } 
                       return 0;}
```

Here we have a function called `isEven` that accepts one argument called `number` and prints whether the number is even or odd.

Then we call the function twice: once for all the numbers between 15 and 34, and second time for all numbers between 153 and 219.

# Return Types

The `return` statement in a function is used to specify the value or values that the function should produce as its output. For example, the following function will output `100`:

```cpp
int functionName() {    
return 100;}
```

To pass the value to a variable, write:

```cpp
int number = functionName();
```

Now the `number` variable will hold `100` because this is what the function returned.

> Note that the return type of the function (int in this case) must match the data type of the variable where you're storing the returned value.

# Function Overloading

Function overloading is a feature in C++ where two or more functions can have the same name but different parameters. When you call an overloaded function, the C++ compiler determines the most appropriate definition to use by comparing the argument types you've used in the call with the parameter types specified in the definitions. If no matching function is found, the compiler will generate an error.

Here's an example of function overloading:

```cpp
int add(int a, int b) {    
return a + b;}
double add(double a, double b) {    
return a + b;
}int main() {    
int sum1 = add(5, 3);
 // Calls the first version of add    
 double sum2 = add(2.5, 3.7);
  // Calls the second version of add    
  return 0;}
```

In this example, we have two functions named `add`. One takes two `int` parameters, and the other takes two `double` parameters. Depending on the types of the arguments we pass to `add`, the appropriate version of the function is called.

It's important to note that the return type alone is not sufficient to overload a function. The functions must differ in their parameter lists.
# Void Functions

In C++, a `void` function is a function that does not return any value. When you declare a function as `void`, it indicates that the function performs a task or a set of operations, but it does not produce a result that needs to be returned to the caller. `void` functions are used when you want to perform actions like printing output, modifying object states, or executing a sequence of statements without returning a specific value.

Here's the basic structure of a `void` function:

```cpp
void functionName(parameters) {    // Code to be executed
}
```
