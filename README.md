# Customer Churn Prediction with Logistic Regression

## Overview

This repository contains an R script for predicting customer churn in a bank using Logistic Regression. The analysis involves data exploration, preprocessing, handling multicollinearity, feature standardization, variable selection, binning, model building, threshold optimization, and performance evaluation.

## Script Details

### 1. Data Exploration and Preparing for Modelling

- **Libraries:** The script loads necessary R libraries for data manipulation, exploratory data analysis, model building, and visualization.

- **Data Loading:** The dataset "CHURN.csv" is loaded using the `data.table` library.

- **Exploration:** The script explores the dataset using functions like `glimpse`, `inspect_na`, and `View`.

- **Data Cleaning:** Unnecessary columns ('RowNumber', 'CustomerId', 'Surname') are removed, and the target variable 'Exited' is converted to a binary factor.

- **Information Value (IV) Analysis:** IV is calculated for variable selection based on a threshold of 0.02.

- **Binning:** Binning is performed on the selected variables.

- **Outlier Handling:** Outliers in numeric variables are identified and handled.

- **Dummy Variable Creation:** Dummy variables are created for character variables.

- **Train-Test Split:** The dataset is split into training and testing sets.

- **WoE Transformation:** Weight of Evidence (WoE) transformation is applied on training and testing sets.

### 2. Modelling

- **Variable Selection:** Logistic regression model is built using the `glm` function.

- **Model Refinement:** Non-significant variables are iteratively removed based on p-values.

- **Handling Multicollinearity:** Variables with high Variance Inflation Factor (VIF) are removed iteratively.

- **H2O GLM Model:** An H2O GLM model is built with variable selection, removal of collinear columns, and iterative refinement.

### 3. Model Evaluation

- **Model Predictions:** Predictions are made on the test set using the H2O model.

- **Performance Evaluation:** Model performance is evaluated using H2O's performance metrics, including precision, AUC, Gini, and confusion matrix.

- **ROC & AUC Curves:** ROC curves are generated, and the threshold for the max F1 score is identified. AUC and Gini values for train and test sets are displayed.

- **Overfitting Check:** Overfitting is checked by comparing AUC scores between train and test sets.

## Dataset Information

### Description

The dataset contains information about bank customers, and the goal is to predict customer churn based on various features.

### Analysis Steps

1. **Handling Multicollinearity:** Identify and remove variables with high VIF.

2. **Standardize Features:** Standardize numeric features.

3. **Split Data:** Split the data into training and testing sets using seed=123.

4. **Exclude Unimportant Variables:** Exclude variables with information value less than 0.02.

5. **Apply Binning:** Apply binning according to the Weight of Evidence (WoE) principle.

6. **Build Logistic Regression Model:** Build a logistic regression model with p-value variables below 0.05.

7. **Find Threshold:** Find the threshold by maximizing the F1 score.

8. **Calculate AUC Score:** Calculate AUC scores for both train and test sets.

9. **Check Overfitting:** Compare AUC scores to check for overfitting.

## How to Use

To replicate the analysis:

1. Ensure you have R and the required libraries installed.
2. Place the "CHURN.csv" dataset in the same directory as the script.
3. Run the script in an R environment, considering any specific package dependencies.

## Author

- **Author:** [Your Name]
- **Date:** [Date]


