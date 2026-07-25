# **DAY-07** | *30 June 2026*

## 🎯 Today's Goal

Strengthen my Python programming skills by solving coding problems based on NumPy, functions, recursion, dictionaries, loops, strings, and introductory Machine Learning concepts. The objective was to apply the concepts learned during previous sessions to improve logical thinking, debugging skills, and problem-solving ability.

## 📚 Topics Covered

1. NumPy Random Number Generation
2. Functions and Recursion
3. Dictionary and String Programming
4. Problem Solving with Python
5. Machine Learning Evaluation Metrics

## 📖 What I Learned

Today's session was completely focused on solving programming problems rather than learning new syntax or concepts. The aim was to reinforce previously learned Python and NumPy concepts by applying them to different logical and real-world scenarios.

Through these exercises, I revised the use of Python functions, recursion, loops, dictionaries, strings, conditional statements, and NumPy. I practiced breaking larger problems into smaller reusable functions, making the programs easier to understand, maintain, and debug.

One of the important concepts I explored was **random number generation** using NumPy. By setting a random seed using `np.random.seed()`, I learned that the same sequence of random numbers can be generated every time the program is executed. This is especially useful in Machine Learning because it makes experiments reproducible.

I also solved several logical programming problems, including counting label frequencies using dictionaries, finding prime numbers within a given range, calculating powers using recursion, and finding the sum of digits of a number. These exercises strengthened my understanding of loops, recursion, conditional statements, and function design.

Towards the end of the session, I implemented a function to calculate **Precision** and **Recall**, two important evaluation metrics used in Machine Learning classification problems. I learned how **True Positives (TP)**, **False Positives (FP)**, and **False Negatives (FN)** are calculated and how these values are used to measure the performance of a predictive model.

Overall, today's session emphasized applying theoretical concepts through practical coding exercises, helping me improve my logical thinking, debugging skills, and confidence in Python programming.

---

#  Hands-on Practice

## Program 1: Generate Random Numbers Using NumPy

**Question:**

Write a Python program to generate random numbers using NumPy's `rand()` and `randn()` functions. Also, use `np.random.seed()` to ensure reproducible random values.

### Code

```python
import numpy as np

np.random.seed(42)

uniform_arr = np.random.rand(2, 3)
print("Uniform Array:")
print(uniform_arr)

normal_arr = np.random.randn(3, 2)
print("\nStandard Normal Distribution:")
print(normal_arr)
```

```markdown
![Program 1 Output](Images/Day-07/program1.png)
```

---

## Program 2: Count Label Frequencies Using a Dictionary

**Question:**

Without importing any external module (such as `collections`), write a Python function `count_frequencies(label_list)` that takes a list of labels and returns a dictionary where the keys are the unique labels and the values are their occurrence counts.

### Code

```python
labels = ["tumor", "healthy", "tumor", "cyst", "tumor", "healthy"]

count = {}

def count_frequencies(label_list):
    for label in label_list:
        if label not in count:
            count[label] = 1
        else:
            count[label] += 1
    return count

print(count_frequencies(labels))
```


```markdown
![Program 2 Output](Images/Day-07/program2.png)
```

---

## Program 3: Find Prime Numbers Within a Range

**Question:**

Write a Python function `is_prime(n)` to check whether a number is prime. Then write another function `get_primes_in_range(start, end)` that returns all prime numbers between the given range by calling the `is_prime()` function.

### Code

```python
def is_prime(n):
    if n < 2:
        return False

    for i in range(2, int(n ** 0.5) + 1):
        if n % i == 0:
            return False

    return True


def get_primes_in_range(start, end):
    primes = []

    for num in range(start, end + 1):
        if is_prime(num):
            primes.append(num)

    return primes


result = get_primes_in_range(10, 50)
print(result)
```

```markdown
![Program 3 Output](Images/Day-07/program3.png)
```

---

## Program 4: Calculate Power Using Recursion

**Question:**

Write a recursive function `recursive_power(base, exponent)` that calculates the value of `base` raised to the power of `exponent` without using the `**` operator or the `math` module.

### Code

```python
def recursive_power(base, exponent):
    if exponent == 0:
        return 1
    else:
        return base * recursive_power(base, exponent - 1)


result = recursive_power(3, 4)
print("Result:", result)
```


```markdown
![Program 4 Output](Images/Day-07/program4.png)
```

---

## Program 5: Sum of Digits of a Number

**Question:**

Write a Python function `sum_of_digits(n)` that takes a positive integer and returns the sum of all its digits without converting the number into a string.

### Code

```python
def sum_of_digits(n):
    total = 0

    while n > 0:
        digit = n % 10
        total += digit
        n = n // 10

    return total


result = sum_of_digits(12345)
print("Sum:", result)
```
---

```markdown
![Program 5 Output](Images/Day-07/program5.png)
```
## Program 6: Calculate Precision and Recall

**Question:**

Write a Python function `calculate_precision_recall(actual, predicted)` that computes **True Positives (TP)**, **False Positives (FP)**, **False Negatives (FN)**, **Precision**, and **Recall** for a binary classification problem. The function should also handle division-by-zero cases.

