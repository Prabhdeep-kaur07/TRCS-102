# 🗓️**DAY-04** | *25 June 2026*

## 🎯 Today's Goal

To understand different types of function arguments, explore variable scope and recursion, and learn the fundamentals of Python lists, including indexing, slicing, and commonly used list operations.

## 📚 Topics Covered

1. Types of Arguments
   - Positional Arguments
   - Keyword Arguments
   - Variable Length Arguments (`*args`)
   - Variable Length Keyword Arguments (`**kwargs`)
   - Default Arguments
2. Variable Scope
   - Local Variables
   - Global Variables
   - `global` Keyword
3. Recursive Functions
4. Lists
   - Creating Lists
   - Indexing
   - Slicing
   - List Operations
     - `append()`
     - `extend()`
     - `insert()`
     - `remove()`
     - `sort()`

## 📖 What I Learned

## 📌 Types of Arguments

When a function is called, values are passed to it through **arguments**. Python provides multiple ways of passing arguments to a function, making programs more flexible and reusable. The different types of arguments help programmers handle different situations, such as fixed inputs, optional inputs, or an unknown number of inputs.

---

### 🔹 Positional Arguments

In **positional arguments**, values are passed to the function according to the order of the parameters defined in the function. The first argument is assigned to the first parameter, the second argument to the second parameter, and so on. Therefore, the order of arguments is very important.

### Syntax

```python
def function(parameter1, parameter2):
    # Function body

function(value1, value2)
```

### Example

```python
def student(name, age):
    print("Name:", name)
    print("Age:", age)

student("Prabhdeep", 20)
```

Output

```text
Name: Prabhdeep
Age: 20
```

If the order of the arguments is changed, the values assigned to the parameters will also change.

---

### 🔹 Keyword Arguments

In **keyword arguments**, values are passed using the parameter names. Since each argument is associated with a parameter name, the order of arguments does not matter.

### Syntax

```python
function(parameter=value)
```

### Example

```python
def student(name, age):
    print("Name:", name)
    print("Age:", age)

student(age=20, name="Prabhdeep")
```

Output

```text
Name: Prabhdeep
Age: 20
```

Keyword arguments improve code readability and reduce mistakes when functions have many parameters.

---

### 🔹 Variable Length Arguments (`*args`)

Sometimes we do not know how many arguments will be passed to a function. Python allows us to accept any number of positional arguments using `*args`.

The `*args` parameter collects all additional positional arguments into a **tuple**.

### Syntax

```python
def function(*args):
    # Function body
```

### Example

```python
def total(*numbers):
    print(numbers)
    print(sum(numbers))

total(10, 20, 30)
```

Output

```text
(10, 20, 30)
60
```

The name `args` is only a convention. Any valid variable name can be used after the `*` symbol.

---

### 🔹 Variable Length Keyword Arguments (`**kwargs`)

When the number of keyword arguments is unknown, Python provides `**kwargs`.

The `**kwargs` parameter collects all keyword arguments into a **dictionary**, where the keys are the parameter names and the values are the corresponding values passed to the function.

### Syntax

```python
def function(**kwargs):
    # Function body
```

### Example

```python
def student(**details):
    print(details)

student(name="Prabhdeep", age=20, course="AI/ML")
```

Output

```text
{'name': 'Prabhdeep', 'age': 20, 'course': 'AI/ML'}
```

Individual values can also be accessed using dictionary keys.

```python
def student(**details):
    print(details["name"])

student(name="Prabhdeep", age=20)
```

Output

```text
Prabhdeep
```

---

### 🔹 Default Arguments

A **default argument** is a parameter that has a predefined value. If the user does not provide a value while calling the function, Python automatically uses the default value.

### Syntax

```python
def function(parameter=default_value):
    # Function body
```

### Example

```python
def greet(name="Student"):
    print("Welcome", name)

greet()
greet("Prabhdeep")
```

Output

