# Declaring Arrays

An array is a collection of items, and it can contain values of the same type, such as numbers, strings, or even other arrays. Arrays are created using square brackets `[]`, and the items inside the array are separated with commas.

Here is an example of how to create an array:

```cpp
int numbers[] = {1, 2, 3, 4, 5};
```

To check the length of the array, we can use the `std::size()` operator:

```cpp
int length = std::size(numbers)
```

The variable `length` will hold 5 because there are 5 elements in the array.

Another way to create an array using brackets `[]` followed by the array size:

```cpp
int numbers[5];
```

Creates an array of 5 integers, all initialized to 0.

# Accessing Elements

In C++, we use arrays to store multiple values in a single variable. Each value in an array is called an element, and each element has an index.

The indices start from `0` to the length of the array minus one. For example take a look at the next array: 

```cpp
char letters[] = {'a', 'b', 'c', 'd', 'e', 'f', 'g'};
```

- Element `a` is at index 0
- Element `b` is at index 1
- ...
- Element `g` is at index 6

To access an element of an array, we can use its index within square brackets. For example, to access the first element of an array named `letters`, we would use `letters[0]`.

Here's an example:

```cpp
int numbers[] = {10, 20, 30, 40, 50};
int element = numbers[2];
```

The variable `element` will hold the value `30` because it accesses the third element (which has an index of 2).


# Modifying Elements

In addition to accessing the elements of an array, you can also modify them. To modify a specific element in an array, you can assign a new value to it using its index.

Here's an example:

```cpp
std::string my_array[] = {"apple", "banana", "cherry"};
my_array[1] = "orange";
std::cout << my_array[0] << ", " << my_array[1] << ", " << my_array[2] << std::endl;
```

Output:

```cpp
apple, orange, cherry
```

