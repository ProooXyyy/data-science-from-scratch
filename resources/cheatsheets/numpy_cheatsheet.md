# NumPy Cheatsheet

A quick reference for NumPy, the fundamental package for numerical computing in Python.

---

### 1. Creating Arrays

-   **Import NumPy:**
    ```python
    import numpy as np
    ```
-   **From a Python List:**
    ```python
    arr = np.array([1, 2, 3, 4, 5])
    ```
-   **Array of a Range:**
    ```python
    range_arr = np.arange(0, 10) # -> [0, 1, ..., 9]
    ```
-   **Array of Zeros or Ones:**
    ```python
    zeros_arr = np.zeros((3, 4)) # 3x4 matrix of zeros
    ones_arr = np.ones(5)
    ```
-   **Array of Random Numbers:**
    ```python
    random_arr = np.random.rand(2, 3) # 2x3 matrix of random values (0 to 1)
    ```

---

### 2. Array Inspection

-   **Shape of an Array:**
    ```python
    arr.shape
    ```
-   **Data Type of Array Elements:**
    ```python
    arr.dtype
    ```

---

### 3. Indexing & Slicing

-   **Get a Single Element:**
    ```python
    arr[0] # First element
    ```
-   **Get a Slice:**
    ```python
    arr[1:4] # Elements from index 1 up to (not including) 4
    ```
-   **Indexing a 2D Array (Matrix):**
    ```python
    matrix = np.array([[1, 2], [3, 4]])
    matrix[0, 1] # Get element at row 0, column 1 -> 2
    ```

---

### 4. Mathematical Operations

NumPy operations are element-wise, making them very fast.

-   **Basic Arithmetic:**
    ```python
    arr + 5  # Add 5 to every element
    arr * 2  # Multiply every element by 2
    arr + arr # Element-wise addition of two arrays
    ```
-   **Universal Functions (ufuncs):**
    ```python
    np.sqrt(arr) # Square root of every element
    np.sin(arr) # Sine of every element
    np.log(arr) # Natural log of every element
    ```

---

### 5. Aggregations

-   **Calculate Mean, Sum, Min, Max:**
    ```python
    arr.mean()
    arr.sum()
    arr.min()
    arr.max()
    ```
-   **Standard Deviation & Variance:**
    ```python
    arr.std()
    arr.var()
    ```

---

### 6. Conditional Selection (Boolean Indexing)

-   **Create a Boolean Mask:**
    ```python
    bool_mask = arr > 3
    ```
-   **Use Mask to Select Elements:**
    ```python
    arr[bool_mask] # Returns only elements where the condition is True
    
    # Or in one line:
    arr[arr > 3]
    ```