```text
Welcome Student
Welcome Prabhdeep
```

Default arguments make functions more flexible because they can work with or without explicitly passing every argument.

---

## 📊 Difference Between Positional and Keyword Arguments

| Positional Arguments | Keyword Arguments |
|----------------------|-------------------|
| Values are assigned based on their position. | Values are assigned using parameter names. |
| Order of arguments is important. | Order of arguments is not important. |
| Easier to write for functions with fewer parameters. | More readable for functions with many parameters. |
| Incorrect ordering may produce incorrect results. | Reduces the chance of assigning incorrect values. |

---

## 📌 Variable Scope

**Variable scope** refers to the region of a program where a variable can be accessed. In Python, the scope of a variable determines where it can be used and modified. Understanding variable scope helps avoid naming conflicts and makes programs easier to debug and maintain.

Python mainly provides two types of variable scope:

- Local Scope
- Global Scope

---

### 🔹 Local Variables

A **local variable** is a variable that is declared inside a function. It can only be accessed within that function and is destroyed once the function finishes execution.

#### Characteristics

- Declared inside a function.
- Accessible only within that function.
- Cannot be accessed from outside the function.
- Temporary in nature.

### Example

```python
def display():
    message = "Hello Python"
    print(message)

display()
```

Output

```text
Hello Python
```

Trying to access `message` outside the function will result in a **NameError** because it only exists inside the function.

---

### 🔹 Global Variables

A **global variable** is declared outside all functions. It can be accessed from anywhere in the program, including inside functions.

#### Characteristics

- Declared outside all functions.
- Accessible throughout the program.
- Exists until the program terminates.

### Example

```python
language = "Python"

def display():
    print(language)

display()
print(language)
```

Output

```text
Python
Python
```

---

### 🔹 The `global` Keyword

Normally, if we assign a value to a variable inside a function, Python treats it as a local variable. To modify a global variable inside a function, we use the **`global`** keyword.

The `global` keyword tells Python that the variable belongs to the global scope rather than the local scope.

### Syntax

```python
global variable_name
```

### Example

```python
count = 10

def update():
    global count
    count += 5

update()

print(count)
```

Output

```text
15
```

Without using the `global` keyword, Python would create a new local variable instead of modifying the global one.

---

## 📊 Difference Between Local and Global Variables

| Local Variable | Global Variable |
|---------------|-----------------|
| Declared inside a function. | Declared outside all functions. |
| Accessible only within that function. | Accessible throughout the program. |
| Created when the function is called. | Exists until the program ends. |
| Cannot be accessed outside the function. | Can be accessed inside and outside functions. |

---

# 📌 Recursive Functions

A **recursive function** is a function that calls itself repeatedly until a specified stopping condition, known as the **base case**, is reached.

Recursion is useful for solving problems that can be divided into smaller subproblems, such as calculating factorials, Fibonacci numbers, tree traversals, and searching algorithms.

Every recursive function must contain:

- **Base Case** – Stops the recursion.
- **Recursive Case** – Calls the function again with a smaller problem.

If a recursive function does not have a base case, it will continue calling itself indefinitely, resulting in a **RecursionError**.

---

### Example: Factorial Using Recursion

```python
def factorial(n):

    if n == 0 or n == 1:
        return 1

    return n * factorial(n - 1)

print(factorial(5))
```

Output

```text
120
```

---

### How Recursion Works

Suppose we calculate:

```
factorial(5)

↓

5 × factorial(4)

↓

5 × 4 × factorial(3)

↓

5 × 4 × 3 × factorial(2)

↓

5 × 4 × 3 × 2 × factorial(1)

↓

5 × 4 × 3 × 2 × 1

↓

120
```

The function repeatedly calls itself until it reaches the base case (`factorial(1)`), after which each function call returns its value back to the previous call.

---

# 📌 Lists

A **list** is one of the most commonly used data structures in Python. It is an **ordered**, **mutable**, and **heterogeneous** collection that allows multiple values to be stored in a single variable.

