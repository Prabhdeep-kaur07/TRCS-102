# 🗓️ **DAY-05** | *26 June 2026*

## 🎯 Today's Goal

To understand advanced Python data structures including tuples, dictionaries, and sets. Learn how tuples store immutable collections, perform tuple unpacking using variables and wildcards, work with key-value pairs using dictionaries, and perform operations on sets.

## 📚 Topics Covered

1. **Tuples**
   - Introduction to Tuples
   - Creating Tuples
   - Characteristics of Tuples
   - Tuple Indexing
   - Tuple Slicing
   - Tuple Unpacking
   - Wildcard (`*`) in Tuple Unpacking

2. **Dictionaries**
   - Introduction to Dictionaries
   - Creating Dictionaries
   - Accessing Dictionary Values
   - Adding and Updating Elements
   - Dictionary Methods

3. **Sets**
   - Introduction to Sets
   - Creating Sets
   - Characteristics of Sets
   - Set Operations


## 📖 What I Learned

## 📌 Tuples

A **tuple** is an ordered and immutable collection of elements in Python. Similar to lists, tuples can store multiple values, but unlike lists, their elements cannot be modified after creation.

Tuples are useful when we want to store data that should remain constant throughout the execution of a program.

Tuples are represented using **parentheses `()`**.

### Example

```python
student = ("Prabhdeep", 20, "CSE")

print(student)
```

Output

```text
('Prabhdeep', 20, 'CSE')
```

---

## 📌 Characteristics of Tuples

- Tuples are ordered collections.
- Tuples are immutable, meaning elements cannot be changed after creation.
- Duplicate values are allowed.
- Elements can be accessed using indexing.
- Tuples can store different data types.
- Tuples are faster than lists because they cannot be modified.

---

## 📌 Creating Tuples

## 🔹 Empty Tuple

```python
t = ()

print(t)
```

Output

```text
()
```

---

## 🔹 Tuple with Multiple Elements

```python
numbers = (10, 20, 30, 40)

print(numbers)
```

Output

```text
(10, 20, 30, 40)
```

---

## 🔹 Tuple Without Parentheses

Python also allows tuple creation without using parentheses.

```python
data = 10, 20, 30

print(data)
```

Output

```text
(10, 20, 30)
```

---

## 🔹 Single Element Tuple

A comma is required when creating a tuple with only one element.

```python
a = (10,)

print(type(a))
```

Output

```text
<class 'tuple'>
```

Without the comma, Python treats it as an integer.

```python
a = (10)

print(type(a))
```

Output

```text
<class 'int'>
```

---

## 📌 Tuple Indexing

Each element in a tuple has an index position.

- Positive indexing starts from `0`.
- Negative indexing starts from `-1`.

Example:

```python
languages = ("Python", "Java", "C++", "SQL")

print(languages[0])
print(languages[-1])
```

Output

```text
Python
SQL
```

---

## 📌 Tuple Slicing

Tuple slicing is used to access multiple elements from a tuple.

## Syntax

```python
tuple[start : stop : step]
```

Where:

- **start** → Starting index (included)
- **stop** → Ending index (excluded)
- **step** → Number of positions skipped

### Example

```python
numbers = (10, 20, 30, 40, 50, 60)

print(numbers[1:4])
print(numbers[:3])
print(numbers[::2])
```

Output

```text
(20, 30, 40)
(10, 20, 30)
(10, 30, 50)
```

---

## 📌 Tuple Unpacking

Tuple unpacking allows us to assign tuple elements directly to multiple variables in a single statement.

Instead of accessing elements using indexes, Python automatically assigns values to variables.

### Example

```python
student = ("Aman", 20, "AI/ML")

name, age, course = student

print(name)
print(age)
print(course)
```

Output

```text
Aman
20
AI/ML
```

Here:

- `name` stores `"Aman"`
- `age` stores `20`
- `course` stores `"AI/ML"`

---

## 📌 Wildcard (`*`) in Tuple Unpacking

The wildcard operator `*` is used when we do not know how many values should be assigned to a variable.

The variable with `*` collects all remaining values into a list.

### Example

```python
numbers = (10, 20, 30, 40, 50)

a, b, *c = numbers

print(a)
print(b)
print(c)
```

Output

```text
10
20
[30, 40, 50]
```

Explanation:

- `a` receives the first value.
- `b` receives the second value.
- `c` collects all remaining values.

