# **DAY - 01** | *22 June 2026*

##  Beginning My AI/ML Journey


##  Today's Goal

Set up the Python environment and learn the fundamentals of Python programming.

---

## 📚 Topics Covered

1. **Setting Up the Development Environment**
   - Installed Python from the official website.
   - Installed Visual Studio Code (VS Code).
   - Verified the Python installation.

2. **Python Basics**
   - Variables
   - Dynamic Typing
   - Built-in Data Types
   - Mutability and Immutability
   - Sharing References (Aliasing)

3. **Input and Output**
   - `print()`
   - `input()`

4. **Types of Operators**
   - Arithmetic Operators
   - Comparison Operators
   - Logical Operators
   - Assignment Operators

---

## 📖 What I Learned

Today was the first day of my AI/ML training, and we began by setting up the development environment. I installed **Python** from its official website and **Visual Studio Code (VS Code)**, which will be my primary code editor throughout the training.

Python is one of the most widely used programming languages in Artificial Intelligence, Machine Learning, Data Science, Web Development, and Automation due to its simple syntax, readability, and extensive ecosystem of libraries.

After completing the installation and setup, I explored the fundamental concepts of Python programming, including variables, built-in data types, dynamic typing, mutability and immutability, object references, input/output functions, and operators.

### 🐍 Installing Python

The first step was installing Python from its official website and setting up the programming environment. Installing Python correctly is essential because it provides the interpreter required to write, execute, and test Python programs. After installation, I verified that Python was successfully installed and ready to use.

---

### 📌 Variables

Variables are named memory locations used to store data. Instead of using values directly throughout a program, variables allow us to assign meaningful names to data, making programs easier to read, write, and maintain.

**Example:**

```python
name = "Alice"
age = 20
```

Here, `name` stores a string while `age` stores an integer.

---

### 🔄 Dynamic Typing

One of Python's most useful features is **dynamic typing**. Unlike many programming languages, Python does not require the programmer to specify the data type of a variable explicitly. Instead, the interpreter automatically determines the type based on the value assigned.

**Example:**

```python
x = 10
x = "Hello"
```

Initially, `x` stores an integer, but later it stores a string. Python automatically updates the variable's type without requiring any additional declarations.

---

### 📚 Built-in Data Types

Python provides several built-in data types for storing different kinds of information.

- **Integer (`int`)** – Stores whole numbers.
- **Float (`float`)** – Stores decimal numbers.
- **String (`str`)** – Stores text enclosed within quotes.
- **Boolean (`bool`)** – Represents logical values: `True` or `False`.
- **List (`list`)** – An ordered and mutable collection of elements.
- **Tuple (`tuple`)** – An ordered but immutable collection.
- **Set (`set`)** – An unordered collection that stores unique elements.
- **Dictionary (`dict`)** – Stores information as key-value pairs.

Choosing the appropriate data type helps in organizing, processing, and managing data efficiently within a program.

---

### 🔁 Mutability and Immutability

Python objects are classified as either **mutable** or **immutable** depending on whether their contents can be modified after creation.

- **Mutable objects** can be changed after they are created. Examples include **lists, dictionaries, and sets**.
- **Immutable objects** cannot be modified once they are created. Examples include **integers, floats, strings, tuples, and booleans**.

Understanding mutability is important because it affects how data behaves during program execution and how memory is managed.

---

### 🔗 Sharing References (Aliasing)

In Python, variables do not directly store values; instead, they store **references** to objects in memory. When one variable is assigned to another, both variables may refer to the same object. This concept is known as **sharing references** or **aliasing**.

**Example:**

```python
list1 = [10, 20]
list2 = list1
```

Since both variables refer to the same list object, any modification made using one variable is reflected when accessing the object through the other variable.

This concept is particularly important when working with mutable objects such as lists.

---

### 🖥️ Input and Output

Python provides built-in functions that allow programs to interact with users.

The **`print()`** function is used to display output on the screen.

```python
print("Hello, World!")
```

The **`input()`** function is used to accept input from the user while the program is running.

```python
name = input("Enter your name: ")
print("Welcome", name)
```

These functions form the basis of interactive Python applications and are among the most frequently used functions in Python programming.

---

### ➕ Operators

Operators are special symbols or keywords that perform specific operations on variables and values. They allow a program to perform calculations, compare values, evaluate logical expressions, and assign or update data. Without operators, writing meaningful programs would not be possible because they form the basis of computations and decision-making.

#### 1. Arithmetic Operators

Arithmetic operators are used to perform mathematical calculations on numeric values.