Lists are enclosed within square brackets (`[]`) and can store elements of different data types, such as integers, floats, strings, and even other lists.

### Characteristics of Lists

- Ordered collection.
- Mutable (elements can be modified).
- Allows duplicate values.
- Supports indexing and slicing.
- Can store different data types.

---

## 📌 Creating a List

Lists are created using square brackets.

### Example

```python
numbers = [10, 20, 30, 40]

print(numbers)
```

Output

```text
[10, 20, 30, 40]
```

Lists can also contain different data types.

```python
student = ["Prabhdeep", 20, 8.9, True]

print(student)
```

Output

```text
['Prabhdeep', 20, 8.9, True]
```

---

## 📌 List Indexing

Each element in a list has an index.

- Positive indexing starts from **0**.
- Negative indexing starts from **-1**.

Example list:

```python
fruits = ["Apple", "Banana", "Mango", "Orange"]
```

| Index | Element |
|-------:|---------|
| 0 | Apple |
| 1 | Banana |
| 2 | Mango |
| 3 | Orange |

| Negative Index | Element |
|---------------:|---------|
| -1 | Orange |
| -2 | Mango |
| -3 | Banana |
| -4 | Apple |

### Example

```python
fruits = ["Apple", "Banana", "Mango", "Orange"]

print(fruits[0])
print(fruits[-1])
```

Output

```text
Apple
Orange
```

---

## 📌 List Slicing

**Slicing** is used to access multiple elements from a list.

### Syntax

```python
list_name[start : stop : step]
```

Where:

- **start** → Starting index (included).
- **stop** → Ending index (excluded).
- **step** → Number of positions to skip.

### Example

```python
numbers = [10, 20, 30, 40, 50, 60]

print(numbers[1:4])
print(numbers[:4])
print(numbers[2:])
print(numbers[::2])
print(numbers[::-1])
```

Output

```text
[20, 30, 40]
[10, 20, 30, 40]
[30, 40, 50, 60]
[10, 30, 50]
[60, 50, 40, 30, 20, 10]
```

Slicing is useful for extracting specific portions of a list or reversing the entire list using `[::-1]`.

## 👩‍💻 Hands-on Practice

### Program 1: Demonstrate Different Types of Arguments

**Question:** Write a Python program to demonstrate default, positional, and keyword arguments.

#### Code

```python
def intro(name, age=18, course='B.Tech'):
    print(f"{name} is {age} years old and is pursuing {course}")

intro("Aman", 19)
intro("Aman", 20, 'BCA')
intro(name='Neha', course='BCA', age=21)
```


![Types of Arguments](Images/Day-04/types-of-arguments.png)

---

### Program 2: Variable Length Arguments (`*args`)

**Question:** Write a Python program to calculate the total expenses using variable-length positional arguments.

#### Code

```python
def calculate_total_expenses(*expenses):
    print(f"Expenses received: {expenses} (Type: {type(expenses)})")
    return sum(expenses)

print(calculate_total_expenses(12.5, 20, 18.6, 23.879, 40))
```


![Args Example](Images/Day-04/args.png)

---

### Program 3: Keyword Variable Length Arguments (`**kwargs`)

**Question:** Write a Python program to demonstrate the use of `**kwargs`.

#### Code

```python
def print_model_parameter(**hyperparams):
    print(f"Hyperparameters received: {hyperparams} (Type: {type(hyperparams)})")

    for key, value in hyperparams.items():
        print(f"- {key}: {value}")

print_model_parameter(
    learning_rate=0.001,
    batch_size=64,
    dropout=0.3
)
```


![Kwargs Example](Images/Day-04/kwargs.png)

---

### Program 4: Local and Global Variables

**Question:** Write a Python program to demonstrate local variables, global variables, and the `global` keyword.

#### Code

