# SSIM916 - Problem Set 1
## Project: Telco Customer Churn Prediction & Analysis

## Overview
This project predicts customer churn in the telecom industry using the IBM Telco Customer Churn dataset. This project aims to predict customer churn for a telecommunications provider using machine learning. By identifying high-risk customers, the business can proactively implement retention strategies to reduce revenue loss. 

## Business Objective: 
Identify customers at risk of churning early enough for the retention team to intervene proactively, reducing revenue loss from customer attrition. Maximize **Recall** to capture as many potential churners as possible, as the cost of losing a customer far outweighs the cost of a retention campaign. Two classification models are selected: Logistic Regression and Random Forest. 

## Dataset
- **Source**: IBM Telco Customer Churn (Kaggle)
- **Size**: 7,043 customers, 21 features
- **Target variable**: Churn (binary: Yes/No, 26.5% churn rate)

## Project Structure
```
SSIM916-Problem-Set-1/
├── data/
│   ├── Problem_Set_1.ipynb
│   └── WA_Fn-UseC_-Telco-Customer-Churn.csv
└── README.md
```

## How to Run
1. Clone the repository
2. Open `data/Problem_Set_1.ipynb` in Jupyter Notebook
3. Place `WA_Fn-UseC_-Telco-Customer-Churn.csv` in the same folder
4. Run all cells sequentially

## Key Insights from EDA
Exploratory Data Analysis revealed several critical drivers of churn:
**Tenure**: New customers are the most vulnerable, specifically within the first 20 months of service.
**Service & Value**: Fiber optic users are primary churn drivers, typically associated with high monthly charges (Median ~$80).
**Add-on Services**: A lack of add-ons services like OnlineSecurity and TechSupport strongly correlates with higher churn volumes.
**Contract**: Month-to-month contract status is the primary driver influencing a customer's decision to leave the service.
**Payment Method**: Electronic Check is a critical risk factor, accounting for over 1,071 churners, triple the volume of any other payment method.
**Demographics**: Customers with no partners or dependents show significantly higher attrition rates, while gender is a neutral factor.

## Features Selected (7)
Based on correlation matrix and EDA findings:
`Contract_Month-to-month`, `InternetService_Fiber optic`,`PaymentMethod_Electronic check`,`tenure`,`OnlineSecurity_No`,`TechSupport_No`, `Contract_Two year`

## Model Results
| Metric | Logistic Regression | Random Forest |
|---|---|---|
| Accuracy | 0.7374 | 0.7828 |
| Precision | 0.5034 | 0.6097 |
| **Recall** | **0.8021** | 0.5053 |
| F1-Score | 0.6186 | 0.5526 |
| ROC-AUC | 0.8373 | 0.8127 |

**Final model: Logistic Regression** 
Selected based on superior Recall (0.80), directly aligned with the business objective of minimising missed churners.

## Requirements
pandas, numpy, scikit-learn, matplotlib, seaborn

## Author
Phuong Thuy Do | Student ID: 750081635 | SSIM916
