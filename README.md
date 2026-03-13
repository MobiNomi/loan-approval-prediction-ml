Loan Approval Prediction using Machine Learning
Project Overview

This project builds a machine learning system to predict whether a loan application should be approved or rejected based on applicant information such as income, credit history, education, and property area.

Loan approval prediction is an important problem in banking and financial institutions. Machine learning can help automate decision-making by identifying patterns in historical loan data.

In this project, several machine learning models were developed and evaluated to identify the most effective model for predicting loan approval.

Dataset Description

The dataset contains information about loan applicants and their financial background.

Key features include:

Feature	Description
Gender	Applicant gender
Married	Marital status
Dependents	Number of dependents
Education	Graduate or not
Self_Employed	Self-employed status
ApplicantIncome	Income of the applicant
CoapplicantIncome	Income of the co-applicant
LoanAmount	Loan amount requested
LoanTerm	Duration of the loan
Credit_History	Credit repayment history
Property_Area	Location of property
Loan_Status	Target variable (Approved / Rejected)

Target Variable:

Loan_Status
1 = Loan Approved
0 = Loan Rejected
Project Workflow

The project follows a typical machine learning pipeline used in real-world ML projects.

1. Exploratory Data Analysis (EDA)

EDA was performed to understand the dataset and identify potential issues.

Key tasks included:

Understanding data types

Identifying missing values

Analyzing feature distributions

Detecting skewness in income and loan amount

Checking class imbalance

2. Data Preprocessing

Several preprocessing steps were applied to prepare the dataset for machine learning models.

Handling Missing Values

Missing values were handled using:

Median imputation for numerical features

Most frequent value imputation for categorical features

Encoding Categorical Variables

Categorical variables such as:

Gender
Married
Education
Property_Area

were encoded using One-Hot Encoding.

3. Feature Engineering

New features were created to improve model performance.

Total Income Feature

A new feature was created:

TotalIncome = ApplicantIncome + CoapplicantIncome

This provides a better representation of household income.

Log Transformation

Some numerical features were positively skewed. Log transformation was applied to reduce skewness:

ApplicantIncome_log
CoapplicantIncome_log
LoanAmount_log
TotalIncome_log

This transformation helps models better capture relationships between variables.

Machine Learning Models Used

Three machine learning models were implemented and compared.

1. Logistic Regression (Baseline Model)

Logistic Regression was used as the baseline classification model.

Advantages:

Simple and interpretable

Fast training

Works well for linearly separable data

Pipeline included:

Missing value imputation

One-hot encoding

Feature scaling

Logistic regression training

Evaluation metrics included:

Accuracy

Precision

Recall

F1-score

ROC-AUC

2. Decision Tree Classifier

A Decision Tree model was implemented to capture nonlinear relationships in the data.

Key hyperparameters used:

criterion = entropy
max_depth
min_samples_split
min_samples_leaf

These parameters control tree complexity and help prevent overfitting.

Advantages:

Easy to interpret

Captures nonlinear relationships

Works well with mixed feature types

3. Random Forest Classifier

Random Forest was implemented as an ensemble learning method that combines multiple decision trees.

Random Forest improves performance by:

Training many trees on bootstrapped datasets

Introducing randomness in feature selection

Aggregating predictions using majority voting

Key parameters used:

n_estimators
max_depth
min_samples_split
min_samples_leaf
max_features
class_weight

Random Forest generally provides better generalization than a single decision tree.

Model Evaluation

Models were evaluated using several performance metrics:

Accuracy

Measures the overall correctness of predictions.

Precision

Measures how many predicted approvals/rejections were correct.

Recall

Measures how many actual cases the model successfully identified.

F1 Score

The harmonic mean of precision and recall.

ROC-AUC

Measures the model's ability to distinguish between approved and rejected loans.

Cross Validation

Cross-validation was used to obtain a reliable estimate of model performance.

The dataset was split into multiple folds, and the model was trained and validated across different data partitions.

Stratified K-Fold cross validation was used to maintain the class distribution in each fold.

Model Comparison
Model	Accuracy	ROC-AUC	Strength
Logistic Regression	High	Strong	Good baseline
Decision Tree	Moderate	Moderate	Captures nonlinear patterns
Random Forest	Best overall	High	Stable and robust

Random Forest provided the most balanced performance across all evaluation metrics.

Key Insights

Important factors influencing loan approval include:

Credit history

Total income

Loan amount

Applicant financial stability

Random Forest feature importance can help identify the most influential variables.

Technologies Used

Python

Libraries used:

pandas
numpy
scikit-learn
matplotlib
seaborn
Project Structure

Example structure:

loan-approval-prediction-ml

│
├── data
│   └── loan_dataset.csv
│
├── notebooks
│   └── loan_prediction_analysis.ipynb
│
├── models
│   └── trained_models
│
├── README.md
└── requirements.txt
Future Improvements

Possible improvements to the project include:

Hyperparameter tuning using GridSearchCV

Advanced models such as XGBoost or LightGBM

More feature engineering (e.g., loan-to-income ratio)

Model explainability using SHAP values

Conclusion

This project demonstrates a complete machine learning workflow for loan approval prediction, including data preprocessing, feature engineering, model training, evaluation, and comparison.

The Random Forest model achieved the best balance between accuracy and generalization, making it a strong candidate for loan approval prediction systems.

Author

Machine Learning Project by Mubashir Hussain.
