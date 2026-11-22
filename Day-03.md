
# DAY-03 | 24 June 2026

## Today's Goal

To understand the concept of functions and modular programming, explore commonly used built-in functions, learn how to create custom functions, differentiate between parameters and arguments, and understand the purpose of the `return` statement.

## Topics Covered

1. Functions
2. Advantages of Functions
3. Modular Programming
4. Built-in Functions
   - `len()`
   - `sum()`
   - `min()`
   - `max()`
   - `abs()`
   - `round()`
   - `print()`
5. Custom Functions
   - Defining Functions
   - Calling Functions
6. Parameters and Arguments
7. Return Statement

## What I Learned

### Functions

A **function** is a reusable block of code designed to perform a specific task. Instead of writing the same code multiple times, a function allows us to write it once and execute it whenever needed. Functions make programs more organized, readable, and efficient by reducing code duplication.

Python provides two types of functions:

- **Built-in Functions** – Functions that are already provided by Python, such as `len()`, `sum()`, and `print()`.
- **User-defined (Custom) Functions** – Functions created by the programmer using the `def` keyword.

Functions are widely used in software development, data analysis, machine learning, and artificial intelligence because they promote code reusability and modular programming.

---

### Advantages of Functions

Functions offer several benefits that improve the quality and maintainability of programs.

- Reduce code duplication by allowing the same code to be reused.
- Improve readability by dividing a program into meaningful sections.
- Make debugging easier since each function performs a single task.
- Simplify testing because each function can be tested independently.
- Support modular programming by breaking large programs into smaller modules.
- Make programs easier to maintain and update.

---

### Modular Programming

**Modular Programming** is a programming approach in which a large program is divided into smaller, independent modules or functions. Each module performs a specific task, making the overall program easier to understand, develop, test, and maintain.

For example, in a Student Management System:

- One function calculates marks.
- Another function calculates attendance.
- Another function displays student details.
- Another function generates the final report.

Since each function has a single responsibility, modifications can be made without affecting the rest of the program.

---

# Built-in Functions

Python provides several built-in functions that are readily available without requiring additional implementation. These functions simplify common programming tasks and improve code readability.

## `len()`

The `len()` function returns the number of elements present in an object such as a string, list, tuple, dictionary, or set.

**Syntax**

```python
len(object)
```

**Example**

```python
fruits = ["Apple", "Banana", "Kiwi"]

print(len(fruits))
```

**Output**

```text
3
```

---

## `sum()`

The `sum()` function calculates the total sum of all numeric elements in an iterable.

**Syntax**

```python
sum(iterable)
```

**Example**

```python
marks = [80, 75, 90, 85]

print(sum(marks))
```

**Output**

```text
330
```

---

## `min()`

The `min()` function returns the smallest element from an iterable.

**Syntax**

```python
min(iterable)
```

**Example**

```python
numbers = [10, 25, 3, 50]

print(min(numbers))
```

**Output**

```text
3
```

---

## `max()`

The `max()` function returns the largest element from an iterable.

**Syntax**

```python
max(iterable)
```

**Example**

```python
numbers = [10, 25, 3, 50]

print(max(numbers))
```

**Output**

```text
50
```

---

## `abs()`

The `abs()` function returns the absolute (positive) value of a number.

**Syntax**

```python
abs(number)
```

**Example**

```python
print(abs(-15))
```

**Output**

```text
15
```

---

## `round()`

The `round()` function rounds a floating-point number to the nearest integer or to the specified number of decimal places.

**Syntax**

```python
round(number, digits)
```

**Example**

```python
print(round(3.14159, 2))
```

**Output**

```text
3.14
```

---

## `print()`

The `print()` function displays output on the screen. It is one of the most frequently used built-in functions in Python and is primarily used for displaying messages, variables, and program results.

**Syntax**

```python
print(object)
```

**Example**

```python
language = "Python"

print("Welcome to", language)
```

**Output**

```text
Welcome to Python
```

---

# Custom Functions

A **custom function**, also known as a **user-defined function**, is a function created by the programmer to perform a specific task. Unlike built-in functions, custom functions are written according to the requirements of the program.

Custom functions help organize code into smaller reusable blocks, making programs more structured, readable, and easier to maintain.

In Python, custom functions are created using the `def` keyword.

## Defining a Function

Defining a function means creating a reusable block of code by giving it a name and specifying the statements it should execute.

**Syntax**

```python
def function_name(parameters):
    # function body
```

**Explanation**

