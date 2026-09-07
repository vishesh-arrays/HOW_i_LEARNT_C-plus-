# If Statement

If statements allow us to execute code with conditions.

For example, let's look at the following code:

```cpp
int age = 20;
std::string status = "Child";
if (age > 18) {    status = "Adult";
}age += 1;
```

The above code checks whether the `age` variable is bigger than `18`. If it is, it will set `status` to hold `"Adult"` string.

In the end, the code will increment `age` by `1` whether the age is bigger than 18 or not.

**To use an `if` statement in C++, we need to use curly braces `{}` to define the code block, and everything inside the if statement should be placed between these braces:

```cpp
if (condition) {   
 code;    
 code;    
 code;}
```

If the condition is `true`, we will enter the code block inside the if (The indented code)

# If - Else

`if` allows us to execute particular code if a condition is met, but what if we want to execute something else if the condition is not met?

For that we have the `else` statement:

```cpp
int age = 15;
std::string status = "None";
if (age >= 18) {    status = "Adult";
} else {    status = "Young";
}
```

In the above example, `age` is smaller than `18` which means it enters the else code and `status` will hold `"Young"`.

We can even make it more profound using the `else if` statement:

```cpp
int age = 68;
std::string status = "None";
if (age < 18) {    status = "Young";
} else if (age >= 18 && age <= 65) {    status = "Adult";
} else {    status = "Old";}
```

Here it checks whether age is smaller than 18, if not it will continue to the next condition and check whether age is between 18 and 65. If that condition is also not met it will set `status` to `"Old"`.

We can add as many `else if` statements as we want:

```cpp
if (condition1) {    
code;} else if (condition2) {
    code;} else if (condition3) {
        code;}...
```
# Switch Statement

The `switch` statement is like a multi-way `if` statement. Instead of evaluating a single condition, it checks the value of a variable against multiple cases and executes the code associated with the matching case.

Here's the basic structure of a `switch` statement:

```cpp
switch (variable) {    
case value1:    
    // Code to execute if variable equals value1   
         break;    
         case value2:  
 // Code to execute if variable equals value2
         break;    
         // ... more cases    
         default:        
         // Code to execute if no case matches}
```

- The `switch` keyword is followed by the variable you want to test in parentheses.
- Each `case` represents a possible value of the variable.
- The code inside each `case` is executed if the variable matches that case's value.

- The `break` statement is crucial; it exits the `switch` after a case is executed. Without it, execution would "fall through" to the next case.
- The `default` case is optional and is executed if no other case matches.

Here's an example:

```cpp
int day = 3;
std::string dayName;
switch (day) {    
case 1:        
dayName = "Monday";        
break;    
case 2:        
dayName = "Tuesday";        
break;    
// ... cases for other days    
default:        
dayName = "Invalid day";}
```

You can also combine multiple cases into one:

```cpp
int day = 3;
std::string dayName;
switch (day) {    
case 1:    
case 2:    
case 3:        
dayName = "Start of week";        
break;    
// ... cases for other days    
default:        
dayName = "Invalid day";}
```

# Conditional Operator

The conditional operator is a simple one-line `if-else` statement. It has the following syntax:

```cpp
variable = (condition) ? value_if_true : value_if_false;
```

The conditional operator evaluates the condition. If it's `true`, it assigns `value_if_true` to the variable; otherwise, it assigns `value_if_false`.

For example:

```cpp
int age = 20;
std::string message = (age >= 18) ? "Adult" : "Minor";
```

In this example, since `age` is greater than or equal to 18, `message` will be assigned the value `"Adult"`. If `age` were less than 18, `message` would be assigned `"Minor"`.

You can stack as many conditions as you like:

```cpp
vrbl = (cond1) ? val1 : (cond2) ? val2 : val3;
```

For example:

```cpp
int score = 100;
std::string result = (score == 100) ? "Perfect!" : (score >= 90) ? "Excellent" : "Good";
```

In this example, since `score == 100` is true, `result` will be assigned `"Perfect!"`. If the score were 95, it would be assigned `"Excellent"`.

# Nested If - Else

We can nest `if-elif-else` statements within each other. This allows us to create hierarchical decision-making structures.

For example:

```cpp
if (age > 18) {    
if (hasLicense) {        
std::cout << "You can drive";
    } else {       
     std::cout << "Get a license first";    
     }
     } else {   
      std::cout << "Too young to drive";
      }
```

It can be infinitely nested:

```cpp
if (condition1) {    
if (condition2) {        
if (condition3) {           
 // if condition1, condition2 and condition3 are true        }  
   }
   }
```
