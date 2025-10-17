# Git & GitHub Cheatsheet

A quick reference for version control with Git and collaborating on GitHub.

---

### 1. The Core Concept

-   **Git:** A version control system on your local machine that tracks changes to your files. Think of it as "save points" for your code.
-   **GitHub:** A web-based platform that hosts your Git repositories. It's used for storing, sharing, and collaborating on projects.

---

### 2. Initial Setup

-   **Configure Your Info (do this once):**
    ```bash
    git config --global user.name "Your Name"
    git config --global user.email "youremail@example.com"
    ```

---

### 3. Starting a Project

-   **Initialize a New Git Repository in an Existing Folder:**
    ```bash
    git init
    ```
-   **Clone an Existing Repository from GitHub:**
    ```bash
    git clone [https://github.com/user/repo.git](https://github.com/user/repo.git)
    ```

---

### 4. The Basic Workflow (Local)

This is the most common cycle you'll use.

1.  **Check Status:** See which files have been modified.
    ```bash
    git status
    ```
2.  **Stage Changes:** Add your modified files to the "staging area" to be included in the next "save".
    ```bash
    # Add a specific file
    git add filename.py

    # Add all modified files
    git add .
    ```
3.  **Commit Changes:** Save the staged files to your project's history with a descriptive message.
    ```bash
    git commit -m "A brief, clear message about what you changed"
    ```

---

### 5. Working with GitHub (Remote)

-   **Push Your Commits to GitHub:** Upload your local commits to the remote repository.
    ```bash
    git push origin main
    ```
    *(Note: Your main branch might be called `master`)*

-   **Pull Changes from GitHub:** Download the latest changes from the remote repository to your local machine.
    ```bash
    git pull origin main
    ```

---
### ## Data Science Project Workflow Cheatsheet 🚀

This final cheatsheet summarizes the entire end-to-end process you've learned. Create a file named **`project_workflow_cheatsheet.md`** inside `resources/cheatsheets/`.

```markdown
# The Data Science Project Workflow Cheatsheet

A step-by-step guide to tackling an end-to-end data science project.

---

### Phase 1: Problem Definition & Data Collection

-   [ ] **Understand the Business Goal:** What problem are you solving? What defines success? (e.g., "Predict customer churn to reduce it by 10%")
-   [ ] **Define the ML Problem:** Is it regression, classification, clustering, etc.?
-   [ ] **Gather Data:** Collect data from databases, APIs, or CSV files.

---

### Phase 2: Exploratory Data Analysis (EDA) & Cleaning

-   [ ] **Inspect the Data:**
    -   `df.head()`, `df.info()`, `df.describe()`
-   [ ] **Clean the Data:**
    -   Handle missing values (`.isnull().sum()`, `.dropna()`, `.fillna()`).
    -   Correct data types (e.g., `pd.to_numeric`).
    -   Remove duplicates (`.drop_duplicates()`).
-   [ ] **Visualize the Data:**
    -   Understand distributions (`sns.histplot`).
    -   Explore relationships between variables (`sns.scatterplot`, `sns.heatmap`).
    -   Compare categories (`sns.countplot`, `sns.boxplot`).

---

### Phase 3: Feature Engineering & Pre-processing

-   [ ] **Select Features (X) and Target (y).**
-   [ ] **Handle Categorical Features:**
    -   Use One-Hot Encoding (`pd.get_dummies()`) for nominal data.
-   [ ] **Feature Scaling:**
    -   Standardize numerical features for distance-based algorithms like Logistic Regression (`StandardScaler`).

---

### Phase 4: Model Building

-   [ ] **Train-Test Split:**
    -   `from sklearn.model_selection import train_test_split`
-   [ ] **Choose and Train Models:**
    -   Start with a simple baseline (e.g., `LogisticRegression`).
    -   Try more complex models (e.g., `RandomForestClassifier`).
-   [ ] **Fit Models to Training Data:**
    -   `model.fit(X_train, y_train)`

---

### Phase 5: Model Evaluation & Interpretation

-   [ ] **Make Predictions on the Test Set:**
    -   `predictions = model.predict(X_test)`
-   [ ] **Choose the Right Metrics:**
    -   **Regression:** MAE, MSE, RMSE.
    -   **Classification:** Accuracy, Precision, Recall, Confusion Matrix, ROC/AUC.
-   [ ] **Compare Models:** Which model performs best according to your chosen metric and business goal?
-   [ ] **Draw Conclusions:** Summarize your findings and provide actionable insights.