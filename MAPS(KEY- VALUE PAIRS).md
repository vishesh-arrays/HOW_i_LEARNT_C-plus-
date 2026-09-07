# Introducing std::map

While vectors are excellent for storing collections of similar items, sometimes you need to associate one piece of data with another. This is where `std::map` becomes invaluable - it's a container that stores elements as key-value pairs.

Think of a map like a dictionary where each word (the key) has a corresponding definition (the value). In programming, you might use a map to store student names paired with their test scores, or product names paired with their prices. The key allows you to quickly look up its associated value.

To use `std::map` in your C++ programs, you need to include the `<map>` header at the top of your file:

```cpp
#include <map>
```

Maps are particularly useful when you need fast lookups based on a specific identifier, making them perfect for scenarios where you want to retrieve information using a meaningful key rather than a numeric index.


# Creating a Map

Now that you understand what a map is, let's learn how to create one and add key-value pairs to it. When declaring a `std::map`, you need to specify both the key type and the value type using angle brackets.

Here's the basic syntax for creating a map:

```cpp
std::map<KeyType, ValueType> mapName;
```

For example, to create a map that stores student names as keys and their test scores as values:

```cpp
std::map<std::string, int> studentScores;
```

To add elements to your map, you can use the square bracket notation with the key, then assign a value:

```cpp
studentScores["Alice"] = 95;
studentScores["Bob"] = 87;
studentScores["Carol"] = 92;
```

This creates three key-value pairs in the map. Each student's name serves as the key that allows you to quickly retrieve their corresponding score.

To iterate over all entries in a map, use a **range-based for loop** with `auto`. Each element in a `std::map` is a key-value pair, so you access the key with `.first` and the value with `.second`:

```cpp
for (const auto& pair : studentScores) {    
std::cout << pair.first << ": " << pair.second << std::endl;
}
```

Here, `auto` automatically deduces the type of each element, `pair.first` gives the key (student name), and `pair.second` gives the value (score). Note that `std::map` always iterates in **sorted order by key**.


# Accessing and Modifying Values

Once you have a map with key-value pairs, you'll often need to retrieve or update the values stored in it. The square bracket `[]` operator provides a convenient way to both access existing values and modify them.

To access a value, simply use the key inside square brackets:

```cpp
std::map<std::string, int> scores;
scores["Alice"] = 95;
int aliceScore = scores["Alice"]; // Gets 95
```

The same syntax works for updating existing values:

```cpp
scores["Alice"] = 98; // Updates Alice's score to 98
```

Here's an important behavior to remember: if you use the `[]` operator with a key that doesn't exist in the map, it automatically creates a new element with that key and initializes it with a default value (0 for integers, empty string for strings, etc.).

```cpp
int bobScore = scores["Bob"]; // Creates "Bob" with value 0
```

This automatic creation feature makes the `[]` operator very convenient for both reading and writing map data, as you don't need to check if a key exists before using it.

You can also iterate through all key-value pairs in a map using a range-based `for` loop. Each element in the map is a **pair**, where `pair.first` holds the key and `pair.second` holds the value:

```cpp
for (auto pair : scores) {    
std::cout << pair.first << ": " << pair.second << std::endl;
}
```

This will print every key-value pair stored in the map, one per line.

# Checking for Keys

While the square bracket operator is convenient for accessing map values, there's a potential problem: what happens if you try to access a key that doesn't exist? As you learned in the previous lesson, using `[]` with a non-existent key automatically creates that key with a default value.

Sometimes you want to check if a key exists before accessing it, without accidentally creating new entries. This is where the `.count()` method becomes useful. It tells you whether a specific key is present in the map.

The `.count()` method returns `1` if the key exists and `0` if it doesn't:

```cpp
std::map<std::string, int> scores;
scores["Alice"] = 95;
if (scores.count("Alice")) {    
std::cout << "Alice's score: " << scores["Alice"] << std::endl;
} else {    
std::cout << "Alice not found" << std::endl;
}
```

This approach lets you safely check for a key's existence and handle both cases appropriately, preventing unwanted entries from being created in your map.


# Removing Pairs

Sometimes you need to remove key-value pairs from your map when they're no longer needed. The `.erase()` method provides a straightforward way to delete elements by specifying the key you want to remove.

To remove an element from a map, simply call `.erase()` with the key as the argument:

```cpp
std::map<std::string, int> scores;
scores["Alice"] = 95;
scores["Bob"] = 87;
scores["Carol"] = 92;
scores.erase("Bob"); // Removes Bob's entry completely
```

After calling `erase("Bob")`, the map will only contain Alice and Carol's scores. If you try to erase a key that doesn't exist in the map, the operation simply does nothing - no error occurs.

This method is particularly useful for maintaining clean data structures, removing outdated information, or implementing features where users can delete entries from your application.

# Iterating Over a Map

Now that you know how to create, modify, and remove elements from a map, let's learn how to go through all the key-value pairs in your map. The range-based for loop provides an elegant way to iterate through every element in a `std::map`.

Here's the basic syntax for iterating over a map:

```cpp
for (auto pair : myMap) {    // Access the key with pair.first    // Access the value with pair.second}
```

Each element in the loop is a pair object that contains two important members: `first` holds the key, and `second` holds the value. Here's a practical example:

```cpp
std::map<std::string, int> scores;
scores["Alice"] = 95;
scores["Bob"] = 87;
scores["Carol"] = 92;
for (auto pair : scores) {   
 std::cout << pair.first << ": " << pair.second << std::endl;
 }
```

This will print each student's name followed by their score. The `auto` keyword automatically determines the correct type for each pair, making your code cleaner and easier to read