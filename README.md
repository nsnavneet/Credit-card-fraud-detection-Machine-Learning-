# Credit-card-fraud-detection-Machine-Learning-
Build a predictive model to recognize fraudulent credit card transactions so that customers are not charged for items that they did not purchase.
Description:

This project investigates machine learning techniques to build a predictive model that identifies fraudulent credit card transactions. It focuses on addressing class imbalance and optimizing model performance for high recall to minimize customer losses.
Data:
Description: 
The dataset contains anonymized credit card transactions made by European cardholders in September 2013, spanning two days. It includes 284,807 transactions, with only 492 being fraudulent (0.172% class imbalance).
Features:
V1, V2, ..., V28: Numerical features resulting from PCA transformation.
Time: Seconds elapsed since the first transaction (removed due to low significance).
Amount: Transaction amount.
Class: Target variable (1 for fraud, 0 otherwise).
Source: [Link to the dataset source] (if publicly available)
Data Preprocessing:

Normalization: PowerTransformer from scikit-learn is used to normalize the PCA-transformed features towards a Gaussian distribution, improving model performance.
Feature Selection: Time feature is removed due to its observed uniformity across classes and minimal impact on fraud detection.
Train-Test Split:

The dataset is stratified into 70% training and 30% testing sets using stratify=True to preserve the class imbalance for accurate evaluation.
Model Building:

Imbalanced Training:
Models (Logistic Regression, KNN, SVM, Decision Trees, Random Forest) are trained on the original imbalanced dataset.
Hyperparameter tuning is performed using stratified K-fold cross-validation and GridSearchCV to find the best configuration for each model.
Model performance is evaluated using ROC-AUC score.
Oversampling Techniques:
To address class imbalance and potentially improve fraud detection accuracy, various oversampling techniques are employed:
Random Oversampling: Duplicates instances from the minority class (frauds) randomly until class balance is achieved.
SMOTE (Synthetic Minority Oversampling Technique): Creates synthetic samples for the minority class based on existing data points.
ADASYN (Adaptive Synthetic Minority Oversampling Technique): Focuses on oversampling instances from the minority class that are more difficult to classify, potentially leading to better performance.
Models are trained on the oversampled datasets using the same approach as with the imbalanced dataset.
Model Selection:
The best performing model-oversampling technique combination is chosen based on ROC-AUC score, prioritizing high recall to minimize missed fraud cases. Hyperparameters are fine-tuned further for optimal performance.
Evaluation:

The chosen model is evaluated on the unseen testing set using ROC-AUC score, precision, and recall.
The focus is on achieving high recall to ensure minimal fraudulent transactions are missed, even if it means some non-fraudulent cases might be flagged (adjustable with a decision threshold).
Results:

This section will include the final performance metrics (ROC-AUC, precision, recall) of the chosen model, along with any visualizations or insights gained during the process.
Future Work:

Explore additional oversampling techniques or ensemble methods for potential performance improvements.
Investigate feature engineering to create new features for better fraud detection.
Experiment with online learning or real-time fraud detection systems that adapt to evolving fraud patterns.
