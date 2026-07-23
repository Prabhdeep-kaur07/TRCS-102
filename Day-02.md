# 🗓️**DAY-02** | *23 June 2026*

## 🎯 Today's Goal

To understand advanced Python operators, including bitwise, membership, and identity operators, and learn how loops help automate repetitive tasks in Python.

## 📚 Topics Covered

1. **Bitwise Operators**
   - AND (`&`)
   - OR (`|`)
   - XOR (`^`)
   - NOT (`~`)
   - Left Shift (`<<`)
   - Right Shift (`>>`)
   - One's Complement
   - Two's Complement

2. **Membership Operators**
   - `in`
   - `not in`

3. **Identity Operators**
   - `is`
   - `is not`

4. **Loops**
   - `for` Loop
   - `while` Loop
   - `break`
   - `continue`
   - `pass`
   - `for...else`

## 📖 What I Learned

### 📌 Bitwise Operators

Bitwise operators perform operations directly on the binary (bit-level) representation of integers. Since computers store numbers in binary format (0s and 1s), these operators manipulate individual bits instead of whole numbers. Before performing a bitwise operation, Python converts decimal numbers into binary, applies the operation bit by bit, and then converts the result back into decimal.

Bitwise operators are widely used in low-level programming, embedded systems, networking, cryptography, image processing, and performance optimization.

---

### 🔹 Bitwise AND (`&`)

The **AND** operator compares the corresponding bits of two numbers. It returns **1 only if both bits are 1**; otherwise, it returns **0**.

#### Truth Table

| A | B | A & B |
|---|---|-------|
|0|0|0|
|0|1|0|
|1|0|0|
|1|1|1|

#### Mathematical Example

```
12 = 1100
10 = 1010
------------
&    1000
```

```
1000₂ = 8₁₀
```

Therefore,

```python
print(12 & 10)
```

Output

```text
8
```

---

### 🔹 Bitwise OR (`|`)

The **OR** operator returns **1 if at least one corresponding bit is 1**.

#### Truth Table

| A | B | A \| B |
|---|---|--------|
|0|0|0|
|0|1|1|
|1|0|1|
|1|1|1|

#### Mathematical Example

```
12 = 1100
10 = 1010
------------
|    1110
```

```
1110₂ = 14₁₀
```

```python
print(12 | 10)
```

Output

```text
14
```

---

### 🔹 Bitwise XOR (`^`)

The **Exclusive OR (XOR)** operator returns **1 only when the corresponding bits are different**.

#### Truth Table

| A | B | A ^ B |
|---|---|-------|
|0|0|0|
|0|1|1|
|1|0|1|
|1|1|0|

#### Mathematical Example

```
12 = 1100
10 = 1010
------------
^    0110
```

```
0110₂ = 6₁₀
```

```python
print(12 ^ 10)
```

Output

```text
6
```

---

### 🔹 Bitwise NOT (`~`)

The **NOT** operator inverts every bit of a number. In Python, the result is represented using the **two's complement** system.

#### Mathematical Example

```
5 = 00000101

NOT

11111010
```

Python calculates it as

```
~5 = -(5 + 1)

= -6
```

```python
print(~5)
```

Output

```text
-6
```

---

### 🔹 Left Shift (`<<`)

The **Left Shift** operator shifts all bits toward the left by a specified number of positions. Every left shift by one position multiplies the number by **2**.

#### Mathematical Example

```
5 = 00000101

5 << 2

00010100
```

```
00010100₂ = 20₁₀
```

```python
print(5 << 2)
```

Output

```text
20
```

---

### 🔹 Right Shift (`>>`)

The **Right Shift** operator shifts all bits toward the right by a specified number of positions. Every right shift by one position divides the number by **2** using integer division.

#### Mathematical Example

```
20 = 10100

20 >> 2

00101
```

```
00101₂ = 5₁₀
```

```python
print(20 >> 2)
```

Output

```text
5
```

---

### 📌 One's Complement

One's Complement is obtained by changing every **0 to 1** and every **1 to 0** in the binary representation of a number.

#### Example

```
13 = 00001101

One's Complement

11110010
```

One's complement is mainly used as the first step in calculating the two's complement of a binary number.

---

### 📌 Two's Complement

Two's Complement is obtained by adding **1** to the one's complement of a binary number. It is the standard method used by computers to represent negative integers.

#### Example

```
13 = 00001101

One's Complement

11110010

Add 1

11110011
```

Python internally uses two's complement representation while performing bitwise operations on signed integers.

### 📌 Membership Operators

Membership operators are used to check whether a particular element exists in a sequence such as a string, list, tuple, set, or dictionary. They return a Boolean value (`True` or `False`) based on whether the element is found.

Python provides two membership operators:

- `in`
- `not in`

---

### 🔹 `in` Operator

The `in` operator returns **True** if the specified element is present in the given sequence.

#### Syntax

```python
element in sequence
```

#### Example

