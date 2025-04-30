# Bike-Sharing Demand Prediction 🚴♂️📈

## Overview
This project develops a **supervised machine learning regression model** to predict demand in bike-sharing systems. By analyzing how demand varies with different features, the model helps businesses optimize operations and understand market dynamics.

## Problem Statement
**Objective:** Predict bike rental demand (`rented_bike_count`) as a continuous variable.  
**Business Value:**
- Adjust inventory and staffing based on anticipated demand
- Optimize pricing strategies
- Understand key factors influencing bike rentals in new markets

## Data Pipeline

### 1. Exploratory Data Analysis (EDA)
- Analyzed distributions of all variables
- Applied transformations (log, sqrt) to achieve normal distributions
- Tested critical business hypotheses:
  - "Temperature significantly affects rental demand"
  - "Weekends show different rental patterns than weekdays"
  - "Hourly demand follows predictable peaks"

### 2. Data Preparation
- **Null Value Treatment:** Imputed missing values using median/mean
- **Feature Engineering:**
  - Extracted temporal features (hour, day_of_week, month)
  - Created weather-based features
- **Encoding:** One-hot encoding for categorical variables
- **Scaling:** Standardized numeric features (StandardScaler)

### 3. Model Training
**Algorithms Implemented:**
| Model | R² Score | Key Characteristics |
|-------|----------|---------------------|
| Linear Regression | 0.72 | Baseline |
| Regularized (Lasso/Ridge) | 0.74 | Reduced overfitting |
| Decision Tree | 0.76 | Interpretable splits |
| Random Forest | 0.84 | Robust to outliers |
| AdaBoost | 0.58 | Poor performance |
| **Gradient Boosting (GBM)** | **0.88** | **Best performer** |

### 4. Model Evaluation
- **Metrics:** R², MAE, RMSE
- **Hyperparameter Tuning:** GridSearchCV for optimal parameters
- **Feature Importance:** 
  - Top predictors: Hour of day, Temperature, Humidity
  - Surprising finding: Holiday effect less significant than expected

## Key Findings
- **Temporal patterns dominate:** Hour of day accounts for ~40% of predictive power
- **Weather sensitivity:** Demand drops sharply when temperature < 5°C or during rain
- **GBM superiority:** Outperformed other models by 4-30% on R² score