```python
a = "Aman"

def function():
    score = 95
    print(f"{a}'s score is {score}")
    print("Inside function : 95")

function()

b = 20

def change():
    global b
    b = 10
    print("After changing the value of b:", b)

change()

print("Original:", b)
```


![Global Variables](Images/Day-04/global-local.png)

---

### Program 5: Recursive Function (Factorial)

**Question:** Write a Python program to calculate the factorial of a number using recursion.

#### Code

```python
def calculate_factorial(n):

    if n == 0 or n == 1:
        return 1

    return n * calculate_factorial(n - 1)

print(calculate_factorial(5))
```


![Factorial](Images/Day-04/factorial.png)

---

### Program 6: Fibonacci Series Using Recursion

**Question:** Write a Python program to generate the Fibonacci sequence using recursion.

#### Code

```python
def fib(n):

    if n == 0:
        return 0

    elif n == 1:
        return 1

    else:
        return fib(n - 1) + fib(n - 2)

print(fib(7))
```


![Fibonacci](Images/Day-04/fibonacci.png)

---

### Program 7: List Operations

**Question:** Write a Python program to perform different list operations.

#### Code

```python
list1 = [10, 20]

print(type(list1))

list1.append(90)
print(list1)

list2 = [30, 50]

list1.extend(list2)
print(list1)

list1.insert(0, 50)
print("After inserting:", list1)

list1.remove(50)
print(list1)

list1.append(50)

list1.pop(2)

list1 = [10, 20, 30, 45, 74]

list1.sort()

print(list1)
```


![List Operations](Images/Day-04/list-operations.png)

---

### Program 8: Update Salary List

**Question:** Write a Python program to reduce every employee's salary by 70%.

#### Code

```python
salary = [1000, 2000, 3000, 4000]

for i in range(len(salary)):
    salary[i] -= salary[i] * 0.7

print(salary)
```


![Salary Update](Images/Day-04/salary-update.png)

---

### Program 9: Remove Sentinel Values from a List

**Question:** Write a Python program to remove all `-99.0` values from a list of predictions.

#### Code

```python
predictions = [0.15, -99.0, 0.82, 1.45, -99.0, 0.67, 2.1]

for value in predictions[:]:
    if value == -99.0:
        predictions.remove(value)

print(predictions)
```

![Remove Sentinel Values](Images/Day-04/remove-sentinel.png)

---

### Program 10: Find Pairs with Sum Equal to 11

**Question:** Write a Python program to find all pairs of elements in a list whose sum is equal to 11.

#### Code

```python
numbers = [1, 8, 10, 10, 8, 8, 3, 5]

for i in range(len(numbers)):
    for j in range(i + 1, len(numbers)):

        if numbers[i] + numbers[j] == 11:
            print(numbers[i], numbers[j])
```

![Pair Sum](Images/Day-04/pair-sum.png)

---

## 💻 What I Practiced

- Practiced positional, keyword, and default arguments while defining and calling functions.
- Used `*args` to pass a variable number of positional arguments to a function.
- Used `**kwargs` to pass variable-length keyword arguments as dictionaries.
- Explored local and global variables and learned how the `global` keyword modifies global variables inside functions.
- Implemented recursive functions to calculate factorials and Fibonacci numbers.
- Performed various list operations such as `append()`, `extend()`, `insert()`, `remove()`, `pop()`, and `sort()`.
- Updated list elements using loops and indexing.
- Removed unwanted values from a list safely by iterating over a copy.
- Solved a nested loop problem to find pairs of elements with a given sum.

---

## 💡 Key Takeaway

Today's session strengthened my understanding of Python functions by exploring different ways of passing arguments and managing variable scope. I learned how recursion solves problems by allowing a function to call itself and gained hands-on experience with Python lists, one of the most important data structures. By practicing list operations, recursion, and variable-length arguments, I developed a deeper understanding of writing modular, reusable, and efficient Python programs. These concepts are fundamental for data manipulation and algorithm development in Data Science, Machine Learning, and Artificial Intelligence.
