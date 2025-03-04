# Loan Default Analysis

## Overview
This project uses exploratory data analysis and builds supervised machine learning models to predict the housing loan default status based on characteristics associated with the loan.

## Business Understanding
Albeit the rigorous loan approval process, many loans still default at the cost of profit and risk to the bank. Our data science team is tasked to gather insights into real estate loans for both commercial and retail borrowers, on what charateristics of a loan will make  more likely to default. By building a model that is best positioned to predict the loan data with actual defaults, minimizing false negatives (i.e. default loans predicted as non-default), we can help mitigate the most major risk of missing to monitor a loan that is likely to default.

## Repository Navigation
The repository has three notebooks and a data folder. You will find the appropriate information within each specific file.
data
- Loan_Default.csv
 cleaned.csv
Notebooks
- Data Cleaning
- EDA
- Classification_Models

## Presentation and Data Source
- 2019 The loan default data set from Kaggle - [Link](https://www.kaggle.com/datasets/yasserh/loan-default-dataset/data)
- Presentation - [Link](https://docs.google.com/presentation/d/1KgJH2fwKUstvnzfsk29R9V8aWu8x1A1pqu2k8tJLzUc/edit#slide=id.p)

## Data and Model Analysis
The data for this project has been cleaned and sorted for the final analysis.
Many tools were used in this process of analysis, including but not limited to pandas, seaborn, sklearn, etc.
After cleaning the data, we set our target variable to "Status" as its values are binary (0 or 1) where 0 means Non-Default, and 1 means Default.
With this set as our target variable, we looked at pairplots using seaborn, where the various plots were hued on "Status".
In doing so, we noticed a correlation in the "LTV" (Loan to Value), "dtir1" (Debt to Income Ratio), "income", "loan_amount", "lump_sum_payment", "Neg_ammortization", and "business_or_commerical" columns.
Next, we ran several models including Logistic Regression, Decision Tree, and K-Nearest Neighbor while maximizing our recall score.
Recall score was important to this project because it was imperative for us to predict loans with acutal default status and minimize false negatives (loans that were not seen as defaulting, but did in fact default).
After running several models, we:
- added features for Logistic Regression
- addressed the class imbalance
-- (balanced the class weights, performed SMOTE)
- ran hyperparameter tuning using cross-validation
-- best K, C for regularization, addressing Tree depth

## Conclusion
By the end of the process, the Decision Tree was our most effective model, with a test set recall score of 0.65 and a tree depth set to 4.
The key features with highest importance were "dtir1", "income", "LTV", "Neg_ammortization", "lump_sum_payment", and "business_or_commercial".
To improve this model further, we would require more default data from various years to improve accuracy and precision.
