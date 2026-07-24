# 🗓️ **DAY-06** | *29 June 2026*

## 🎯 Today's Goal

Install NumPy in Visual Studio Code and learn the fundamentals of NumPy arrays. Understand why NumPy is preferred over Python lists for numerical computations and explore the basics of creating arrays and their attributes.

## 📚 Topics Covered

1. **Installing NumPy**
2. **Python Lists vs NumPy Arrays**
3. **Creating NumPy Arrays**
4. **Array Attributes**
5. **Performance Comparison**

## 📖 What I Learned

## 📌 Installing NumPy in VS Code

Today, I learned about **NumPy (Numerical Python)**, one of the most important Python libraries used in Data Science, Machine Learning, Artificial Intelligence, and Scientific Computing. NumPy provides a powerful **N-dimensional array** object and numerous mathematical functions that make numerical computations much faster than standard Python.

Before using NumPy, it needs to be installed in the Python environment.

### Installation

Open the **VS Code Terminal** and run the following command:

```bash
pip install numpy
```

If NumPy is already installed, it can be updated using:

```bash
pip install --upgrade numpy
```

### Verifying the Installation

```python
import numpy as np

print(np.__version__)
```

---

## 📌 Python Lists vs NumPy Arrays

Python provides **lists** to store collections of data, but lists are designed for general-purpose programming. In contrast, **NumPy arrays** are specifically designed for numerical computations and mathematical operations.

Unlike Python lists, NumPy arrays store elements of the **same data type**, making them more memory-efficient and significantly faster for large datasets. NumPy also supports **vectorized operations**, allowing mathematical calculations to be performed on an entire array without using loops.

### Python List Example

```python
numbers = [10, 20, 30, 40, 50]

print(numbers)
```

Output

```text
[10, 20, 30, 40, 50]
```

### NumPy Array Example

```python
import numpy as np

numbers = np.array([10, 20, 30, 40, 50])

print(numbers)
```

Output

```text
[10 20 30 40 50]
```

---

## 📊 Difference Between Python Lists and NumPy Arrays

| Python Lists | NumPy Arrays |
|--------------|--------------|
| General-purpose data structure | Designed for numerical computing |
| Can store different data types | Stores homogeneous data |
| Slower for mathematical operations | Extremely fast due to vectorization |
| Higher memory consumption | Memory efficient |
| Requires loops for calculations | Supports direct element-wise operations |
| Suitable for small datasets | Suitable for large datasets and AI/ML |

---

## 📌 Performance Comparison

One of the biggest advantages of NumPy is its speed. Python lists perform operations element by element using loops, whereas NumPy performs calculations on the entire array simultaneously through **vectorization**, resulting in much faster execution.

### Python List

```python
numbers = [1, 2, 3, 4, 5]

result = []

for num in numbers:
    result.append(num * 2)

print(result)
```

Output

```text
[2, 4, 6, 8, 10]
```

### NumPy Array

```python
import numpy as np

numbers = np.array([1, 2, 3, 4, 5])

print(numbers * 2)
```

Output

```text
[ 2  4  6  8 10]
```

Using vectorized operations eliminates the need for explicit loops, making NumPy code shorter, easier to read, and significantly faster.

---

## 📌 Creating NumPy Arrays

NumPy arrays are created using the **`array()`** function.

### Syntax

```python
np.array(iterable)
```

### Creating a One-Dimensional Array

```python
import numpy as np

arr = np.array([10, 20, 30, 40, 50])

print(arr)
```

Output

```text
[10 20 30 40 50]
```

### Creating a Two-Dimensional Array

```python
arr = np.array([
    [1, 2, 3],
    [4, 5, 6]
])

print(arr)
```

Output

```text
[[1 2 3]
 [4 5 6]]
```

### Creating a Three-Dimensional Array

```python
arr = np.array([
    [[1, 2], [3, 4]],
    [[5, 6], [7, 8]]
])

print(arr)
```

Output

```text
[[[1 2]
  [3 4]]

 [[5 6]
  [7 8]]]
```

---

## 📌 NumPy Array Attributes

NumPy provides several built-in attributes that describe the structure and properties of an array.

### `shape`

Returns the dimensions of an array.

```python
arr = np.array([[1, 2, 3], [4, 5, 6]])

print(arr.shape)
```

Output

```text
(2, 3)
```

---

### `ndim`

Returns the number of dimensions.

```python
print(arr.ndim)
```

Output

```text
2
```

---

### `size`

Returns the total number of elements.

```python
print(arr.size)
```

Output

```text
6
```

---

### `dtype`

Returns the data type of the array.

```python
print(arr.dtype)
```

Output

```text
int64
```

---

### `itemsize`

Returns the size of each element in bytes.

```python
print(arr.itemsize)
```

Output

```text
8
```

---

### `nbytes`

Returns the total memory occupied by the array.

```python
print(arr.nbytes)
```

Output

```text
48
```
## 📌 Indexing