---

## 🔹 Wildcard at the Beginning

```python
numbers = (10, 20, 30, 40, 50)

*a, b, c = numbers

print(a)
print(b)
print(c)
```

Output

```text
[10, 20, 30]
40
50
```

The wildcard can be placed anywhere during tuple unpacking depending on which values need to be grouped together.

## 📌 Dictionaries

A **dictionary** is a built-in data structure in Python that stores data in the form of **key-value pairs**. Each key is unique and is used to access its corresponding value.

Dictionaries are mutable, meaning their elements can be modified after creation.

Dictionaries are represented using **curly brackets `{}`**.

### Example

```python
student = {
    "name": "Prabhdeep",
    "age": 20,
    "course": "CSE"
}

print(student)
```

Output

```text
{'name': 'Prabhdeep', 'age': 20, 'course': 'CSE'}
```

---

## 📌 Characteristics of Dictionaries

- Data is stored in key-value pairs.
- Keys must be unique.
- Values can be duplicated.
- Dictionaries are mutable.
- Keys must be immutable data types such as strings, numbers, or tuples.
- Values can be of any data type.
- Elements are accessed using keys instead of indexes.

---

## 📌 Creating a Dictionary

### 🔹 Empty Dictionary

```python
data = {}

print(data)
```

Output

```text
{}
```

---

### 🔹 Dictionary with Elements

```python
student = {
    "name": "Aman",
    "roll_no": 101,
    "marks": 95
}

print(student)
```

Output

```text
{'name': 'Aman', 'roll_no': 101, 'marks': 95}
```

---

## 📌 Accessing Dictionary Values

Values in dictionaries are accessed using their keys.

### Example

```python
student = {
    "name": "Aman",
    "age": 20
}

print(student["name"])
print(student["age"])
```

Output

```text
Aman
20
```

---

## 🔹 Using `get()` Method

The `get()` method is used to access values safely. If the key does not exist, it returns `None` instead of generating an error.

### Example

```python
student = {
    "name": "Aman",
    "age": 20
}

print(student.get("name"))
print(student.get("course"))
```

Output

```text
Aman
None
```

---

## 📌 Adding and Updating Dictionary Elements

New key-value pairs can be added by assigning a value to a new key.

Existing values can be updated by assigning a new value to an existing key.

### Example

```python
student = {
    "name": "Aman",
    "age": 20
}

student["course"] = "AI/ML"

student["age"] = 21

print(student)
```

Output

```text
{'name': 'Aman', 'age': 21, 'course': 'AI/ML'}
```

---

## 📌 Dictionary Methods

Python provides several built-in methods to work with dictionaries.

---

## 🔹 `keys()`

Returns all keys present in the dictionary.

### Example

```python
student = {
    "name": "Aman",
    "age": 20,
    "course": "CSE"
}

print(student.keys())
```

Output

```text
dict_keys(['name', 'age', 'course'])
```

---

## 🔹 `values()`

Returns all values present in the dictionary.

### Example

```python
print(student.values())
```

Output

```text
dict_values(['Aman', 20, 'CSE'])
```

---

## 🔹 `items()`

Returns all key-value pairs as tuples.

### Example

```python
print(student.items())
```

Output

```text
dict_items([('name', 'Aman'), ('age', 20), ('course', 'CSE')])
```

---

## 🔹 `update()`

The `update()` method is used to add new elements or modify existing values.

### Example

```python
student.update({"age":21,"city":"Ludhiana"})

print(student)
```

Output

```text
{'name':'Aman','age':21,'course':'CSE','city':'Ludhiana'}
```

---

## 🔹 `pop()`

The `pop()` method removes an element using its key and returns the removed value.

### Example

```python
student.pop("age")

print(student)
```

Output

```text
{'name':'Aman','course':'CSE','city':'Ludhiana'}
```

---

## 📌 Sets

A **set** is an unordered collection of unique elements in Python. Sets do not allow duplicate values and are mainly used for mathematical operations such as union, intersection, and difference.

Sets are represented using **curly brackets `{}`**.

### Example

```python
numbers = {10,20,30,40}

print(numbers)
```

Output

```text
{10,20,30,40}
```

---

## 📌 Characteristics of Sets

- Sets are unordered.
- Sets do not allow duplicate elements.
- Sets are mutable.
- Elements cannot be accessed using indexing.
- Sets can store multiple data types.
- Sets are useful for removing duplicate values.

