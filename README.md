# European Fashion E-commerce Data Science Project

## Project Overview
This project presents an end-to-end data science workflow using a multi-table European fashion e-commerce dataset.  
The main objective is to identify high-value sales and support business decision-making using interpretable machine learning models.

The project includes data cleaning, feature engineering, regression analysis, classification, threshold tuning, model interpretation, and model comparison.

---

## Business Objective
The goal of this project is to predict whether a sale is a high-value sale based on historical transaction, campaign, and time-based features.  
The focus is on minimizing missed high-value sales rather than maximizing overall accuracy.

---

## Dataset Description
The dataset consists of multiple related tables:

- Campaign: campaign metadata and discount information  
- Channel: sales channel descriptions  
- Customer: customer demographic data  
- Products: product attributes  
- Sales: transaction-level sales data  
- SalesItem: item-level transaction details  
- Stock: product stock levels by country  

The final analytical dataset represents one row per sale.

---

## Data Cleaning and Preparation
The following steps were applied:

- Standardization of date columns
- Removal of unused and deprecated features
- Handling of missing values
- Consistent joins across multiple tables
- Removal of the product size column after validation

---

## Feature Engineering
Several meaningful features were created, including:

- Discount ratio
- Campaign active indicator
- Time-based features such as month and weekday
- Price margin derived from catalog and cost prices

These features were selected to balance model performance and interpretability.

---

## Regression Analysis
Linear regression was used as an exploratory step to understand the relationship between selected features and total sales value.  
This step was intended for insight generation rather than final prediction.

---

## Classification Model
Sales were classified into two categories:

- Class 1: High-value sales  
- Class 0: Normal sales  

Logistic Regression was selected as the primary classification model due to its interpretability and suitability for structured tabular data.

---

## Threshold Tuning
Instead of using the default probability threshold, the decision threshold was tuned to prioritize recall for the positive class.

Final threshold: 0.25  
Recall (Class 1): 0.73  
Precision (Class 1): 0.48  

Final decision rule:

If predicted probability ≥ 0.25, classify as high-value sale.  
Otherwise, classify as normal sale.

This approach reduces the risk of missing high-value sales.

---

## Model Interpretation
Feature importance analysis showed that:

- Discount ratio had the strongest influence and a negative relationship with high-value sales
- Campaign activity had a positive impact on high-value sales
- Time-based features had a relatively minor effect

The model behavior aligns well with expected business intuition.

---

## Deep Learning Comparison
A simple neural network was implemented for comparison purposes.  
However, its performance on the minority class was significantly weaker.

Recall (Class 1): 0.07

Due to poor performance and limited interpretability, the deep learning model was not selected.

---

## Final Model Selection
Logistic Regression was selected as the final model because it achieved strong recall for high-value sales while remaining interpretable and stable.

---

## Model Performance Summary

| Model               | Recall (Class 1) | Precision (Class 1) | ROC-AUC |
|---------------------|------------------|---------------------|---------|
| Logistic Regression | 0.73             | 0.48                | 0.72    |
| Deep Learning       | 0.07             | –                   | –       |

---

## Business Insights
- High-value sales are less dependent on aggressive discounting
- Campaign presence plays a more important role than discount depth
- The model can be used to prioritize sales or customers for targeted actions

---
## Future Improvements
- Collect additional data to improve model robustness
- Evaluate tree-based models such as Random Forest or XGBoost
- Incorporate customer-level behavioral features

---

## Repository Structure
├── notebook.ipynb
├── README.md
└── data/
---

Author: Gelareh Eghbalikalhor, 
Data Science Portfolio Project

