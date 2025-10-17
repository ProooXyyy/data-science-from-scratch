# Advanced Topics Cheatsheet (NLP & Time Series)

A quick reference for the core concepts in Natural Language Processing and Time Series Analysis.

---

## Part 1: Natural Language Processing (NLP)

NLP is used to help computers understand human language. The first step is always text pre-processing.

### 1. The NLP Pre-processing Pipeline

The goal is to turn raw text into clean, numerical data for a model.

1.  **Tokenization:** Split text into words (tokens).
2.  **Normalization:** Convert all text to lowercase.
3.  **Stop Word Removal:** Remove common, non-informative words.
4.  **Stemming / Lemmatization:** Reduce words to their root form.

### 2. Core `nltk` Operations

-   **Initial Setup & Downloads:**
    ```python
    import nltk
    nltk.download('punkt')
    nltk.download('stopwords')
    nltk.download('wordnet')
    ```
    *(Remember to restart the kernel after the first download.)*

-   **Tokenization:**
    ```python
    from nltk.tokenize import word_tokenize
    tokens = word_tokenize("Your sample text goes here.")
    ```

-   **Stop Word Removal:**
    ```python
    from nltk.corpus import stopwords
    stop_words = set(stopwords.words('english'))
    filtered = [word for word in tokens if word.lower() not in stop_words and word.isalpha()]
    ```

-   **Lemmatization (Preferred Method):**
    ```python
    from nltk.stem import WordNetLemmatizer
    lemmatizer = WordNetLemmatizer()
    lemmatized = [lemmatizer.lemmatize(word) for word in filtered]
    ```

---

## Part 2: Time Series Analysis

Time series analysis is used for data collected sequentially over time (e.g., stock prices, sales data).

### 1. Core Concepts

-   **Trend:** The long-term upward or downward direction of the data.
-   **Seasonality:** A repeating, predictable pattern at regular intervals (e.g., yearly, weekly).
-   **Residuals (Noise):** The random, unpredictable fluctuations left over.

### 2. Handling Time Series in Pandas

-   **Set a Datetime Index:** This is the most crucial step. It unlocks Pandas' time series functionality.
    ```python
    import pandas as pd
    df = pd.read_csv('your_data.csv')
    
    # Convert date column to datetime objects
    df['Date'] = pd.to_datetime(df['Date'])
    
    # Set the date column as the index
    df.set_index('Date', inplace=True)
    ```

### 3. Time Series Decomposition

This technique separates a time series into its trend, seasonal, and residual components.

-   **Using `statsmodels`:**
    ```python
    from statsmodels.tsa.seasonal import seasonal_decompose

    # Decompose the series (assuming a yearly cycle with monthly data, freq=12)
    result = seasonal_decompose(df['your_column'], model='additive')
    
    # Plot the components
    result.plot()
    ```