`banana` was changed to an `orange

# Arrays And Functions

Arrays cannot be passed directly to functions as complete arrays. When you try to pass an array to a function, it "decays" into a pointer to its first element.

For example:

```cpp
int numbers[5] = {1, 2, 3, 4, 5};
void processArray(int arr[]) {    
int size = std::size(arr);}
```

`std::size(arr)` won't give you the actual array size. `arr` is actually a pointer here, not an array. Pointers will be learned in the next course.

This is why when passing arrays to functions, we typically need to pass the size as a separate parameter:

```cpp
void processArray(int arr[], int size) {    
// Now we can safely work with the array using the size parameter}
```

Here how to call the function:

```cpp
int numbers[5] = {1, 2, 3, 4, 5};
processArray(numbers, 5);
```

Also it is not possible to return an array in a function:

```cpp
int[] processArray(int arr[]) {    
return arr;}
```

This is illegal. Instead you should use the `*` syntax:

```cpp
int* processArray(int arr[]) {    
return arr;
}int* newArr = processArray(arr);
```

The star `(*)` syntax refers to pointers which will discussed in the next course.


# Enhanced For Loop

The enhanced `for` loop, also known as the for-each loop, provides a simpler way to iterate through arrays. It automatically handles the indexing and retrieval of elements, making the code more readable and less prone to errors.

Here's the basic syntax of an enhanced `for` loop:

```cpp
for (data_type element : array) {    // Code to be executed for each element}
```

- `data_type`: The type of elements in the array.
- `element`: A variable that will hold the current element in each iteration.
- `array`: The array you want to iterate over.

Here's an example:

```cpp
int numbers[] = {1, 2, 3, 4, 5};
for (int number : numbers) {    
std::cout << number << std::endl;}
```

In this example, the loop iterates over the `numbers` array. In each iteration, the current element is assigned to the `number` variable, and the code inside the loop is executed. The output will be:

```cpp
1
2
3
4
5
```

The enhanced `for` loop is especially useful when you need to access each element in an array without modifying the array itself.


# Common Array Operations

Here are some common array operations:

- Find the **sum** of all elements in an array:

```cpp
int numbers[] = {1, 2, 3, 4, 5};
int sum = 0;
for (int number : numbers) {   
 sum += number;}std::cout << "Sum: " << sum;
```

- Find the **average** of elements in an array:

```cpp
int numbers[] = {1, 2, 3, 4, 5};
double sum = 0;
for (int number : numbers) {    
sum += number;
}double average = sum / std::size(numbers);
std::cout << "Average: " << average;
```

- Find the **maximum** element in an array:

```cpp
int numbers[] = {1, 5, 2, 9, 3};
int max = numbers[0];
for (int i = 1;
 i < std::size(numbers); i++) {   
  if (numbers[i] > max) {        
  max = numbers[i];
      }
      }std::cout << "Max: " << max;
```

- Find the **minimum** element in an array:

```cpp
int numbers[] = {1, 5, 2, 9, 3};
int min = numbers[0];
for (int i = 1; i < std::size(numbers);
 i++) {    
 if (numbers[i] < min) {        
 min = numbers[i];
     }
     }std::cout << "Min: " << min;
```

# C-style Strings Part 1

C-style strings are created with the char type instead of string. They end with a special character called the null character (`'\0'`).

This character marks the end of the string. C-style strings are often referred to as "null-terminated strings."

For example a simple declaration:

```cpp
char str1[] = "Hello";
```

`str1` is declared without a specific size. The compiler automatically determines the size based on the initializer (including the null character).

Example of explicitly initialize with characters:

```cpp
char str2[6] = {'W', 'o', 'r', 'l', 'd', '\0'};
```

`str2` is declared with a size of 6 and explicitly initialized with characters, including the null character at the end.

Example of partly initialized:

```cpp
char str3[10] = "Coddy";
```

`str3` is declared with a size of 10, but only the first 6 characters are initialized. The rest of the array is filled with null characters.

To use C-style strings we need to include it:

```cpp
#include <cstring>
```

After the include, we can use the strlen function to get the length of a C-style string:

```c
std::cout << strlen(str1); // Output: 5
```
# C-style Strings Part 2

It's important to remember that when you declare a C-style string with a specific size, you need to allocate enough space for the characters you want to store, plus one extra space for the null character.

For example:

```cpp
// Correct: "Hello" needs 6 spaces// (5 letters + '\0')
char str1[6] = "Hello";
```

```cpp
// Wrong: Array too small!
// "Hello" needs 6 spaces, but only 5 given
char str2[5] = "Hello";// This might cause problems
```

```cpp
// Correct: Extra space is fine// More than enough space (10 > 6 needed)
char str3[10] = "Hello";
```

```cpp
// Example showing character 
count:char name[5] = "John";
  // Needs 5 spaces:// J + o + h + n + '\0' = 5 characters
```

You can access individual characters in a C-style string using array notation:

```cpp
char str[] = "Hello";
char first = str[0]; // 'H'char third = str[2]; // 'l'
```

You can also modify characters in a C-style string, as long as you don't exceed the bounds of the array:

```cpp
char str[] = "Hello";
str[0] = 'J';std::cout << str; // Outputs "Jello"
```

However, you cannot directly assign a new string to a C-style string after it's declared. You'll need to use functions like `strcpy` to copy strings, which we'll cover in later lessons.

# String Operations

In C++, you can concatenate strings using the `+` operator or the `+=` operator.

For example:

```cpp
std::string str1 = "Hello";
std::string str2 = "World";
std::string result = str1 + " " + str2;
// Concatenates str1, a space, and str2
std::cout << result;// Outputs: Hello World
```

You can also use the `+=` operator to append one string to another:

```cpp
std::string str = "Hello";
str += " ";str += "World";
std::cout << str;// Outputs: Hello World
```

Here, we start with the string "Hello" and append a space and then "World" using the `+=` operator.

Another common string operation is finding the length of a string. In C++, you can use the `length()` or `size()` method to get the number of characters in a string: 

```cpp
std::string str = "Hello";
int len = str.length(); // Or str.size();
std::cout << len; // Outputs: 5
```

The `length()` and `size()` methods return the same value - the number of characters in the string.

# String Functions Part 1

Here are some useful functions in strings:

- `insert(pos, str)`: Inserts the string `str` at position `pos` in the current string.

- `replace(pos, len, str)`: Replaces `len` characters starting at position `pos` with the string `str`.

- `substr(pos, len)`: Returns a substring of the current string, starting at position `pos` and having length `len`.

- `append(str)`: Adds the string `str` to the end of the current string.

For example using the following string:

```cpp
std::string str = "Hello, World!";
```

```cpp
str.insert(5, " C++");// Output: "Hello C++, World!"
```

```cpp
str.replace(7, 5, "Universe");// Output: "Hello, Universe!"
```

```cpp
str.substr(0, 5);// Output: "Hello"
```

```cpp
str.substr(7, 5);// Output: "World"
```

```cpp
str.substr(7);// Output: "World!"
```

```cpp
str.append(" This is universe");// Output: "Hello, World! This is universe"
```

# String Functions Part 2

Here are more useful functions for strings:

- erase(pos, len): Removes len characters starting at position pos from the current string.

- find(str): Returns the position of the first occurrence of str in the current string. Returns some object that can be compared to -1 if not found.

- clear(): Removes all characters from the string, making it empty.

- empty(): Returns true if the string is empty, false otherwise.

For example using the following string:

```cpp
std::string str = "Hello, World!";
```

```cpp
int pos = str.find("World");// Output: pos = 7 (position where "World" starts)
```

```cpp
str.erase(5, 2);// Output: "HelloWorld!"
```

```cpp
str.clear();// Output: "" (empty string)
```

```cpp
bool isEmpty = str.empty();// Returns true if str has no characters
```
# Number Pattern

When creating patterns like pyramids, we often need to create strings with repeated characters. Here's a useful technique to create such strings:

```cpp
std::string str(10, 'a');
```

In this example, `str` will hold 10 occurrences of `a`: `"aaaaaaaaaa"`

Let's break down how this works: 

1. `std::string str` declares a string variable named `str`
2. `(10, 'a')` the constructor of string that creates a string with 10 times the char `'a'`