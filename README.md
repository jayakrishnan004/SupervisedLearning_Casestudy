# Customer Churn Prediction

## Project Overview
This project focuses on predicting customer churn in the telecommunications industry using machine learning techniques. The objective is to identify customers who are likely to discontinue their services and help businesses develop effective customer retention strategies.

## Dataset
The dataset contains customer information, service subscriptions, contract details, payment methods and billing information.

**Key features include:**
- Customer demographics
- Tenure and contract details
- Internet and phone services
- Payment methods
- Monthly and total charges

**Target Variable:** `Churn`
- `Yes` – Customer churned.
- `No` – Customer retained.

## Project Workflow

### 1. Exploratory Data Analysis (EDA)
- Analyzed numerical and categorical features.
- Examined missing values and duplicates.
- Studied relationships between customer attributes and churn.
- Identified potential outliers using the IQR method.

### 2. Data Preprocessing
- Handled missing values using appropriate imputation strategies.
- Applied One-Hot Encoding to categorical features.
- Scaled numerical features using StandardScaler.
- Examined and retained genuine outliers.

### 3. Feature Engineering
Created additional features:
- `CustomerLifetimeValue`: Estimated accumulated customer spending using Tenure × MonthlyCharges.
- `Tenure_Contract`: Interaction feature combining customer tenure and contract type.

Used Random Forest feature importance to identify relevant features.

### 4. Model Development
Developed and evaluated three classification algorithms:
- Logistic Regression
- Decision Tree Classifier
- Random Forest Classifier

Evaluation metrics:
- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC
- Confusion Matrix

### 5. Hyperparameter Tuning
Applied GridSearchCV with 5-fold cross-validation to optimize Logistic Regression.

**Best Parameters:**
- C: 0.1
- Class Weight: balanced
- Solver: liblinear

## Model Performance

The tuned Logistic Regression model was selected based on validation performance and evaluated on the separate testing dataset.

| Evaluation Metric | Final Test Score |
|---|---:|
| Accuracy | 72.25% |
| Precision (Churn) | 48% |
| Recall (Churn) | 77% |
| F1-score (Churn) | 0.59 |
| ROC-AUC | 0.839 |

## Technologies Used
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Repository Structure

```text
Customer-Churn-Prediction/
│
├── Customer_Churn_Prediction.ipynb
├── train.csv
├── test.csv
└── README.md
```

*Dataset filenames and notebook filename may be adjusted to match the actual repository.*

## Conclusion

The tuned Logistic Regression model achieved a ROC-AUC score of 0.839 on the testing dataset and identified 77% of actual churners.

The results demonstrate how machine learning can support customer churn analysis and help telecommunications businesses identify customers who may require targeted retention strategies.
