# cout Statement

In C++, the `cout` object provides various methods for printing output to the console. Here are some of the most commonly used `cout` methods:

- `<<`: Prints a string to the console. It does **not add** a newline character at the end, so subsequent output will continue on the same line.

- `endl` or `\n`: Used to add a line break in the output. Without these, all output will appear on the same line.

Here's how you can use these methods:

```cpp
std::string name = "Alice";int age = 30;
```

Using `endl`:

```cpp
cout << "Name: ";cout << name;cout << " is " << age << " years old." << endl;
cout << "Hello, " << name << "!" << endl;
// Output:// Name: Alice is 30 years old.// Hello, Alice!
```

Using `\n`:

```cpp
cout << "Name: " << name << "\n";
cout << "Age: " << age << "\n";
cout << "Hello, " << name << "!\n";// Output:// Name: Alice// Age: 30// Hello, Alice!
```


# cin Statement

As of now we stored values that we thought about in variables. Programs usually don't work this way. We receive values from an outer source, a user for example.

In C++, getting input from a user is done using the `cin` statement. This statement provides methods to read different types of input, such as integers, floating-point numbers, and strings.

To use the `cin` statement, you first need to declare a variable to store the input value. Then, you can use the extraction operator `>>` to read the input from the standard input stream `std::cin` and store it in the variable. Here's how you do it:

```cpp
int age;
std::cout << "Enter your age: ";
std::cin >> age;
```

The extraction operator >> will automatically convert the input to the appropriate data type based on the variable you're storing it in. For example:

```cpp
// For integers:std::cin >> intVariable;// For doubles:std::cin >> doubleVariable;// For strings:std::cin >> stringVariable;
```

For boolean values in C++, `cin` can handle input in two ways:

1. Using numbers (0 is converted to false, non-zero value is converted to true)

2. Using strings ("true" or "false" are converted to true or false respectively)

# string Input

Strings behave a bit differently then other types. There are several ways to get input into a string in C++. Here are the most common methods:

1. Using `cin`:

```cpp
std::string str;
std::cin >> str;
```

Note: This only reads until the **first whitespace**

2. Using `getline()` (recommended for sentences with spaces):

```cpp
std::string str;
std::getline(std::cin, str);
```

This reads entire line including spaces.

3. Using both `cin` and `getline` (when reading after cin):

```cpp
int n;
std::string str;
std::cin >> n;
std::cin.ignore();
  // Clear the newline from input bufferstd::getline(cin, str);
```

Without `cin.ignore()`, getline would read the leftover newline instead of waiting for input