```python
fruits = ["Apple", "Banana", "Mango"]

print("Apple" in fruits)
print("Orange" in fruits)
```

Output

```text
True
False
```

---

### 🔹 `not in` Operator

The `not in` operator returns **True** if the specified element is **not** present in the sequence.

#### Syntax

```python
element not in sequence
```

#### Example

```python
fruits = ["Apple", "Banana", "Mango"]

print("Orange" not in fruits)
print("Banana" not in fruits)
```

Output

```text
True
False
```

---

### 📌 Identity Operators

Identity operators are used to determine whether two variables refer to the **same object in memory**. Unlike comparison operators, which compare values, identity operators compare the memory locations (object identities) of variables.

Python provides two identity operators:

- `is`
- `is not`

---

### 🔹 `is` Operator

The `is` operator returns **True** if both variables refer to the same object in memory.

#### Syntax

```python
variable1 is variable2
```

#### Example

```python
a = [10, 20, 30]
b = a

print(a is b)
```

Output

```text
True
```

---

### 🔹 `is not` Operator

The `is not` operator returns **True** if two variables refer to different objects in memory.

#### Syntax

```python
variable1 is not variable2
```

#### Example

```python
a = [10, 20, 30]
b = [10, 20, 30]

print(a is not b)
```

Output

```text
True
```

---

# 🔁 Loops

Loops are control structures that repeatedly execute a block of code until a specified condition becomes false or until all elements in a sequence have been processed. They reduce repetitive coding and make programs shorter, more efficient, and easier to maintain.

Python provides two looping statements:

- `for` Loop
- `while` Loop

---

## 📌 `for` Loop

A `for` loop is used when the number of iterations is known or when traversing a sequence such as a list, tuple, string, set, dictionary, or a sequence generated using the `range()` function.

#### Syntax

```python
for variable in sequence:
    # code block
```

---

### 🔹 The `range()` Function

The `range()` function generates a sequence of numbers and is commonly used with `for` loops.

It has three forms:

- `range(stop)`
- `range(start, stop)`
- `range(start, stop, step)`

---

### 🔹 `range(stop)`

This form starts from **0** by default and generates numbers up to **stop - 1**.

#### Example

```python
for i in range(5):
    print(i)
```

Output

```text
0
1
2
3
4
```

---

### 🔹 `range(start, stop)`

This form starts from the specified **start** value and stops before the **stop** value.

#### Example

```python
for i in range(2, 7):
    print(i)
```

Output

```text
2
3
4
5
6
```

---

### 🔹 `range(start, stop, step)`

This form allows us to specify the increment or decrement between two consecutive values.

- **start** → Starting value
- **stop** → Ending value (not included)
- **step** → Increment or decrement value

#### Example

```python
for i in range(2, 11, 2):
    print(i)
```

Output

```text
2
4
6
8
10
```

A negative step prints values in reverse order.

```python
for i in range(10, 0, -2):
    print(i)
```

Output

```text
10
8
6
4
2
```

---

## 📌 `while` Loop

A `while` loop repeatedly executes a block of code as long as the specified condition remains `True`. It is mainly used when the number of iterations is not known in advance.

#### Syntax

```python
while condition:
    # code block
```

#### Example

```python
count = 1

while count <= 5:
    print("Count =", count)
    count += 1
```

Output

```text
Count = 1
Count = 2
Count = 3
Count = 4
Count = 5
```

## ⏭️ Loop Control Statements

Loop control statements are used to alter the normal execution of loops. They provide greater flexibility by allowing the loop to terminate early, skip specific iterations, or act as a placeholder for future code.

Python provides three loop control statements:

- `break`
- `continue`
- `pass`

---

### 🔹 `break` Statement

The `break` statement immediately terminates the nearest enclosing loop when a specified condition is met. Once a `break` statement is executed, the control moves to the first statement after the loop.

#### Syntax

```python
break
```

#### Example

```python
for i in range(1, 11):
    if i == 6:
        break
    print(i)
```

Output

```text
1
2
3
4
5
```

---

### 🔹 `continue` Statement

The `continue` statement skips the remaining statements of the current iteration and immediately proceeds to the next iteration of the loop. It does not terminate the loop.

#### Syntax

```python
continue
```

#### Example

```python
for i in range(1, 6):
    if i == 3:
        continue
    print(i)
```

Output

```text
1
2
4
5
```

---

### 🔹 `pass` Statement

The `pass` statement is a null statement that performs no operation. It is mainly used as a placeholder when the syntax requires a statement but no action needs to be performed.

#### Syntax

```python
pass
```

#### Example

```python
for i in range(1, 4):
    if i == 2:
        pass
    print(i)
```

Output

```text
1
2
3
```

---

### 🔹 `for...else` Statement

Python provides an optional `else` block with a `for` loop. The `else` block is executed only if the loop completes normally without encountering a `break` statement.

It is commonly used while searching for an element in a sequence.

#### Syntax

```python
for variable in sequence:
    # code block
else:
    # executes if loop completes normally
```

#### Example

