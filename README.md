# Comparing Logistic Regression and Decision Tree Classifiers

## Overview

This project demonstrates the implementation and comparison of two popular machine learning classification algorithms:

* Logistic Regression
* Decision Tree Classifier

The objective is to predict whether a student will pass or fail based on their study hours and previous exam scores. The project evaluates both models using common classification metrics and analyzes their strengths, weaknesses, and suitability for different types of datasets.

---

## Objectives

* Implement Logistic Regression for binary classification.
* Implement a Decision Tree Classifier for binary classification.
* Train and evaluate both models on the same dataset.
* Compare model performance using evaluation metrics.
* Visualize the Decision Tree structure.
* Understand the advantages and limitations of each algorithm.

---

## Technologies Used

* Python
* NumPy
* Pandas
* Scikit-learn
* Matplotlib

---

## Project Structure

```text id="vb6cbh"
Model-Comparison-Classification/
│
├── compare_models.py
├── README.md
└── requirements.txt
```

---

## Dataset

The dataset contains information about students' study habits and academic performance.

| Study Hours | Previous Exam Score | Pass |
| ----------- | ------------------- | ---- |
| 1           | 30                  | 0    |
| 2           | 40                  | 0    |
| 3           | 45                  | 0    |
| 4           | 50                  | 0    |
| 5           | 60                  | 0    |
| 6           | 65                  | 1    |
| 7           | 70                  | 1    |
| 8           | 75                  | 1    |
| 9           | 80                  | 1    |
| 10          | 85                  | 1    |

### Features

* **StudyHours** – Number of hours spent studying.
* **PrevExamScore** – Previous examination score.

### Target Variable

* **Pass**

  * 0 = Fail
  * 1 = Pass

---

## Model Workflow

### 1. Data Preparation

The dataset is loaded into a Pandas DataFrame and divided into:

* Features (X)
* Target Variable (y)

```python id="ajh7g5"
X = df[['StudyHours', 'PrevExamScore']]
y = df['Pass']
```

---

### 2. Train-Test Split

The dataset is divided into:

* 80% Training Data
* 20% Testing Data

using:

```python id="6s7g8d"
train_test_split()
```

This ensures that model performance is evaluated on unseen data.

---

## Model 1: Logistic Regression

### Description

Logistic Regression is a statistical classification algorithm that predicts the probability of a binary outcome using the sigmoid function.

### Training

```python id="0cbg9n"
logreg_model = LogisticRegression()
logreg_model.fit(X_train, y_train)
```

### Prediction

```python id="6ksn54"
y_pred_logreg = logreg_model.predict(X_test)
```

### Characteristics

* Simple and efficient
* Easy to interpret
* Performs well on linearly separable data
* Fast training and prediction

---

## Model 2: Decision Tree Classifier

### Description

A Decision Tree Classifier creates decision rules by recursively splitting the dataset into branches based on feature values.

### Training

```python id="w3sdff"
tree_model = DecisionTreeClassifier(random_state=42)
tree_model.fit(X_train, y_train)
```

### Prediction

```python id="2g1spm"
y_pred_tree = tree_model.predict(X_test)
```

### Characteristics

* Handles nonlinear relationships
* Highly interpretable
* Requires little data preprocessing
* Can overfit if not properly tuned

---

## Model Evaluation

Both models are evaluated using:

### Accuracy Score

Measures the percentage of correct predictions.

```python id="1jcb9t"
accuracy_score()
```

---

### Confusion Matrix

Displays:

* True Positives (TP)
* True Negatives (TN)
* False Positives (FP)
* False Negatives (FN)

```python id="yl2q0d"
confusion_matrix()
```

---

### Classification Report

Provides:

* Precision
* Recall
* F1-Score
* Support

```python id="8eh7lp"
classification_report()
```

---

## Sample Results

### Logistic Regression

```text id="mms1ef"
Accuracy: 0.90

Confusion Matrix:
[[1 0]
 [0 1]]
```

### Decision Tree

```text id="axv1hy"
Accuracy: 1.00

Confusion Matrix:
[[1 0]
 [0 1]]
```

*Note: Results may vary depending on train-test split and dataset size.*

---

## Decision Tree Visualization

One major advantage of Decision Trees is interpretability.

The model structure can be visualized using:

```python id="wk7d4i"
tree.plot_tree(
    tree_model,
    feature_names=['StudyHours', 'PrevExamScore'],
    class_names=['Fail', 'Pass'],
    filled=True
)
```

The visualization helps understand:

* Feature importance
* Decision rules
* Classification paths
* Leaf node predictions

---

## Model Comparison

| Feature                  | Logistic Regression | Decision Tree               |
| ------------------------ | ------------------- | --------------------------- |
| Problem Type             | Classification      | Classification & Regression |
| Interpretability         | High                | Very High                   |
| Handles Nonlinear Data   | No                  | Yes                         |
| Training Speed           | Fast                | Moderate                    |
| Overfitting Risk         | Low                 | High                        |
| Feature Scaling Required | Recommended         | Not Required                |
| Probability Output       | Yes                 | Yes                         |
| Visualization            | Limited             | Excellent                   |

---

## Advantages and Disadvantages

### Logistic Regression

#### Advantages

* Simple to implement
* Fast training
* Easy interpretation
* Works well on linearly separable data

#### Disadvantages

* Cannot capture complex nonlinear patterns
* Assumes linear relationships between features and target

---

### Decision Tree

#### Advantages

* Handles nonlinear relationships
* Easy to visualize and interpret
* Works with both numerical and categorical data
* Requires minimal preprocessing

#### Disadvantages

* Prone to overfitting
* Sensitive to small changes in data
* Can become complex with deeper trees

---

## Key Learning Outcomes

After completing this project, you will understand:

* Binary Classification Concepts
* Logistic Regression Fundamentals
* Decision Tree Fundamentals
* Model Training and Testing
* Classification Metrics
* Confusion Matrix Interpretation
* Model Comparison Techniques
* Choosing the Right Algorithm for a Problem

---

## Applications

### Logistic Regression

* Spam Detection
* Credit Approval
* Medical Diagnosis
* Customer Churn Prediction

### Decision Trees

* Fraud Detection
* Loan Risk Assessment
* Customer Segmentation
* Recommendation Systems
* Educational Performance Prediction

---

## Future Enhancements

* Use larger real-world datasets.
* Compare additional algorithms:

  * Random Forest
  * Support Vector Machines (SVM)
  * K-Nearest Neighbors (KNN)
  * Gradient Boosting
  * XGBoost
* Perform hyperparameter tuning.
* Implement cross-validation.
* Build a machine learning model comparison dashboard using Streamlit.

---

## Conclusion

This project compares Logistic Regression and Decision Tree Classifiers on the same classification problem. Logistic Regression provides a simple and efficient solution for linearly separable data, while Decision Trees offer greater flexibility and interpretability for more complex datasets. Understanding the strengths and limitations of both algorithms is essential when selecting the right model for a machine learning task.

---

## Author

**Tejaswi**
Salesforce Developer | AI/ML Enthusiast | Aspiring Data Scientist

---

## License

This project is licensed under the MIT License.