### Code

```python
def calculate_precision_recall(actual, predicted):
    TP = 0
    FP = 0
    FN = 0

    for i in range(len(actual)):
        if actual[i] == 1 and predicted[i] == 1:
            TP += 1
        elif actual[i] == 0 and predicted[i] == 1:
            FP += 1
        elif actual[i] == 1 and predicted[i] == 0:
            FN += 1

    precision = TP / (TP + FP) if (TP + FP) != 0 else 0
    recall = TP / (TP + FN) if (TP + FN) != 0 else 0

    print("True Positives =", TP)
    print("False Positives =", FP)
    print("False Negatives =", FN)
    print("Precision =", precision)
    print("Recall =", recall)


actual = [1, 0, 1, 1, 0, 0, 1, 0, 1, 1]
predicted = [1, 0, 0, 1, 0, 1, 1, 0, 1, 0]

calculate_precision_recall(actual, predicted)
```


```markdown
![Program 6 Output](Images/Day-07/program6.png)
```

---

## Program 7: Calculate Jaccard Similarity

**Question:**

Write a Python function `jaccard_similarity(doc1, doc2)` that calculates the Jaccard Similarity between two text documents by converting them into lowercase word sets and finding the ratio of the intersection to the union.

### Code

```python
def jaccard_similarity(doc1, doc2):
    set1 = set(doc1.lower().split())
    set2 = set(doc2.lower().split())

    intersection = set1.intersection(set2)
    union = set1.union(set2)

    similarity = len(intersection) / len(union)

    return similarity


doc1 = "Python is great for machine learning"
doc2 = "Machine learning in Python is awesome"

print("Jaccard Similarity:", jaccard_similarity(doc1, doc2))
```


```markdown
![Program 7 Output](Images/Day-07/program7.png)
```

---

## Program 8: Validate Image Shape

**Question:**

Write a Python function `validate_image_shape(shape_tuple)` that checks whether an image is square and has either **1 channel (grayscale)** or **3 channels (RGB)**.

### Code

```python
def validate_image_shape(shape_tuple):
    height, width, channels = shape_tuple

    if height == width and (channels == 1 or channels == 3):
        return True

    return False


print(validate_image_shape((224, 224, 3)))
print(validate_image_shape((128, 256, 3)))
print(validate_image_shape((512, 512, 4)))
```


```markdown
![Program 8 Output](Images/Day-07/program8.png)
```

---

## Program 9: Detect Sensor Anomalies

**Question:**

Write a Python program that searches a list of sensor readings for anomalies (values less than **0.0** or greater than **100.0**). If an anomaly is found, print its index and value, then terminate the loop using `break`. If no anomaly is found, print **"All sensor readings are normal."** using the `for...else` construct.

### Code

```python
readings_1 = [12.5, 45.2, 98.9, 0.5, 76.1]
readings_2 = [12.5, 45.2, -1.2, 98.9, 105.4]

print("Checking readings_1:")

for index, value in enumerate(readings_1):
    if value < 0.0 or value > 100.0:
        print(f"Anomaly found at index {index}: {value}")
        break
else:
    print("All sensor readings are normal.")

print("\nChecking readings_2:")

for index, value in enumerate(readings_2):
    if value < 0.0 or value > 100.0:
        print(f"Anomaly found at index {index}: {value}")
        break
else:
    print("All sensor readings are normal.")
```

```markdown
![Program 9 Output](Images/Day-07/program9.png)
```

---

## Program 10: Check Whether a String is a Palindrome

**Question:**

Write a Python function `is_palindrome(text)` that checks whether a given string is a palindrome while ignoring spaces, punctuation, and letter case.

### Code

```python
import string

def is_palindrome(text):
    cleaned = ""

    for char in text.lower():
        if char.isalnum():
            cleaned += char

    return cleaned == cleaned[::-1]


print(is_palindrome("A man a plan a canal Panama"))
print(is_palindrome("Machine Learning"))
```

```markdown
![Program 10 Output](Images/Day-07/program10.png)
```

---

## 💻 What I Practiced

- Solved programming problems using Python and NumPy.
- Applied functions, recursion, loops, and conditional statements to solve logical problems.
- Used dictionaries to count the frequency of categorical data.
- Generated random numbers using NumPy for reproducible experiments.
- Implemented mathematical and string-based algorithms.
- Calculated Machine Learning evaluation metrics such as Precision and Recall.
- Explored set operations through Jaccard Similarity.
- Practiced debugging and writing modular, reusable Python code.

## 💡 Key Takeaway

Today's session emphasized the importance of applying theoretical concepts through practical programming exercises. By solving a variety of logical, mathematical, and Machine Learning-oriented problems, I strengthened my understanding of Python, NumPy, recursion, dictionaries, strings, and evaluation metrics. This hands-on practice enhanced my coding confidence, improved my debugging skills, and reinforced the importance of problem-solving as a key step toward building real-world AI and Machine Learning applications.

