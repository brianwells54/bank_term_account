
# [Model Comparison on Bank Marketing Dataset](bank_term_offer.ipynb)
## Overview
This project evaluates and compares the performance of four machine learning models (Logistic Regression, K-Nearest Neighbors, Decision Tree, and Support Vector Machine) using the default settings. The dataset comes from a Portuguese banking institution and contains results of various marketing campaigns. The goal is to predict whether a client will subscribe to a term deposit.

---

## Data Preparation
- **Dataset**: `bank-additional-full.csv`
- **Target Variable**: `y_yes` (binary: 1 for "Yes", 0 for "No")
- **Features**:
  - Categorical features such as `job`, `marital`, `education`, etc., were one-hot encoded.
  - Numerical features were used as-is.
- **Preprocessing**:
  - Rows with missing values in critical columns (`job`, `marital`, `education`, etc.) were removed.
  - The `duration` column was dropped as it leaks information about the target.

---

## Methodology
1. **Model Training and Evaluation**:
   - Default configurations were used for all models.
   - Models were trained on 70% of the data and evaluated on 30%.
   - Fit time, training accuracy, and test accuracy were measured for each model.
   - Confusion matrices were generated to visualize the performance for each model.

2. **Performance Metrics**:
   - **Train Time (Fit Time)**: Time taken to train each model.
   - **Train Accuracy**: Percentage of correct predictions on training data.
   - **Test Accuracy**: Percentage of correct predictions on test data.

---

## Results

| Model                | Train Time (s) | Train Accuracy (%) | Test Accuracy (%) |
|----------------------|----------------|---------------------|-------------------|
| Logistic Regression  | 0.43           | 88.76              | 88.75             |
| K-Nearest Neighbors  | 0.02           | 90.11              | 86.42             |
| Decision Tree        | 0.05           | 100.00             | 85.67             |
| Support Vector Machine | 9.21          | 89.72              | 88.36             |

- **Logistic Regression**:
  - Performed well overall with a balance between training and testing accuracy.
  - Convergence warnings were suppressed to maintain default settings.

- **K-Nearest Neighbors (KNN)**:
  - Performance was dependent on the number of neighbors, which defaults to 5. It showed strong training accuracy but slightly lower test accuracy due to overfitting.

- **Decision Tree**:
  - Achieved perfect training accuracy, but test accuracy was slightly lower, indicating overfitting.

- **Support Vector Machine (SVM)**:
  - Delivered competitive accuracy but had a higher training time compared to other models.

---

## Confusion Matrix Insights
Confusion matrices revealed:
- High performance on the majority class (`No`) across all models.
- Challenges in identifying the minority class (`Yes`), with Logistic Regression showing moderate performance in classifying positives.

---

## Recommendations
   
1. **Feature Engineering**:
   - Explore additional features or interactions that could improve model performance.

2. **Model Optimization**:
   - Fine-tune hyperparameters (e.g., neighbors in KNN, depth in Decision Tree, `C` and `gamma` in SVM) for improved performance.

3. **Deployment**:
   - Logistic Regression is a strong candidate for deployment due to its simplicity, interpretability, and competitive performance.

---