- `def` is the keyword used to define a function.
- `function_name` is the name given to the function.
- `parameters` are optional variables that receive values when the function is called.
- The indented block contains the statements that the function executes.

**Example**

```python
def welcome():
    print("Welcome to AI/ML Training!")
```

The function has been defined, but it will not execute until it is called.

---

## Calling a Function

Calling a function means executing the function after it has been defined.

**Syntax**

```python
function_name()
```

**Example**

```python
def welcome():
    print("Welcome to AI/ML Training!")

welcome()
```

**Output**

```text
Welcome to AI/ML Training!
```

Whenever the function is called, Python executes all the statements inside the function.

---

# Parameters and Arguments

Parameters and arguments are often confused, but they are different.

- **Parameters** are variables listed in the function definition.
- **Arguments** are the actual values passed to the function when it is called.

**Example**

```python
def greet(name):
    print(f"Hello, {name}")

greet("Prabhdeep")
```

**Output**

```text
Hello, Prabhdeep
```

Here,

- `name` is the **parameter**.
- `"Prabhdeep"` is the **argument**.

---

## Difference Between Parameters and Arguments

| Parameters | Arguments |
|---|---|
| Declared in the function definition. | Passed while calling the function. |
| Act as placeholders for values. | Are the actual values supplied to the function. |
| Receive data from the caller. | Send data to the function. |
| Exist only inside the function. | Can be variables, constants, or expressions. |

---

## Types of Arguments

Python supports different ways of passing arguments to functions.

### Positional Arguments

Values are passed in the same order as the parameters.

**Example**

```python
def student(name, age):
    print(name)
    print(age)

student("Prabhdeep", 20)
```

**Output**

```text
Prabhdeep
20
```

---

### Keyword Arguments

Arguments are passed using the parameter names, so their order does not matter.

**Example**

```python
def student(name, age):
    print(name)
    print(age)

student(age=20, name="Prabhdeep")
```

**Output**

```text
Prabhdeep
20
```

---

### Default Arguments

A parameter can have a default value. If no value is provided while calling the function, the default value is used.

**Example**

```python
def greet(name="Student"):
    print("Hello", name)

greet()
greet("Prabhdeep")
```

**Output**

```text
Hello Student
Hello Prabhdeep
```

---

# Return Statement

The **`return`** statement is used to send a value back from a function to the place where the function was called. Once a `return` statement is executed, the function immediately terminates, and the returned value can be stored in a variable or used in an expression.

Unlike the `print()` function, which simply displays output on the screen, the `return` statement allows the returned value to be reused later in the program.

**Syntax**

```python
return value
```

---

## Example 1

```python
def add(a, b):
    return a + b

result = add(10, 20)

print(result)
```

**Output**

```text
30
```

---

## Example 2

```python
def square(number):
    return number * number

value = square(5)

print(value)
print(value + 10)
```

**Output**

```text
25
35
```

In this example, the value returned by the function is stored in a variable and later used in another calculation.

---

## Difference Between `print()` and `return`

| `print()` | `return` |
|---|---|
| Displays output on the screen. | Sends a value back to the caller. |
| Cannot be reused in another calculation. | Returned value can be stored and reused. |
| Does not terminate the function. | Immediately exits the function after execution. |
| Mainly used for displaying information. | Mainly used for producing results from a function. |

### Example

```python
def add_print(a, b):
    print(a + b)

def add_return(a, b):
    return a + b

add_print(5, 10)

result = add_return(5, 10)
print(result + 20)
```

**Output**

```text
15
35
```

This demonstrates that `return` makes functions reusable, whereas `print()` only displays the output.

---

# Hands-on Practice

## Program 1: Bank Simulator

**Question:** Write a Python program to simulate a simple banking system that allows the user to check balance, deposit money, withdraw money, and exit the program using a menu-driven approach.

**Code**

```python
bal = 1000

while True:
    print("Bank Simulator")
    print("Option 1 : Check Balance")
    print("Option 2 : Deposit")
    print("Option 3 : Withdraw")
    print("Option 4 : Exit")

    choice = int(input("Enter your choice : "))

    if choice == 1:
        print(f"Current balance : {bal}")

    elif choice == 2:
        dep = int(input("Enter amount to Deposit : "))
        bal += dep
        print("Amount deposited successfully!")
        print(f"New Balance : {bal}")

    elif choice == 3:
        withd = int(input("Enter amount to Withdraw : "))

        if withd > bal:
            print("Insufficient Balance")
        else:
            bal -= withd
            print("Amount withdrawn successfully!")

        print(f"New Balance : {bal}")

    elif choice == 4:
        print("Exiting the System.....")
        break
```