---

## 📌 Creating a Set

### 🔹 Empty Set

An empty set is created using `set()` because `{}` creates an empty dictionary.

```python
s = set()

print(type(s))
```

Output

```text
<class 'set'>
```

---

### 🔹 Set with Elements

```python
colors = {"red","blue","green"}

print(colors)
```

Output

```text
{'red','blue','green'}
```

---

## 📌 Removing Duplicate Values Using Set

```python
numbers = [10,20,20,30,30,40]

unique_numbers = set(numbers)

print(unique_numbers)
```

Output

```text
{10,20,30,40}
```

---

## 📌 Set Operations

Sets support mathematical operations between different sets.

---

## 🔹 Union (`|`)

Union combines all elements from both sets.

### Example

```python
A = {1,2,3}
B = {3,4,5}

print(A | B)
```

Output

```text
{1,2,3,4,5}
```

---

## 🔹 Intersection (`&`)

Intersection returns common elements present in both sets.

### Example

```python
print(A & B)
```

Output

```text
{3}
```

---

## 🔹 Difference (`-`)

Difference returns elements present in the first set but not in the second set.

### Example

```python
print(A - B)
```

Output

```text
{1,2}
```

---

## 🔹 Symmetric Difference (`^`)

Returns elements that are present in either set but not common in both.

### Example

```python
print(A ^ B)
```

Output

```text
{1,2,4,5}
```

---

# 📊 Difference Between List, Tuple, Dictionary and Set

| Feature | List | Tuple | Dictionary | Set |
|---------|------|-------|------------|-----|
| Ordered | Yes | Yes | Yes (Python 3.7+) | No |
| Mutable | Yes | No | Yes | Yes |
| Duplicate Values | Allowed | Allowed | Keys: No, Values: Yes | Not Allowed |
| Indexing | Supported | Supported | Key-based Access | Not Supported |
| Symbol | `[]` | `()` | `{key:value}` | `{}` |

## 👩‍💻 Hands-on Practice

## Program 1: Find Pairs with Given Sum Using List

**Question:** Write a Python program to find pairs of elements from a list whose sum is equal to 11.

### Code

```python
numbers = [1,8,10,10,8,8,3,5]

visited = []
result = []

for i in numbers:
    diff = 11 - i

    if diff in visited:
        result.append((i, diff))
        visited.remove(diff)

    else:
        visited.append(i)

print(result)
```


![Pair Sum](Images/Day-05/pair-sum.png)

---

# Program 2: Tuple Unpacking

**Question:** Write a Python program to unpack tuple values into different variables.

### Code

```python
tuple1 = (10,20,30)

print(type(tuple1))

l,b,h = tuple1

print(l)

print(l*b*h)
```


![Tuple Unpacking](Images/Day-05/tuple-unpacking.png)

---

# Program 3: Tuple Unpacking Using Wildcard (*)

**Question:** Write a Python program to extract multiple values from a tuple using wildcard unpacking.

### Code

```python
tuple2 = (10,"Simran",80,90,30,10,"9th")

age,name,*expenses,course = tuple2

print(age)

print(expenses)

print(sum(expenses))
```

![Wildcard Tuple](Images/Day-05/wildcard-tuple.png)

---

# Program 4: Nested Tuple Unpacking

**Question:** Write a Python program to unpack nested tuples containing training, validation, and testing data.

### Code

```python
splits = (
    ([1.2,3.4,5.6],[0,1,0]),
    ([2.1,3.4],[1,5]),
    ([2,1],[3,4])
)

print(splits)

train,val,test = splits

x_train,y_train = train

print(len(x_train))

x_val,y_val = val

x_test,y_test = test

print(len(x_val))

print(len(x_test))
```

![Nested Tuple](Images/Day-05/nested-tuple.png)

---

# Program 5: Convert Tuple into List and Modify

**Question:** Write a Python program to convert a tuple into a list, perform modifications, and convert it back into a tuple.

### Code

```python
tuple1 = (10,20,30,40,50,60)

list1 = list(tuple1)

list1.insert(1,100)

list1.append(1000)

tuple1 = tuple(list1)

print(tuple1)
```


![Tuple Conversion](Images/Day-05/tuple-list.png)

---

# Program 6: Dictionary Creation and Operations

**Question:** Write a Python program to create a dictionary and perform different dictionary operations.

### Code

