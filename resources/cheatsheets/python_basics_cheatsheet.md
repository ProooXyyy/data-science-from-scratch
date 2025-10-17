# Python Basics Cheatsheet

A quick reference for the fundamental Python syntax and data structures used in data science.

---

### 1. Data Types

-   **Integer:** `x = 10`
-   **Float:** `y = 3.14`
-   **String:** `s = "Hello"`
-   **Boolean:** `is_true = True`

---

### 2. Data Structures

-   **List:** An ordered, changeable collection of items.
    ```python
    my_list = [10, "apple", 20.5]
    my_list[0] # Access first element -> 10
    my_list.append("new") # Add item to the end
    ```

-   **Dictionary:** An unordered collection of key-value pairs.
    ```python
    my_dict = {"name": "Alice", "age": 30}
    my_dict["name"] # Access value by key -> "Alice"
    my_dict["city"] = "New York" # Add a new key-value pair
    ```

---

### 3. Control Flow

-   **`if`/`elif`/`else` Statements:** Used for conditional logic.
    ```python
    if age < 18:
        print("Minor")
    elif age >= 18 and age < 65:
        print("Adult")
    else:
        print("Senior")
    ```

-   **`for` Loop:** Used for iterating over a sequence (like a list).
    ```python
    numbers = [1, 2, 3, 4]
    for num in numbers:
        print(num * 2)
    ```

---

### 4. Functions

-   **Defining a Function:** A reusable block of code.
    ```python
    def calculate_sum(a, b):
        """This function returns the sum of two numbers."""
        return a + b
    ```

-   **Calling a Function:**
    ```python
    result = calculate_sum(5, 10) # result is 15
    ```

---

### 5. String Methods

-   **Lowercase:** `my_string.lower()`
-   **Uppercase:** `my_string.upper()`
-   **Split by a Delimiter:** `my_string.split(',')`
-   **Formatted Strings (f-strings):**
    ```python
    name = "Bob"
    age = 40
    print(f"My name is {name} and I am {age} years old.")
    ```