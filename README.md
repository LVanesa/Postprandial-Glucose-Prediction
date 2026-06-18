# Postprandial Glucose Response Prediction Using CGM and Nutritional Data

A comparative study of machine learning approaches for predicting postprandial glucose response (PPGR) using continuous glucose monitoring (CGM), nutritional intake, clinical biomarkers, and physical activity data.

## Overview

Postprandial glucose response varies substantially across individuals, even when consuming identical meals. Understanding and predicting this variability is important for personalized nutrition, metabolic health assessment, and diabetes prevention.

This project compares multiple machine learning paradigms for PPGR prediction using the CGMacros dataset:

* Linear Models (OLS)
* Linear Mixed-Effects Models (LMM)
* XGBoost
* TabPFN (Tabular Foundation Model)

Models are evaluated using Leave-One-Subject-Out (LOSO) cross-validation to prevent subject-level data leakage and assess generalization to unseen individuals.

## Dataset

This work uses the CGMacros dataset:

[*CGMacros: A Pilot Scientific Dataset for Personalized Nutrition and Diet Monitoring*](https://www.nature.com/articles/s41597-025-05851-7).

The dataset includes:

* Continuous Glucose Monitoring (CGM)
* Meal nutritional information
* Clinical biomarkers
* Physical activity measurements
* Demographic information

Participants belong to three metabolic groups:

* Healthy
* Pre-diabetic
* Type-2 Diabetes

## Prediction Targets

Two complementary measures of postprandial glucose response were modeled:

1. **AUC**: Total area under the glucose curve over the 2-hour postprandial window.

2. **iAUC**: Incremental area under the curve above baseline glucose, capturing the reactive glucose spike.

## Methods

### Linear Models

* Ordinary Least Squares (OLS)
* Linear Mixed-Effects Models (LMM)

### Gradient Boosting

* XGBoost

### Foundation Models

* TabPFN

## Evaluation

Models were evaluated using:

* Pearson Correlation (r)
* RMSE
* MAE
* R²

Cross-validation strategy:

* Leave-One-Subject-Out (LOSO)

## Main Findings

* Breakfast meals consistently yielded the highest predictive performance.
* Dinner meals were substantially harder to predict due to higher variability.
* Physical activity features provided modest improvements, especially for iAUC prediction.
* TabPFN achieved performance comparable to XGBoost without extensive hyperparameter tuning.
* Carbohydrates, HbA1c, fasting glucose, and baseline glucose were among the most influential predictors.