```python
student = {
    "Name":"Simran",
    "Course":"B.Tech",
    "RollNo.":101
}

print(student)

print(student.keys())

print(student.items())

print(student.values())


for key,value in student.items():
    print(f"-{key} : {value}")


student['RollNo.'] = 103

print(student.items())


student["School"] = "GNDEC"

print(student)
```


![Dictionary Operations](Images/Day-05/dictionary.png)

---

# Program 7: Count Frequency of Elements

**Question:** Write a Python program to count the frequency of elements in a list using a dictionary.

### Code

```python
data = [100,300,200,300,400]

count = {}

for i in data:
    count[i] = data.count(i)

print(count)
```


![Frequency Count](Images/Day-05/frequency.png)

---

# Program 8: Set Creation and Operations

**Question:** Write a Python program to perform different operations on sets.

### Code

```python
train_classes = {"cat","dog","bird","cat"}

val_classes = {"dog","horse","sheep"}


print("Union:", train_classes.union(val_classes))

print("Union:", train_classes | val_classes)


print("Intersection:", train_classes.intersection(val_classes))

print("Intersection:", train_classes & val_classes)


print("Symmetric Difference:",
      train_classes.symmetric_difference(val_classes))


print("Difference:",
      train_classes - val_classes)


print("Difference:",
      val_classes - train_classes)
```


![Set Operations](Images/Day-05/set-operations.png)

---

# Program 9: Find Unseen Classes Using Sets

**Question:** Write a Python program to find classes present in testing data but missing from training data.

### Code

```python
train_labels = [
    "tumor",
    "healthy",
    "healthy",
    "tumor",
    "cysts",
    "tumor"
]

test_labels = [
    "tumor",
    "healthy",
    "fibroid",
    "tumor"
]


set_train = set(train_labels)

set_test = set(test_labels)


print(
"Classes in Test but not in Train:",
set_test-set_train
)


print(set_test)

print(set_train)

print("Union:", set_train | set_test)
```


![Unseen Classes](Images/Day-05/unseen-classes.png)

---

# Program 10: Separate Temperature Values Using Lists

**Question:** Write a Python program to separate temperatures into cold and hot categories.

### Code

```python
temp = [28,32,18,15,30,22,17]

cold = []

hot = []


for i in temp:

    if i < 20:
        cold.append(i)

    else:
        hot.append(i)


print(cold)

print(hot)
```


![Temperature List](Images/Day-05/temperature.png)

---

# Program 11: Tuple Based Student Record

**Question:** Write a Python program to extract student information from a tuple.

### Code

```python
student_record = ("S105","Ananya",20,"AI/ML")

student_id,name,age,course = student_record


print(
f"Student {name} (ID {student_id}) is {age} years old and is enrolled in {course}"
)
```


![Student Record](Images/Day-05/student-record.png)

---

# Program 12: Dictionary Inventory Management

**Question:** Write a Python program to manage book inventory using dictionaries.

### Code

```python
inventory = {
    "Python Guide":12,
    "Maths for ML":5,
    "AI Basics":8
}


if "Data Science Handbook" in inventory:

    pass

else:

    inventory["Data Science Handbook"] = 10


inventory["Maths for ML"] -= 3


print(inventory)


for k in inventory:

    inventory[k] += 10


print(inventory)
```


![Dictionary Inventory](Images/Day-05/inventory.png)

---

## 💻 What I Practiced

- Created and manipulated tuples in Python.
- Learned tuple unpacking to assign multiple values to variables.
- Used wildcard (`*`) unpacking to collect multiple remaining values.
- Worked with nested tuples and extracted training, validation, and testing data.
- Converted tuples into lists for modification and converted them back.
- Created dictionaries and performed operations using keys, values, and items.
- Counted element frequency using dictionaries.
- Created sets and performed union, intersection, difference, and symmetric difference operations.
- Used sets to identify unique and unseen classes in datasets.
- Applied lists, tuples, dictionaries, and sets to solve practical programming problems.

---

## 💡 Key Takeaway

Today's session introduced me to powerful Python data structures beyond lists. I learned how tuples provide immutable storage and support efficient data unpacking, including wildcard unpacking. I explored dictionaries for storing and managing data using key-value pairs and understood how sets help in handling unique values and performing mathematical operations. These data structures are extremely important in Data Science and Machine Learning for handling datasets, storing information, and performing efficient data processing operations.
