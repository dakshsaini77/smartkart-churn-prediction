# 🛒 SmartKart Customer Churn Prediction

An end-to-end Machine Learning project that predicts which SmartKart customers are likely to churn using **Logistic Regression**.

## 📌 Project Overview

Customer churn is an important business problem for retail companies. The goal of this project is to identify customers who are likely to leave SmartKart so that the retention team can take action before they churn.

This project takes a deliberately messy customer dataset through a complete **15-step ML pipeline**, from data collection and cleaning to model evaluation and a business-ready churn risk report.

## 🎯 Business Goal

Predict customer churn using:

* Age
* Monthly Spend
* Complaints

The model produces both a **churn prediction** and a **churn probability**, allowing customers to be identified based on their risk level.

## 📊 Dataset

The project uses:

`SmartKart_dirty_100_rows.csv`

The dataset contains **100 customer records** with 5 columns:

| Column          | Description                              |
| --------------- | ---------------------------------------- |
| `Customer_ID`   | Unique customer identifier               |
| `Age`           | Customer age                             |
| `Monthly_Spend` | Customer's monthly spending              |
| `Complaints`    | Number of customer complaints            |
| `Churn`         | Target variable: 0 = No Churn, 1 = Churn |

The dataset intentionally contains real-world-style data-quality problems, including:

* Duplicate records
* Missing values
* Incorrect data types
* Whitespace in values
* Invalid ages
* Negative spending values
* Extreme outliers

## 🔄 ML Pipeline

The notebook follows these **15 steps**:

1. Data Collection
2. Data Understanding
3. Data Cleaning
4. Outlier Detection & Treatment
5. Feature Selection
6. Define Target Variable
7. Encode Target Variable
8. Train-Test Split
9. Feature Standardisation
10. Model Building
11. Model Training
12. Prediction
13. Model Evaluation
14. Model Interpretation
15. Final Business Output

## 🧹 Data Preprocessing

The dataset is cleaned by:

* Removing duplicate records
* Removing unnecessary whitespace
* Converting `Age` to numeric format
* Correcting invalid values
* Replacing invalid values with missing values
* Filling missing values using the median
* Detecting outliers using the **IQR method**
* Capping extreme outliers instead of deleting customer records

After cleaning, the dataset contains **95 customer records**.

## 🤖 Machine Learning Model

### Logistic Regression

Logistic Regression was selected because churn is a **binary classification problem**.

The model uses three features:

```text
Age
Monthly_Spend
Complaints
```

Before training, the features are standardised using `StandardScaler`.

The data is divided using an **80/20 train-test split** with stratification and `random_state=42`.

## 📈 Model Evaluation

The model is evaluated using:

* Confusion Matrix
* Accuracy
* Precision
* Recall
* F1-Score

The notebook reports approximately:

* **Accuracy:** 89–95%
* **Recall:** ~100%
* **Precision:** 83–91%

The exact results are generated when the notebook is executed.

## 🔍 Model Interpretation

The Logistic Regression coefficients are used to understand how the selected features relate to predicted churn risk.

The notebook identifies:

* **Monthly Spend:** negative relationship with churn risk
* **Complaints:** positive relationship with churn risk
* **Age:** smaller positive relationship with churn risk

These relationships are observations from this dataset and should not be treated as universal conclusions about customer behaviour.

## 📋 Business Output

The project generates:

`smartkart_churn_risk_report.csv`

The report contains:

| Column              | Description                           |
| ------------------- | ------------------------------------- |
| `Customer_ID`       | Customer identifier                   |
| `Age`               | Customer age                          |
| `Monthly_Spend`     | Monthly spending                      |
| `Complaints`        | Number of complaints                  |
| `Actual_Churn`      | Actual churn status                   |
| `Predicted_Churn`   | Model prediction                      |
| `Churn_Probability` | Predicted probability of churn        |
| `Risk_Label`        | Likely to Churn / Not Likely to Churn |

The results are sorted by **churn probability**, making it easier for a retention team to identify higher-risk customers.

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Google Colab
* Logistic Regression

## 📁 Project Structure

```text
smartkart-churn-prediction/
│
├── SmartKart_Churn_Prediction_ML_Pipeline.ipynb
├── SmartKart_dirty_100_rows.csv
├── smartkart_churn_risk_report.csv
└── README.md
```

## 🚀 How to Run

### 1. Clone the repository

```bash
git clone https://github.com/your-username/smartkart-churn-prediction.git
cd smartkart-churn-prediction
```

### 2. Open the notebook

Open:

```text
SmartKart_Churn_Prediction_ML_Pipeline.ipynb
```

You can run it using **Google Colab** or Jupyter Notebook.

### 3. Upload the dataset

When prompted by the notebook, upload:

```text
SmartKart_dirty_100_rows.csv
```

### 4. Run all cells

Run the notebook from top to bottom.

The final step generates:

```text
smartkart_churn_risk_report.csv
```

## 🎓 Academic Context

**Course:** Introduction to AI & ML
**Program:** BBA AI/ML
**Institution:** Chitkara Business School
**CLO:** CLO02 — Apply data preprocessing, feature selection and ML models to business scenarios and evaluate performance using appropriate metrics.

## 💡 Key Learning Outcomes

This project demonstrates practical understanding of:

* Data cleaning
* Missing-value handling
* Outlier treatment
* Feature selection
* Target-variable preparation
* Train-test splitting
* Feature standardisation
* Logistic Regression
* Classification metrics
* Model interpretation
* Business-oriented ML outputs

## 📌 Project Summary

This project demonstrates how a messy customer dataset can be transformed into a complete machine-learning solution for customer churn prediction, while connecting model outputs to a practical business use case.

---

**Built with Python & Scikit-learn 🤖**
