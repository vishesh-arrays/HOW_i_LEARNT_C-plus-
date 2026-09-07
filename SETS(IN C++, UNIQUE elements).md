
# Introducing std::set

A `std::set` is a container that stores a collection of unique elements in sorted order. Unlike vectors or arrays where you can have duplicate values, a set automatically prevents duplicates and keeps everything organized.

Think of a set like a collection of unique items on your desk - you can't have two identical items in the same spot, and they're naturally arranged in order. This makes sets perfect when you need to ensure no duplicates exist in your data.

To use `std::set` in your program, you need to include the appropriate header:

```cpp
#include <set>
```

Here's a simple example of declaring a set:

```cpp
std::set<int> numbers;
```

This creates an empty set that can hold integers. The set will automatically sort any numbers you add to it and reject duplicates, making it an excellent choice for maintaining collections of unique, ordered data.

# Create Set & Add Elements

Now that you know what a set is, let's learn how to create one and add elements to it. To add elements to a `std::set`, you use the `.insert()` method.

Here's how to create an empty set and add elements:

```cpp
std::set<int> numbers;
numbers.insert(5);
numbers.insert(2);
numbers.insert(8);
```

The most important feature of sets is that they automatically reject duplicates. If you try to insert the same value twice, the set remains unchanged:

```cpp
numbers.insert(5);
  // This won't add another 5
  numbers.insert(5);  // Neither will this
```

After all these insertions, your set will only contain three unique elements: 2, 5, and 8 (automatically sorted). The duplicate attempts to insert 5 are simply ignored, which is exactly what makes sets so useful for maintaining collections of unique data.


# Checking for Elements

When working with sets, you often need to check whether a specific element exists before performing operations on it. The `.count()` method provides a simple way to verify if an element is present in your set.

Just like with maps, the `.count()` method returns 1 if the element exists in the set, and 0 if it doesn't. This makes it perfect for conditional checks:

```cpp
std::set<int> numbers = {10, 20, 30};
if (numbers.count(20)) {    
std::cout << "Found 20 in the set!" << std::endl;
} else {    
std::cout << "20 is not in the set" << std::endl;
}
```

This approach is much safer than trying to access elements directly, especially when you're not sure if they exist. You can use `.count()` to validate user input, prevent errors, or make decisions based on what's currently stored in your set.


# Removing Elements

Sometimes you need to remove elements from a set when they're no longer needed. The `.erase()` method allows you to remove a specific element by providing its value.

Here's how to remove an element from a set:

```cpp
std::set<int> numbers = {10, 20, 30, 40};
numbers.erase(20);  // Removes the element 20
```

After calling `.erase(20)`, the set will only contain {10, 30, 40}. If you try to erase an element that doesn't exist in the set, nothing happens - the set remains unchanged and no error occurs.

This makes `.erase()` safe to use even when you're not certain the element exists. It's particularly useful for maintaining clean collections where you need to remove specific items based on user input or program logic.

# Iterating Over a Set

Now that you can add, check, and remove elements from a set, let's learn how to iterate through all elements in a set. The range-based for loop provides the cleanest way to visit each element.

Here's how to iterate through a set:

```cpp
std::set<std::string> fruits = {"banana", "apple", "cherry"};
for (const std::string& fruit : fruits) {    
std::cout << fruit << std::endl;
}
```

The most important feature to remember is that sets automatically maintain sorted order. When you iterate through the fruits set above, the output will be "apple", "banana", "cherry" - not the order you inserted them. This automatic sorting is one of the key advantages of using `std::set`.

This sorted iteration makes sets perfect for displaying data in alphabetical or numerical order without needing to sort manually. Whether you're working with numbers, strings, or other comparable types, the set will always present them in their natural sorted sequence.