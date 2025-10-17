# SQL Basics Cheatsheet

A quick reference for the most common SQL queries for data analysis.

---

### 1. The Core `SELECT` Statement

-   **Select All Columns from a Table:**
    ```sql
    SELECT * FROM table_name;
    ```
-   **Select Specific Columns:**
    ```sql
    SELECT column1, column2 FROM table_name;
    ```
-   **Limit the Number of Results:**
    ```sql
    SELECT * FROM table_name LIMIT 100;
    ```

---

### 2. Filtering Data with `WHERE`

-   **Basic Condition:**
    ```sql
    SELECT * FROM customers WHERE country = 'USA';
    ```
-   **Multiple Conditions (`AND`, `OR`):**
    ```sql
    SELECT * FROM products WHERE price > 50 AND category = 'Electronics';
    ```
-   **Other Common Operators:**
    -   `=`, `!=` (or `<>`), `>`, `<`, `>=`, `<=`
    -   `IN ('value1', 'value2')`
    -   `BETWEEN value1 AND value2`
    -   `LIKE 'pattern%'` (e.g., `%` is a wildcard)

---

### 3. Aggregating Data with `GROUP BY`

-   **Count Rows in Groups:**
    ```sql
    SELECT country, COUNT(*)
    FROM customers
    GROUP BY country;
    ```
-   **Common Aggregate Functions:**
    -   `COUNT()`: Counts rows
    -   `SUM()`: Sums values
    -   `AVG()`: Averages values
    -   `MIN()`: Finds the minimum value
    -   `MAX()`: Finds the maximum value

---

### 4. Sorting Results with `ORDER BY`

-   **Sort in Ascending Order (default):**
    ```sql
    SELECT * FROM products
    ORDER BY price; -- or ORDER BY price ASC;
    ```
-   **Sort in Descending Order:**
    ```sql
    SELECT * FROM products
    ORDER BY price DESC;
    ```

---

### 5. Joining Tables

-   **Inner Join (returns only matching rows from both tables):**
    ```sql
    SELECT orders.order_id, customers.customer_name
    FROM orders
    INNER JOIN customers ON orders.customer_id = customers.customer_id;
    ```
-   **Left Join (returns all rows from the left table, and matching rows from the right):**
    ```sql
    SELECT customers.customer_name, orders.order_id
    FROM customers
    LEFT JOIN orders ON customers.customer_id = orders.customer_id;
    ```