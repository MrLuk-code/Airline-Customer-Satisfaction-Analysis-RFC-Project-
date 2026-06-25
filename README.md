# Airline-Customer-Satisfaction-Analysis-RFC-Project-

# Random Forest Classification – Airline Customer Satisfaction Analysis

## Project Overview

This project analyzes airline passenger survey data to predict customer satisfaction using a **Random Forest Classifier**. The objective is to build an optimized ensemble learning model, compare its performance with a baseline Decision Tree model, and identify the most influential factors affecting passenger satisfaction.

The project demonstrates a complete machine learning workflow, including data preprocessing, three-way data splitting, hyperparameter tuning, model evaluation, and interpretation of feature importance.

---

## Dataset

**Dataset:** `Invistico_Airline.csv`

The dataset contains passenger demographic information, travel details, service ratings, and an overall satisfaction label.

### Target Variable

- `satisfaction`
  - Satisfied
  - Dissatisfied

---

## Project Objectives

- Implement a three-way data split strategy to prevent data leakage.
- Tune Random Forest hyperparameters using `GridSearchCV`.
- Utilize `PredefinedSplit` to ensure the validation set is used exclusively for model selection.
- Evaluate the optimized model on unseen test data.
- Compare Random Forest performance against a Decision Tree classifier.
- Identify the most important drivers of airline customer satisfaction.
- Present findings in a management-friendly format.

---

## Data Splitting Strategy

The dataset was divided into three subsets:

| Dataset | Percentage |
|---------|------------|
| Training Set | 60% |
| Validation Set | 20% |
| Test Set | 20% |

The validation set was incorporated into a `PredefinedSplit` object and used exclusively during hyperparameter optimization.

The test set remained untouched until the final evaluation stage.

---

## Hyperparameter Optimization

A grid search was conducted over the following parameter combinations:

```python
param_grid = {
    'max_depth': [10, 15, None],
    'n_estimators': [100, 200],
    'min_samples_leaf': [1, 2, 4]
}
```

### Tuning Method

- **Algorithm:** GridSearchCV
- **Validation Strategy:** PredefinedSplit
- **Scoring Metric:** `f1_weighted`

---

## Model Evaluation Metrics

The optimized Random Forest model was evaluated on the held-out test set using:

- Accuracy
- Precision
- Recall
- F1-score

---

## Decision Tree vs Random Forest

| Metric | Decision Tree | Random Forest |
|--------|---------------|---------------|
| Accuracy | XX.XX | XX.XX |
| Precision | XX.XX | XX.XX |
| Recall | XX.XX | XX.XX |
| F1-score | XX.XX | XX.XX |

### Key Observations

The Random Forest model demonstrated improved generalization performance compared to the Decision Tree.

Benefits observed include:

- Reduced overfitting
- Improved stability
- Better predictive performance on unseen data
- More reliable customer satisfaction predictions

---

## Feature Importance Analysis

Feature importance scores were extracted from the optimized Random Forest model.

Examples of influential variables may include:

- Inflight Entertainment
- Seat Comfort
- Online Boarding
- Leg Room Service
- Ease of Online Booking
- Cleanliness

These variables provide actionable insights into areas where airline management can improve passenger experiences.

---

## Business Recommendations

Based on the model findings, airline management should prioritize investments in service categories with the greatest impact on customer satisfaction.

Suggested focus areas include:

- Enhancing inflight entertainment systems
- Improving seat comfort
- Streamlining online boarding processes
- Increasing cabin cleanliness standards
- Optimizing digital booking experiences

Targeted improvements in these areas can increase customer loyalty, strengthen brand reputation, and improve overall passenger retention.

---

## Repository Structure

```text
├── random_forest_airline.ipynb
├── README.md
├── requirements.txt
└── Invistico_Airline.csv
```

---

## Technologies Used

- Python 3.x
- Pandas
- NumPy
- Scikit-learn
- Jupyter Notebook

---

## Conclusion

This project demonstrates how ensemble learning techniques such as Random Forest can outperform single Decision Trees by reducing variance and improving generalization.

The combination of proper data splitting, rigorous hyperparameter tuning, and feature importance analysis enables data-driven decision-making and provides valuable insights for airline leadership.
