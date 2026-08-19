# NumPy in Python

A concise reference guide to NumPy — the core library for numerical computing in Python.

---

## 1. Introduction

**NumPy** (Numerical Python) is an open-source Python library used for working with large, multi-dimensional arrays and matrices, along with a collection of high-level mathematical functions to operate on them.

**Why it's used:**
- Provides fast, memory-efficient array operations (much faster than native Python lists).
- Forms the foundation for the entire Python data science/ML stack.
- Supports vectorized operations, eliminating the need for explicit loops.

**Role in the Data Science/ML ecosystem:**
NumPy arrays are the backbone of libraries like **Pandas**, **Scikit-learn**, **TensorFlow**, and **PyTorch**. Almost every numerical computation in Python — from data cleaning to deep learning — relies on NumPy under the hood.

---

## 2. Installation

Install via pip:
```bash
pip install numpy
```

Or via conda:
```bash
conda install numpy
```

Import it in your script:
```python
import numpy as np
```

---

## 3. Core Concept: `ndarray`

The **`ndarray`** (N-dimensional array) is NumPy's central data structure — a grid of values, all of the same type, indexed by a tuple of non-negative integers.

**ndarray vs Python list:**

| Feature | Python List | NumPy ndarray |
|---|---|---|
| Data type | Mixed types allowed | Single, fixed data type |
| Speed | Slower (loop-based) | Faster (vectorized, C-backed) |
| Memory | Higher overhead | Compact, contiguous memory |
| Operations | No built-in math ops | Element-wise math built-in |

```python
arr = np.array([1, 2, 3, 4])
print(type(arr))  # <class 'numpy.ndarray'>
```

---

## 4. Data Types (dtypes)

NumPy arrays store elements of a single data type (`dtype`), which makes computations efficient.

Common dtypes:
- `int32`, `int64` – integers
- `float32`, `float64` – decimal numbers
- `bool` – True/False
- `complex64`, `complex128` – complex numbers
- `str_` – strings

**Checking and setting dtype:**
```python
arr = np.array([1, 2, 3])
print(arr.dtype)          # int64

arr_float = np.array([1, 2, 3], dtype=np.float32)
print(arr_float.dtype)    # float32
```

---

## 5. Array Creation

```python
np.array([1, 2, 3])          # From a list
np.zeros((2, 3))             # Array of zeros, shape (2,3)
np.ones((3, 3))              # Array of ones
np.arange(0, 10, 2)          # [0 2 4 6 8]
np.linspace(0, 1, 5)         # 5 evenly spaced values between 0 and 1
np.eye(3)                    # 3x3 Identity matrix
np.random.rand(2, 2)         # Random values (uniform distribution)
```

---

## 6. Array Attributes

```python
arr = np.array([[1, 2, 3], [4, 5, 6]])

arr.shape     # (2, 3) -> dimensions
arr.ndim      # 2 -> number of dimensions
arr.size      # 6 -> total number of elements
arr.dtype     # data type of elements
arr.itemsize  # size (in bytes) of each element
```

---

## 7. Indexing & Slicing

```python
arr = np.array([10, 20, 30, 40, 50])

arr[1]          # 20 -> basic indexing
arr[1:4]        # [20 30 40] -> slicing
arr[arr > 25]   # [30 40 50] -> boolean indexing
arr[[0, 2, 4]]  # [10 30 50] -> fancy indexing

# 2D indexing
arr2d = np.array([[1, 2], [3, 4]])
arr2d[0, 1]     # 2 -> row 0, column 1
```

---

## 8. Array Operations

```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

a + b        # Element-wise addition [5 7 9]
a * b        # Element-wise multiplication [4 10 18]
a * 2        # Broadcasting -> [2 4 6]

a.sum()      # 6
a.mean()     # 2.0
a.max()      # 3
a.min()      # 1
a.std()      # Standard deviation

a > 2        # [False False True] -> comparison
```

**Broadcasting** allows NumPy to perform operations on arrays of different shapes without explicit loops.

---

## 9. Reshaping & Manipulation

```python
arr = np.arange(6)

arr.reshape(2, 3)     # Reshape to 2 rows, 3 columns
arr.flatten()         # Convert to 1D (returns a copy)
arr.ravel()           # Convert to 1D (returns a view when possible)
arr.transpose()       # Transpose dimensions

np.concatenate([a, b])        # Join arrays
np.stack([a, b])              # Stack arrays along a new axis
np.split(arr, 3)              # Split array into 3 parts
```

---

## 10. Linear Algebra

```python
A = np.array([[1, 2], [3, 4]])
B = np.array([[5, 6], [7, 8]])

np.dot(A, B)          # Matrix multiplication
A @ B                 # Matrix multiplication (shorthand)

np.linalg.inv(A)      # Inverse of matrix
np.linalg.det(A)      # Determinant
np.linalg.eig(A)      # Eigenvalues and eigenvectors
```

---

## 11. Random Module

```python
np.random.rand(3)          # 3 random floats [0, 1)
np.random.randint(1, 10, 5)# 5 random integers between 1-10
np.random.randn(3)         # Samples from standard normal distribution
np.random.seed(42)         # Set seed for reproducibility
```

---

## 12. Performance Notes

NumPy is significantly faster than plain Python lists because:
- **Vectorization** – Operations run on entire arrays at once instead of looping element-by-element.
- **C Backend** – NumPy's core is implemented in C, avoiding Python's interpreter overhead.
- **Contiguous Memory** – Arrays are stored in fixed-type, contiguous memory blocks, enabling efficient CPU cache usage.

```python
# NumPy vectorized (fast)
result = arr * 2

# Pure Python loop (slow)
result = [x * 2 for x in list_data]
```

---

## 13. Example Code Snippets

```python
import numpy as np

# Create and inspect an array
data = np.array([[1, 2, 3], [4, 5, 6]])
print("Shape:", data.shape)
print("Mean:", data.mean())

# Reshape and transform
reshaped = data.reshape(3, 2)
print(reshaped)

# Filter with boolean indexing
filtered = data[data > 3]
print(filtered)
```

---

## 14. References

- Official Documentation: [https://numpy.org/doc/](https://numpy.org/doc/)
- NumPy GitHub: [https://github.com/numpy/numpy](https://github.com/numpy/numpy)
- NumPy Quickstart Guide: [https://numpy.org/doc/stable/user/quickstart.html](https://numpy.org/doc/stable/user/quickstart.html)
