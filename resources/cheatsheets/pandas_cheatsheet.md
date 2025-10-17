# Pandas Cheatsheet

A quick reference for the most common Pandas operations for data manipulation and analysis.

---

### 1. Importing & Exporting Data

-   **Import Pandas:**
    ```python
    import pandas as pd
    ```
-   **Read from CSV:**
    ```python
    df = pd.read_csv('your_file.csv')
    ```
-   **Write to CSV:**
    ```python
    df.to_csv('output_file.csv', index=False)
    ```

---

### 2. Inspecting a DataFrame

-   **View First 5 Rows:**
    ```python
    df.head()
    ```
-   **View Last 5 Rows:**
    ```python
    df.tail()
    ```
-   **Get DataFrame Info (Data Types, Non-null counts):**
    ```python
    df.info()
    ```
-   **Get Descriptive Statistics (for numerical columns):**
    ```python
    df.describe()
    ```
-   **Get DataFrame Shape (rows, columns):**
    ```python
    df.shape
    ```
-   **List Column Names:**
    ```python
    df.columns
    ```
-   **Count Unique Values in a Column:**
    ```python
    df['column_name'].value_counts()
    ```

---

### 3. Selecting Data (Slicing & Indexing)

-   **Select a Single Column (returns a Series):**
    ```python
    df['column_name']
    ```
-   **Select Multiple Columns (returns a DataFrame):**
    ```python
    df[['col1', 'col2']]
    ```
-   **Select Rows by Label (`.loc`):**
    ```python
    df.loc[row_label]
    ```
-   **Select Rows by Integer Index (`.iloc`):**
    ```python
    df.iloc[0] # First row
    df.iloc[:5] # First 5 rows
    ```
-   **Conditional Selection:**
    ```python
    df[df['age'] > 30]
    df[(df['age'] > 30) & (df['city'] == 'New York')]
    ```

---

### 4. Data Cleaning

-   **Check for Missing Values (returns count per column):**
    ```python
    df.isnull().sum()
    ```
-   **Drop Rows with Any Missing Values:**
    ```python
    df.dropna()
    ```
-   **Fill Missing Values with a Specific Value:**
    ```python
    df.fillna(value=0)
    ```
-   **Fill Missing Values with Column Mean:**
    ```python
    df['age'].fillna(value=df['age'].mean(), inplace=True)
    ```
-   **Drop Duplicate Rows:**
    ```python
    df.drop_duplicates()
    ```

---

### 5. Data Manipulation

-   **Add a New Column:**
    ```python
    df['new_column'] = df['col1'] * 2
    ```
-   **Apply a Function to a Column:**
    ```python
    def double(x):
        return x * 2
    df['col1'].apply(double)
    ```
-   **Drop Columns:**
    ```python
    df.drop('column_to_drop', axis=1, inplace=True)
    ```
-   **Sort Values:**
    ```python
    df.sort_values(by='column_name', ascending=False)
    ```

---

### 6. Grouping & Aggregating

-   **Group By a Column and Aggregate:**
    ```python
    # Get the average age for each city
    df.groupby('city')['age'].mean()
    
    # Get multiple aggregations
    df.groupby('city').agg({'age': 'mean', 'salary': 'max'})
    ```

---

### 7. Merging & Joining

-   **Merge two DataFrames on a common key:**
    ```python
    pd.merge(df1, df2, on='customer_id', how='inner')
    ```
    *`how` can be 'inner', 'outer', 'left', or 'right'.*