**Output**

```text
Bank Simulator
Option 1 : Check Balance
Option 2 : Deposit
Option 3 : Withdraw
Option 4 : Exit
Enter your choice : 1
Current balance : 1000

Bank Simulator
Option 1 : Check Balance
Option 2 : Deposit
Option 3 : Withdraw
Option 4 : Exit
Enter your choice : 2
Enter amount to Deposit : 500
Amount deposited successfully!
New Balance : 1500

Bank Simulator
Option 1 : Check Balance
Option 2 : Deposit
Option 3 : Withdraw
Option 4 : Exit
Enter your choice : 3
Enter amount to Withdraw : 200
Amount withdrawn successfully!
New Balance : 1300

Bank Simulator
Option 1 : Check Balance
Option 2 : Deposit
Option 3 : Withdraw
Option 4 : Exit
Enter your choice : 4
Exiting the System.....
```

---

## Program 2: Demonstrate Built-in Functions

**Question:** Write a Python program to demonstrate the use of built-in functions such as `len()`, `sum()`, `abs()`, and `round()`.

**Code**

```python
numbers = [10, -20, 23]

print(len(numbers))

text = "abcdefgh"
print(len(text))

print(sum(numbers))

n = -4
print(abs(n))

for i in numbers:
    print(abs(i))

n = 12.435

print(round(n, 2))
print(round(n))
```

**Output**

```text
3
8
13
4
10
20
23
12.43
12
```

---

## Program 3: Create and Call a Custom Function

**Question:** Write a Python program to define and call a simple custom function.

**Code**

```python
def welcome():
    print("Welcome to Training!")

welcome()
```

**Output**

```text
Welcome to Training!
```

---

## Program 4: Calculator Using Functions

**Question:** Write a Python program to perform arithmetic operations using a custom function and the `return` statement.

**Code**

```python
def custom(a, b, s):

    if s == '+':
        return a + b

    elif s == '-':
        return a - b

    elif s == '*':
        return a * b

    elif s == '/':
        return a / b


a = custom(10, 20, '+')

a += 10

print(a)

print(custom(10, 50, '+'))
print(custom(10, 50, '-'))
print(custom(10, 50, '*'))
print(custom(10, 50, '/'))
```

**Output**

```text
40
60
-40
500
0.2
```

---

## Program 5: Prime Number Checker (Without Function)

**Question:** Write a Python program to check whether a given number is prime without using a user-defined function.

**Code**

```python
num = int(input("Enter a number: "))

if num > 1:

    for i in range(2, num):

        if num % i == 0:
            print("Not Prime")
            break

    else:
        print("Prime")

else:
    print("Not Prime")
```

**Output**

```text
Enter a number: 17
Prime
```

---

## Program 6: Prime Number Checker (Using Function)

**Question:** Write a Python program to check whether a number is prime using a user-defined function.

**Code**

```python
def prime(n):

    if n <= 1:
        return False

    for i in range(2, int(n ** 0.5) + 1):

        if n % i == 0:
            return False

    return True


num = int(input("Enter a number: "))

if prime(num):
    print("Prime")
else:
    print("Not Prime")
```

**Output**

```text
Enter a number: 17
Prime
```

---

## What I Practiced

- Built a menu-driven Bank Simulator using loops, conditional statements, and modular programming.
- Practiced commonly used built-in functions such as `len()`, `sum()`, `abs()`, `round()`, `min()`, and `max()`.
- Created and called custom functions using the `def` keyword.
- Passed parameters and arguments to functions and understood their roles.
- Used the `return` statement to send values back from functions.
- Developed a calculator using user-defined functions.
- Implemented a Prime Number Checker both with and without functions.
- Improved my understanding of modular programming by organizing code into reusable functions.

---

## Key Takeaway

Today's session introduced me to one of the most important concepts in Python—**functions**. I learned how functions promote code reusability and modular programming by breaking large programs into smaller, manageable components. I explored several built-in functions, created custom functions, understood the difference between parameters and arguments, and used the `return` statement to produce reusable outputs.

By implementing practical programs such as a **Bank Simulator**, **Calculator**, and **Prime Number Checker**, I gained confidence in writing structured, reusable, and maintainable Python code. These concepts form the foundation of software development and are essential for Data Science, Machine Learning, and Artificial Intelligence, where complex tasks are organized into modular and reusable functions.
