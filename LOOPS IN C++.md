# For Loop Part 1

Sometimes when programming, it's necessary to perform the same or almost the same operation a couple of times.

To prevent writing the same thing over and over again, we can use **Loops**.

The `for` loop has the following syntax:

```cpp
for (initialization; condition; update) {   
 code}
```

The `initialization`, `condition` and `update` determine what is the `start` value and what is the `end` value.

For example, loop from 0 to 5 (not including):

```cpp
for (int i = 0; i < 5; i++) {    
std::cout << i << std::endl;}
```

It will execute the print statement 5 times:

```cpp
01234
```

In this loop the starting value is 0 (like `int i = 0`), the condition checks if the loop should continue (like `i < 5`), and the update changes the value after each iteration (like `i++`).

Loops have many use cases. For example, let's sum all the numbers from 1 to 100:

```cpp
int sum_numbers = 0;
for (int i = 1; i <= 100; i++) {
    sum_numbers += i;
    }std::cout << sum_numbers;
```

This will first loop through all numbers between 1 and 100 (including 100 because of `<=` sign) and sum all of them, then it will print the `sum_numbers` variable

# While Loop

A `while` loop is different from the `for` loop. A `for` loop is commonly used to iterate over a specific `range`, whereas a `while` loop allows us to keep iterating as long as a certain **condition** is met.

To use a `while` loop write:

```cpp
while (condition) {  
  code}
```

The code will execute only if the condition is `true`.

Note: if the loop body contains only a single statement, the curly braces are optional:

```cpp
while (condition)    code;
```

There are many use cases where a `while` would solve the problem, but the `for` loop would not. Keep in mind, however, that a `for` loop is not strictly limited to iterating over a range — its initialization and update steps are optional, so both loop types can be made to behave similarly.

# Do While Loop

The `do-while` loop is similar to the `while` loop, but with one key difference: the code block is executed **at least once** before the condition is checked. This means that the loop's body will always run the first time, regardless of whether the condition is true or false.

Here's the basic structure of a `do-while` loop:

```cpp
do {    // Code to be executed} while (condition);
```

The `do` keyword marks the beginning of the loop, followed by the code block in curly braces. After the code block, the `while` keyword introduces the condition. The loop will continue to execute as long as the condition is `true`.

Here's an example:

```cpp
int count = 0;do {    std::cout << "Count: " << count << std::endl;
    count++;
    } while (count < 5);
```

In this example, the code inside the `do` block will execute first, printing "Count: 0" and incrementing `count` to 1. Then, the condition `count < 5` is checked.

Since it's `true`, the loop continues. This process repeats until `count` becomes 5, at which point the condition becomes `false` and the loop terminates.

The output of this code will be:

```cpp
Count: 0Count: 1Count: 2Count: 3Count: 4
```

# Break

The `break` statement stops the loop instantly when it's encountered.

For example,

```cpp
for (int i = 0; i < 10; i++) {
    if (i == 6) {        break;
        }    std::cout << i << std::endl;
        }
```

In the following example the loop iterates regularly until it reaches number 6. Then the program enters the `if` statement and executes the `break` statement. This **exits** the loop immediately. The output is:

```cpp
012345
```

# Continue

The `continue` statement stops the current iteration and continues to the next iteration. For example:

```cpp
for (int i = 3; i < 9; i++) {    
if (i == 5) {        
continue;    
}    
std::cout << i << std::endl;}
```

The loop will iterate through all of the numbers. When it reaches ⁣`i=5` it will skip that iteration and continue to the next one. The output is:

```cpp
34678
```

Notice, number 5 is not in the output.

# For Loop Part 2

Let's explore some cool variations of the for loop condition

Counting Backwards:

```cpp
for (int i = 10; i >= 0; i--) {    std::cout << i << " ";
}// Output: 10 9 8 7 6 5 4 3 2 1 0
```

Notice how we start with a higher number (`i = 10`), Use `i >= 0` as our condition and use `i--` to decrease the counter

Want to skip numbers? Just change the increment/decrement value:

```cpp
// Counting up by 2s
for (int i = 0; i <= 10; i+=2) {    
std::cout << i << " ";
}// Output: 0 2 4 6 8 10
```

```cpp
// Counting down by 2s
for (int i = 10; i >= 0; i-=2) {
    std::cout << i << " ";
    }// Output: 10 8 6 4 2 0
```

You can even use multiple variables in your loop control:

```cpp
for (int i = 0, j = 10; i <= 10; i++, j--) {    std::cout << "i = " << i << " "  << "j = " << j << " "; 
   }// Output: i = 0 j = 10
   //         i = 1 j = 9
   //         i = 2 j = 8// And so on...
```

In this example, we have two counter variables, `i` and `j`, initialized to 0 and 10, respectively. In each iteration, `i` is incremented by 1 and `j` is decremented by 1. The loop continues as long as i is less than or equal to 10.

# Nested Loops

A nested loop is simply a loop inside another loop. The inner loop will complete all its iterations for each single iteration of the outer loop.

A good analogy for this is a clock: for each hour (outer loop), the minute hand (inner loop) must complete its full 60-minute cycle.

Example of a nested loop:

```cpp
for (int x = 0; x < 2; x++) {    
for (int y = 0; y < 2; y++) {        
std::cout << x << " " << y << std::endl;
    }
    }// This will output:// 0 0// 0 1// 1 0// 1 1
```

The outer loop (x) runs twice, and for each of those times, the inner loop (y) runs twice.


# Infinite Loops

An infinite loop is a loop that never stops because its condition is always true, or there's no condition to stop it. While sometimes useful, they often lead to programs freezing or crashing. It's like a dog chasing its tail forever - it just keeps going and going without end.

Here's a simple example of an infinite loop using a `while` loop:

```cpp
while (true) {    std::cout << "This will print forever!" << std::endl;
}
```

In this case, the condition is always `true`, so the loop will run indefinitely.

You can also create an infinite loop with a `for` loop by leaving out the condition:

```cpp
for (;;) {    std::cout << "This will also print forever!" << std::endl;
}
```

Here, there's no condition to check, so the loop has no reason to stop.

Infinite loops can be useful in some cases, like in servers that need to keep running until manually stopped. However, in most cases, they are problematic. To stop an infinite loop, you usually have to force-quit the program (e.g., by pressing Ctrl+C in the terminal).

