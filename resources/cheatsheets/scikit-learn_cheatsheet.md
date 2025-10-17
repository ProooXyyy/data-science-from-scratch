# Scikit-Learn Cheatsheet

A quick reference for the standard machine learning workflow using `sklearn`.

---

### 1. The Core Workflow

1.  **Split Data:** Separate features (X) and target (y), then split into training and testing sets.
2.  **Choose a Model:** Import and instantiate the model object.
3.  **Fit the Model:** Train the model on the training data (`X_train`, `y_train`).
4.  **Predict:** Make predictions on the unseen test data (`X_test`).
5.  **Evaluate:** Compare the model's predictions to the actual values (`y_test`).

---

### 2. Data Preparation

-   **Train-Test Split:**
    ```python
    from sklearn.model_selection import train_test_split
    X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
    ```
-   **Feature Scaling (Standardization):**
    ```python
    from sklearn.preprocessing import StandardScaler
    scaler = StandardScaler()
    X_train = scaler.fit_transform(X_train)
    X_test = scaler.transform(X_test)
    ```

---

### 3. Supervised Learning Models

#### Regression (Predicting a Number)

-   **Linear Regression:**
    ```python
    from sklearn.linear_model import LinearRegression
    model = LinearRegression()
    ```
-   **Evaluation Metrics:**
    ```python
    from sklearn.metrics import mean_absolute_error, mean_squared_error
    mae = mean_absolute_error(y_test, predictions)
    rmse = np.sqrt(mean_squared_error(y_test, predictions))
    ```

#### Classification (Predicting a Category)

-   **Logistic Regression:**
    ```python
    from sklearn.linear_model import LogisticRegression
    model = LogisticRegression()
    ```
-   **Random Forest Classifier:**
    ```python
    from sklearn.ensemble import RandomForestClassifier
    model = RandomForestClassifier(n_estimators=100)
    ```
-   **Evaluation Metrics:**
    ```python
    from sklearn.metrics import accuracy_score, classification_report, confusion_matrix
    accuracy = accuracy_score(y_test, predictions)
    print(classification_report(y_test, predictions))
    ```

---

### 4. The `fit`, `predict`, `transform` Pattern

-   **`.fit(X_train, y_train)`:** Trains the model or preprocessor on the training data. This is the "learning" step.
-   **`.predict(X_test)`:** Uses the trained model to make predictions.
-   **`.transform(X)`:** Applies a learned transformation from a preprocessor (like a scaler) to data.
-   **`.fit_transform(X_train)`:** A convenient shortcut that learns from and transforms the training data in one step. **Never use this on the test set.**