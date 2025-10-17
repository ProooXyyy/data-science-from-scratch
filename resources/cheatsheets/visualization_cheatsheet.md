# Data Visualization Cheatsheet (Matplotlib & Seaborn)

A quick reference for creating common plots for data exploration and analysis.

---

### 1. Setup & Basic Plotting

-   **Import Libraries:**
    ```python
    import matplotlib.pyplot as plt
    import seaborn as sns
    ```
-   **Apply a Seaborn Style:**
    ```python
    sns.set_theme(style="whitegrid")
    ```
-   **Create a Basic Plot:**
    ```python
    plt.figure(figsize=(10, 6)) # Set the figure size
    plt.plot(x_data, y_data)
    plt.title('My Plot Title')
    plt.xlabel('X-Axis Label')
    plt.ylabel('Y-Axis Label')
    plt.show() # Display the plot
    ```

---

### 2. Common Plot Types

#### Matplotlib (for customization)

-   **Line Plot:** Shows trends over time.
    ```python
    plt.plot(df['date'], df['price'])
    ```
-   **Bar Chart:** Compares quantities across categories.
    ```python
    plt.bar(df['category'], df['count'])
    ```
-   **Scatter Plot:** Shows the relationship between two numerical variables.
    ```python
    plt.scatter(df['age'], df['salary'])
    ```
-   **Histogram:** Shows the distribution of a single numerical variable.
    ```python
    plt.hist(df['age'], bins=20)
    ```

#### Seaborn (for statistical plots with less code)

-   **Histogram / Distribution Plot:**
    ```python
    sns.histplot(data=df, x='total_bill', kde=True)
    ```
-   **Count Plot:** A bar chart showing counts of categories.
    ```python
    sns.countplot(data=df, x='day')
    ```
-   **Box Plot:** Shows distribution across categories (displays median, quartiles, outliers).
    ```python
    sns.boxplot(data=df, x='day', y='total_bill')
    ```
-   **Scatter Plot (with hue):** Adds a third categorical variable using color.
    ```python
    sns.scatterplot(data=df, x='total_bill', y='tip', hue='smoker')
    ```
-   **Heatmap:** Visualizes a matrix of data, often for correlations.
    ```python
    sns.heatmap(df.corr(), annot=True, cmap='coolwarm')
    ```