```python
password = ["abc1234", "123", "xyz1254", "abc"]
target = "12"

for i in password:
    if i == target:
        print("Password found")
        break
else:
    print("Password not found")
```

Output

```text
Password not found
```

---

## 💻 Hands-on Practice

### 📝 Program 1: Perform Bitwise Operations

**Question:** Write a Python program to demonstrate different bitwise operators.

```python
print(13 & 8)
print(13 | 8)
print(13 ^ 8)
print(13 << 1)
print(13 << 2)
print(1 << 3)
print(13 >> 3)
print(~13)
```


![Bitwise Operators](Images/Day-02/bitwise-operators.png)

---

### 📝 Program 2: Membership Operators

**Question:** Write a Python program to demonstrate membership operators.

```python
fruits = ["Apple", "Banana", "Kiwi"]

print("Apple" in fruits)
print("Apple" not in fruits)
print("apple" in fruits)
```


![Membership Operators](Images/Day-02/membership-operators.png)

---

### 📝 Program 3: Identity Operators

**Question:** Write a Python program to demonstrate identity operators.

```python
list_x = [1, 2, 3]
list_y = [1, 2, 3]

print(id(list_x))
print(id(list_y))

print(list_x is list_y)
print(list_x is not list_y)
print(list_x == list_y)
```


![Identity Operators](Images/Day-02/identity-operators.png)

---

### 📝 Program 4: Conditional Statements

**Question:** Write a Python program to check whether a number is even and greater than zero. Also check whether it is divisible by 5 or 3.

```python
a = int(input("Enter a number: "))

if a % 2 == 0 and a > 0:
    print("Even and greater than 0")
else:
    print("Not even and greater than 0")

if a % 5 == 0 or a % 3 == 0:
    print("Divisible by 5 or 3")
else:
    print("Not divisible by 5 or 3")
```


![Conditional Statements](Images/Day-02/conditional-statements.png)

---

### 📝 Program 5: Print Even Numbers

**Question:** Write a Python program to print even numbers from 0 to 10 using the `for` loop.

```python
for i in range(0, 11, 2):
    print(i)
```


![Even Numbers](Images/Day-02/even-numbers.png)

---

### 📝 Program 6: Multiplication Table of 5

**Question:** Write a Python program to print the multiplication table of 5.

```python
for i in range(0, 11):
    print(f"5 x {i} = {5 * i}")
```


![Table of 5](Images/Day-02/table-of-5.png)

---

### 📝 Program 7: Length of Strings

**Question:** Write a Python program to display the number of characters in each programming language.

```python
language = ["Python", "SQL", "C++"]

for i in language:
    print(f"{i} has {len(i)} characters")
```


![Length of Strings](Images/Day-02/string-length.png)

---

### 📝 Program 8: Reverse Counting

**Question:** Write a Python program to print numbers in reverse order using a negative step.

```python
for i in range(10, 0, -2):
    print(i)
```


![Reverse Counting](Images/Day-02/reverse-counting.png)

---

### 📝 Program 9: Password Strength Checker

**Question:** Write a Python program to determine whether passwords are strong or weak based on their length.

```python
password = ["abc1234", "123", "xyz1254", "abc"]

for i in password:
    if len(i) >= 6:
        print("Strong password")
    else:
        print("Weak password")
```


![Password Strength](Images/Day-02/password-strength.png)

---

### 📝 Program 10: Demonstrate `while`, `break`, and `continue`

**Question:** Write a Python program using a `while` loop to demonstrate the use of `break` and `continue`.

```python
count = 4

while count >= 0:
    current_val = count
    count -= 1

    if current_val == 2:
        continue

    if current_val == 1:
        break

    print(current_val)
```


![While Loop](Images/Day-02/while-loop.png)

---

### 📝 Program 11: Search Using `for...else`

**Question:** Write a Python program to search for a password using the `for...else` statement.

```python
password = ["abc1234", "123", "xyz1254", "abc"]
target = "12"

for i in password:
    if i == target:
        print("Password found")
        break
else:
    print("Password not found")
```


![For Else](Images/Day-02/for-else.png)

---

### 📝 Program 12: Age Category Classifier

**Question:** Write a Python program to classify a person based on age.

```python
a = int(input("Enter age: "))

if a < 13:
    print("Child")
elif a >= 13 and a <= 19:
    print("Teenager")
elif a >= 20 and a <= 59:
    print("Adult")
else:
    print("Senior")
```


![Age Classifier](Images/Day-02/age-classifier.png)

---

## 💡 Key Takeaways

- Understood how bitwise operators manipulate binary data and learned their practical applications.
- Learned the difference between membership operators and identity operators.
- Explored the `range()` function with different combinations of `start`, `stop`, and `step`.
- Gained a solid understanding of `for` and `while` loops for performing repetitive tasks.
- Learned how `break`, `continue`, `pass`, and `for...else` influence loop execution.
- Reinforced the concepts by implementing multiple Python programs and observing their outputs.
