# Customer Churn Analysis

An end-to-end machine learning project for analyzing customer churn using exploratory data analysis, feature investigation, and multiple classification models.

The main focus of this project is not only to build predictive models, but also to investigate unusually high model performance and identify potentially suspicious features.

---

##  Project Overview

Customer churn is an important business problem where companies try to identify customers who are likely to stop using their services.

In this project, I analyze customer data to:

- Explore patterns associated with customer churn
- Perform data quality assessment
- Investigate relationships between features and the target
- Train and compare multiple machine learning models
- Investigate unusually high model performance
- Evaluate models after removing suspicious features

---

##  Objectives

- Perform Exploratory Data Analysis (EDA)
- Understand the distribution of customer churn
- Examine relationships between features and churn
- Identify potential data quality issues
- Investigate suspiciously predictive features
- Train multiple classification models
- Compare models using several evaluation metrics
- Analyze model performance after removing suspicious features

---

##  Dataset

The project uses the following dataset:

`customer_churn_dataset-testing-master.csv`

The dataset contains **440,833 observations and 12 columns**.

### Features

| Feature | Description |
|---|---|
| `CustomerID` | Unique customer identifier |
| `Age` | Customer age |
| `Gender` | Customer gender |
| `Tenure` | Length of customer relationship |
| `Usage Frequency` | Customer usage frequency |
| `Support Calls` | Number of support calls |
| `Payment Delay` | Payment delay information |
| `Subscription Type` | Customer subscription type |
| `Contract Length` | Customer contract length |
| `Total Spend` | Total customer spending |
| `Last Interaction` | Days since the last interaction |
| `Churn` | Target variable indicating customer churn |

---

##  Exploratory Data Analysis

The analysis includes:

- Dataset structure and data types
- Missing-value investigation
- Duplicate-value investigation
- Target variable distribution
- Numerical feature distributions
- Categorical feature analysis
- Correlation analysis
- Feature relationships with the target variable

The analysis also identified an empty row and several features stored in numeric formats that were not necessarily appropriate for modeling.

---

## ⚠️ Suspicious Feature Investigation

During the initial modeling stage, several models achieved unusually high performance, with some metrics approaching **1.00**.

Instead of treating these results as automatically successful, the project investigates why the models were performing so well.

`Support Calls` and `Contract Length` showed unusually strong relationships with the target variable and were therefore treated as suspicious features.

The models were evaluated again after removing these features to determine whether the extremely high performance would remain.

---

##  Machine Learning Models

The following classification algorithms were evaluated:

- Logistic Regression
- Decision Tree
- Random Forest
- XGBoost
- CatBoost
- LightGBM

Numerical features were standardized, while categorical features were encoded before model training.

---

## 📈 Model Evaluation

The models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC

### Results After Removing Suspicious Features

| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| LightGBM | 0.9204 | 0.9998 | 0.8598 | 0.9245 | **0.9429** |
| CatBoost | 0.9205 | 0.9995 | 0.8602 | 0.9246 | 0.9428 |
| XGBoost | 0.9207 | 1.0000 | 0.8601 | 0.9248 | 0.9425 |
| Random Forest | **0.9209** | 0.9990 | 0.8613 | **0.9251** | 0.9377 |
| Decision Tree | 0.8607 | 0.8688 | **0.8886** | 0.8786 | 0.8564 |
| Logistic Regression | 0.7518 | 0.7796 | 0.7839 | 0.7818 | 0.8383 |

---

##  Key Findings

### 1. Extremely high model performance should be investigated

The initial models produced nearly perfect results.

Rather than assuming that the models were exceptionally good, the project investigated the underlying data and feature relationships.

### 2. Suspicious features had a major impact

Removing `Support Calls` and `Contract Length` substantially reduced model performance.

The ROC-AUC of the strongest models decreased from approximately **1.00** to around **0.94**.

This demonstrates why unusually high model performance should be investigated before considering a model reliable.

### 3. Tree-based models performed strongly

After removing the suspicious features, XGBoost, CatBoost, LightGBM, and Random Forest performed considerably better than Logistic Regression based on ROC-AUC and F1-score.

### 4. Accuracy alone is not enough

The project compares multiple evaluation metrics rather than relying only on accuracy.

---

📌 Conclusion

This project demonstrates a complete machine learning workflow for customer churn analysis, from data assessment and exploratory analysis to model comparison and investigation of suspiciously high predictive performance.

The main lesson from this project is that a model achieving extremely high performance is not automatically a good model. Investigating the data, validating suspicious features, and understanding why a model performs well are essential parts of a reliable machine learning workflow.

---

👤 Author

****Mahi Shahriar**

B.Sc. in Statistics
University of Rajshahi

---

⭐ If you find this project useful, feel free to explore the notebook and review the analysis.