**Indexing** is used to access individual elements of a NumPy array using their position (index). Like Python lists, NumPy arrays support both **positive** and **negative indexing**.

- Positive indexing starts from **0**.
- Negative indexing starts from **-1** (last element).

### Indexing in a 1-D Array

```python
import numpy as np

arr = np.array([10, 20, 30, 40, 50])

print(arr[0])
print(arr[2])
print(arr[-1])
```

Output

```text
10
30
50
```

---

### Indexing in a 2-D Array

A two-dimensional array uses **row index** followed by **column index**.

```python
arr = np.array([
    [10, 20, 30],
    [40, 50, 60]
])

print(arr[0, 1])
print(arr[1, 2])
```

Output

```text
20
60
```

---

## 📌 Slicing

**Slicing** allows us to extract multiple elements from an array. It follows the same syntax as Python lists.

### Syntax

```python
array[start : stop : step]
```

Where:

- **start** → Starting index (included)
- **stop** → Ending index (excluded)
- **step** → Number of positions to skip

### 1-D Array Slicing

```python
arr = np.array([10,20,30,40,50,60])

print(arr[1:4])
print(arr[:3])
print(arr[3:])
print(arr[::2])
```

Output

```text
[20 30 40]
[10 20 30]
[40 50 60]
[10 30 50]
```

---

### 2-D Array Slicing

```python
arr = np.array([
    [10,20,30],
    [40,50,60],
    [70,80,90]
])

print(arr[0:2,1:3])
```

Output

```text
[[20 30]
 [50 60]]
```

The first slice selects the rows, while the second slice selects the columns.

---

## 📌 NumPy Built-in Functions

NumPy provides many built-in mathematical functions that work directly on arrays without writing loops.

### `sum()`

Returns the sum of all elements.

```python
arr = np.array([10,20,30,40])

print(np.sum(arr))
```

Output

```text
100
```

---

### `min()`

Returns the smallest element.

```python
print(np.min(arr))
```

Output

```text
10
```

---

### `max()`

Returns the largest element.

```python
print(np.max(arr))
```

Output

```text
40
```

---

### `mean()`

Returns the average of all elements.

```python
print(np.mean(arr))
```

Output

```text
25.0
```

---

### `std()`

Returns the standard deviation.

```python
print(np.std(arr))
```

Output

```text
11.18
```

---

### `sqrt()`

Returns the square root of every element.

```python
print(np.sqrt(arr))
```

Output

```text
[3.16227766 4.47213595 5.47722558 6.32455532]
```

---

## 📌 Boolean Indexing

Boolean indexing is used to filter elements based on a condition.

Instead of looping through every element, NumPy automatically returns only those elements that satisfy the given condition.

### Example

```python
arr = np.array([10,20,30,40,50])

print(arr[arr > 25])
```

Output

```text
[30 40 50]
```

---

Another example:

```python
marks = np.array([45,80,32,91,66])

print(marks[marks >= 50])
```

Output

```text
[80 91 66]
```

Boolean indexing is widely used in Data Science for filtering datasets.

---

## 📌 Broadcasting

**Broadcasting** is a feature of NumPy that allows mathematical operations between arrays of different shapes without manually resizing them.

Instead of repeating values, NumPy automatically expands the smaller array to match the larger one.

### Example

```python
arr = np.array([10,20,30,40])

print(arr + 5)
```

Output

```text
[15 25 35 45]
```

Every element is increased by **5**.

---

Another example:

```python
arr = np.array([1,2,3])

print(arr * 10)
```

Output

```text
[10 20 30]
```

Broadcasting makes mathematical operations concise and efficient.

---

## 📌 Reshaping Arrays

The **reshape()** function changes the shape of an array without changing its data.

### Syntax

```python
array.reshape(rows, columns)
```

### Example

```python
arr = np.array([1,2,3,4,5,6])

new_arr = arr.reshape(2,3)

print(new_arr)
```

Output

```text
[[1 2 3]
 [4 5 6]]
```

---

Another example:

```python
new_arr = arr.reshape(3,2)

print(new_arr)
```

Output

```text
[[1 2]
 [3 4]
 [5 6]]
```

Reshaping is frequently used before training Machine Learning models.

---

## 📌 Dot Product

The **dot product** is one of the most important mathematical operations in Linear Algebra and Machine Learning.

It multiplies corresponding elements of two vectors and then adds the results.

### Formula

```
A · B = (a₁×b₁) + (a₂×b₂) + ... + (aₙ×bₙ)
```

### Example

```python
a = np.array([1,2,3])

b = np.array([4,5,6])

print(np.dot(a,b))
```

Output

```text
32
```

Calculation:

```
(1×4) + (2×5) + (3×6)

= 4 + 10 + 18

= 32
```

The dot product is widely used in **Machine Learning**, **Deep Learning**, **Computer Vision**, and **Neural Networks** for performing matrix and vector calculations.
## 👩‍💻 Hands-on Practice