| Operator | Purpose | Example |
|----------|---------|---------|
| `+` | Addition | `10 + 5 = 15` |
| `-` | Subtraction | `10 - 5 = 5` |
| `*` | Multiplication | `10 * 5 = 50` |
| `/` | Division | `10 / 5 = 2.0` |
| `//` | Floor Division | `10 // 3 = 3` |
| `%` | Modulus (Remainder) | `10 % 3 = 1` |
| `**` | Exponentiation | `2 ** 3 = 8` |

These operators are commonly used for mathematical calculations and solving computational problems.

#### 2. Comparison Operators

Comparison operators compare two values and always return either `True` or `False`.

| Operator | Meaning |
|----------|---------|
| `==` | Equal to |
| `!=` | Not equal to |
| `>` | Greater than |
| `<` | Less than |
| `>=` | Greater than or equal to |
| `<=` | Less than or equal to |

**Example:**

```python
age = 20
print(age >= 18)
```

Output:

```text
True
```

These operators are widely used in conditional statements and decision-making.

#### 3. Logical Operators

Logical operators combine multiple conditions or reverse the result of a condition.

- **`and`** – Returns `True` only when both conditions are true.
- **`or`** – Returns `True` if at least one condition is true.
- **`not`** – Reverses the Boolean value.

**Example:**

```python
age = 20
citizen = True

print(age >= 18 and citizen)
```

Output:

```text
True
```

Logical operators are especially useful while implementing conditions in programs.

#### 4. Assignment Operators

Assignment operators are used to assign values to variables and update existing values efficiently.

| Operator | Example | Equivalent To |
|----------|---------|---------------|
| `=` | `x = 10` | Assign a value |
| `+=` | `x += 5` | `x = x + 5` |
| `-=` | `x -= 5` | `x = x - 5` |
| `*=` | `x *= 2` | `x = x * 2` |
| `/=` | `x /= 2` | `x = x / 2` |
| `%=` | `x %= 3` | `x = x % 3` |

Assignment operators make code shorter, cleaner, and easier to understand by combining assignment and computation into a single statement.

---

## 👩‍💻Coding Practice

### Program 1: Perform Basic Arithmetic Operations

**Question:** Write a Python program to perform addition, subtraction, multiplication, division, floor division, modulus, and exponentiation on two numbers.

#### Code

```python
a = 20
b = 4

print(f"Addition : {a+b}")
print(f"Subtraction : {a-b}")
print(f"Multiplication : {a*b}")
print(f"Division : {a/b}")
print(f"Floor Division : {a//b}")
print(f"Modulus : {a%b}")
print(f"Exponent : {a**b}")


### Program 2: Calculate Percentage

**Question:** Write a Python program to input marks of five subjects and calculate the total marks and percentage.

#### Code

```python
eng = int(input("Enter marks for Eng : "))
sci = int(input("Enter marks for Sci : "))
punjabi = int(input("Enter marks for Punjabi : "))
math = int(input("Enter marks for Math : "))
sst = int(input("Enter marks for SST : "))

total_marks = eng + sci + punjabi + math + sst
percentage = (total_marks / 500) * 100

print("Total Marks :", total_marks)
print("Percentage :", percentage)


### Program 3: Find the Greatest of Three Numbers

**Question:** Write a Python program to find the greatest among three numbers using conditional statements.

#### Code

```python
a = int(input("A : "))
b = int(input("B : "))
c = int(input("C : "))

if a > b and a > c:
    print("a is greater")
elif b > a and b > c:
    print("b is greater")
else:
    print("c is greater")


### Program 4: Variables and Memory Address

**Question:** Write a Python program to display the value, data type, and memory address of a variable.

#### Code

```python
x = 42

print(x)
print("x")
print(f"x is a variable : {x}")
print(f"Value of x : {x}")
print(f"Data Type of x : {type(x)}")
print(f"Memory address of x (id): {id(x)}")


## 💻 What I Practiced

- Installed Python successfully.
- Verified the Python installation.
- Installed Visual Studio Code (VS Code).
- Configured VS Code for Python development.
- Wrote simple programs using variables.
- Used `print()` to display output.
- Used `input()` to accept user input.
- Worked with different built-in data types.
- Explored mutable and immutable objects.
- Performed arithmetic calculations using operators.
- Practiced comparison and logical operations.

---

## 💡 Key Takeaway

Today's session helped me build a strong foundation in Python programming. I learned how Python stores and manages data using variables and built-in data types, understood dynamic typing, mutability, and object references, and explored input/output functions and different categories of operators. These concepts form the building blocks for advanced Python programming and will be essential as I continue my journey into Data Science, Machine Learning, and Artificial Intelligence.

