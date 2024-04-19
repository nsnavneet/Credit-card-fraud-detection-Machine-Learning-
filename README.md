# Credit Card Fraud Detection

## Overview
This project focuses on building a predictive model to identify fraudulent credit card transactions, aiming to minimize customer losses by detecting fraudulent activities accurately. Various machine learning techniques and oversampling methods are employed to address the class imbalance present in the dataset.

## Data
- **Source:** [Link to the dataset source]

- **Description:** The dataset contains anonymized credit card transactions made by European cardholders in September 2013, spanning two days. It comprises 284,807 transactions, with only 492 being fraudulent (0.172% class imbalance).

- **Features:**
  - V1, V2, ..., V28: Numerical features resulting from PCA transformation.
  - Time: Seconds elapsed since the first transaction (removed due to low significance).
  - Amount: Transaction amount.
  - Class: Target variable (1 for fraud, 0 otherwise).

## Data Preprocessing
- **Normalization:** PowerTransformer from scikit-learn is used to normalize the PCA-transformed features towards a Gaussian distribution, enhancing model performance.
- **Feature Selection:** Time feature is removed due to its observed uniformity across classes and minimal impact on fraud detection.

## Train-Test Split
The dataset is stratified into 70% training and 30% testing sets using `stratify=True` to preserve the class imbalance for accurate evaluation.

## Model Building
### Imbalanced Training:
- Models trained: Logistic Regression, KNN, SVM, Decision Trees, Random Forest.
- Hyperparameter tuning: Performed using stratified K-fold cross-validation and GridSearchCV.
- Evaluation metric: ROC-AUC score.

### Oversampling Techniques:
- **Random Oversampling:** Duplicates instances from the minority class (frauds) randomly until class balance is achieved.
- **SMOTE (Synthetic Minority Oversampling Technique):** Creates synthetic samples for the minority class based on existing data points.
- **ADASYN (Adaptive Synthetic Minority Oversampling Technique):** Focuses on oversampling instances from the minority class that are more difficult to classify.

## Model Selection
- The best performing model-oversampling technique combination is chosen based on ROC-AUC score, prioritizing high recall.
- Further fine-tuning of hyperparameters for optimal performance.

## Evaluation
- The chosen model is evaluated on the unseen testing set using ROC-AUC score, precision, and recall.
- Emphasis on achieving high recall to minimize missed fraudulent transactions.

## Results
- Final performance metrics (ROC-AUC, precision, recall) of the chosen model.
- Visualizations or insights gained during the process.

## Future Work
- Explore additional oversampling techniques or ensemble methods for potential performance improvements.
- Investigate feature engineering for better fraud detection.
- Experiment with online learning or real-time fraud detection systems.