### Program 1: Creating NumPy Arrays

**Question:** Write a Python program to create one-dimensional and two-dimensional NumPy arrays.

#### Code

```python
import numpy as np

list2 = [
    [1,2,3],
    [4,5,6],
    [7,8,9]
]

arr2d = np.array(list2)

print(list2)
print(arr2d)
print(type(arr2d))
```


![Creating Arrays](Images/Day-06/create-array.png)

---

### Program 2: Creating Arrays with Different NumPy Functions

**Question:** Write a Python program to create arrays using NumPy built-in functions.

#### Code

```python
import numpy as np

print(np.zeros((5,5)))

print(np.ones((4,5)))

print(np.arange(0,10,2))

print(np.linspace(1,5,10))

print(np.eye(4))
```


![NumPy Functions](Images/Day-06/numpy-functions.png)

---

### Program 3: Array Attributes

**Question:** Write a Python program to display the attributes of a NumPy array.

#### Code

```python
import numpy as np

my_matrix = np.array(
    [[1,2,3],
     [4,5,6]],
    dtype=np.int32
)

print(my_matrix)

print("Dimensions :", my_matrix.ndim)

print("Shape :", my_matrix.shape)

print("Size :", my_matrix.size)

print("Data Type :", my_matrix.dtype)

print("Item Size :", my_matrix.itemsize)
```


![Array Attributes](Images/Day-06/attributes.png)

---

### Program 4: Indexing and Slicing

**Question:** Write a Python program to demonstrate indexing and slicing in NumPy arrays.

#### Code

```python
import numpy as np

matrix = np.array([
    [1,2,3],
    [4,5,6],
    [7,8,9]
])

print(matrix[0,1])

print(matrix[:,0:2])

print(matrix[1:3,1:3])
```


![Indexing](Images/Day-06/indexing.png)

---

### Program 5: Boolean Indexing

**Question:** Write a Python program to filter elements using Boolean indexing.

#### Code

```python
import numpy as np

data = np.array([5,12,8,21,3,14,7])

print(data[data > 12])

print(data[data < 10])

data[data < 8] = 8

print(data)
```


![Boolean Indexing](Images/Day-06/boolean.png)

---

### Program 6: Reshaping and Flattening Arrays

**Question:** Write a Python program to reshape and flatten a NumPy array.

#### Code

```python
import numpy as np

flat_arr = np.arange(6)

print("Original:", flat_arr)

matrix_2d = flat_arr.reshape(2,3)

print(matrix_2d)

flattened = matrix_2d.flatten()

print(flattened)
```


![Reshape](Images/Day-06/reshape.png)

---

### Program 7: Dot Product

**Question:** Write a Python program to calculate the dot product of two NumPy arrays.

#### Code

```python
import numpy as np

inputs = np.array([1.0,2.0])

weights = np.array([
    [0.2,0.3,-0.5],
    [0.5,-0.6,-0.7]
])

print(np.dot(inputs,weights))
```


![Dot Product](Images/Day-06/dot-product.png)

---

### Program 8: Temperature Conversion Using NumPy

**Question:** Write a Python program to convert temperatures from Celsius to Fahrenheit using NumPy.

#### Code

```python
import numpy as np

celsius = np.array([0,10,25,36.6,40])

fahrenheit = celsius * (9/5) + 32

print("Temperature in Fahrenheit:")

print(fahrenheit)
```


![Temperature Conversion](Images/Day-06/temperature.png)
## 💻 What I Practiced

- Installed the NumPy library and imported it using the `numpy` package.
- Created one-dimensional and two-dimensional NumPy arrays from Python lists.
- Generated arrays using built-in NumPy functions such as `zeros()`, `ones()`, `arange()`, `linspace()`, and `eye()`.
- Explored important array attributes including `shape`, `ndim`, `size`, `dtype`, and `itemsize`.
- Accessed and modified array elements using indexing.
- Extracted subsets of arrays using slicing techniques.
- Filtered and updated array elements using Boolean indexing.
- Performed statistical operations such as calculating the mean of arrays.
- Reshaped one-dimensional arrays into two-dimensional arrays and flattened them back to one dimension.
- Calculated the dot product of vectors using NumPy.
- Applied vectorized operations to solve real-world problems like temperature conversion from Celsius to Fahrenheit.

---

## 💡 Key Takeaway

Today's session marked my introduction to **NumPy**, one of the most essential libraries for Data Science, Machine Learning, and Artificial Intelligence. I learned why NumPy arrays are preferred over Python lists due to their speed, memory efficiency, and support for vectorized operations. I practiced creating and manipulating arrays, explored array attributes, performed indexing and slicing, filtered data using Boolean indexing, reshaped arrays, and carried out mathematical operations such as finding means and dot products. These concepts form the foundation of numerical computing in Python and are crucial for efficient data preprocessing, linear algebra, and building Machine Learning models.
