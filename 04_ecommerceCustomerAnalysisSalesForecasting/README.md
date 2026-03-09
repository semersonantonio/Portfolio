# E-commerce Customer Analytics and Sales Forecasting

End-to-end Data Science project simulating a real-world e-commerce analytics pipeline.

This project demonstrates how machine learning and data analysis can be applied to understand customer behavior and forecast sales in an online retail environment.

The project covers the full lifecycle of a data science workflow, including:

- data generation
- exploratory data analysis
- feature engineering
- customer segmentation
- sales forecasting
- model explainability

---

## Project Goals

This project focuses on solving two core business problems commonly faced by e-commerce companies.

### Customer Analytics

Understanding customer behavior is critical for designing effective marketing strategies.

Customer segmentation enables businesses to:

- personalize marketing campaigns
- identify high-value customers
- improve customer retention
- optimize promotional strategies

### Sales Forecasting

Reliable revenue forecasting supports several operational decisions:

- inventory planning
- marketing campaign scheduling
- staffing and logistics planning
- financial forecasting

Machine learning models are used to predict daily revenue based on historical purchasing behavior and temporal patterns.

---

# Visual Overview

Below are key visualizations generated during the analysis.

## Revenue Trend

The dataset simulates realistic daily revenue patterns including growth trends and seasonality.

![Revenue Trend](figures/daily_revenue_trend.png)

---

## Weekly Purchasing Patterns

Customer purchasing behavior often varies by day of week.

![Weekday Seasonality](figures/weekday_seasonality.png)

This pattern is common in e-commerce environments where weekend shopping behavior differs from weekday activity.

---

## Forecasting Model Performance

Multiple machine learning models were evaluated for revenue forecasting.

![Model RMSE Comparison](figures/model_rmse_comparison.png)

Tree-based ensemble models significantly outperform the baseline forecast.

---

## Forecast vs Actual Revenue

The best-performing model captures the overall revenue trend and daily fluctuations.

![Forecast vs Actual](figures/forecast_vs_actual.png)

---

## Feature Importance

The most influential predictors of revenue are shown below.

![Feature Importance](figures/feature_importance.png)

Key drivers include:

- order volume
- recent revenue trends
- rolling averages
- temporal features

---

# Dataset

Since real-world e-commerce data is often proprietary, this project generates a **synthetic dataset** designed to mimic realistic online retail activity.

The dataset includes multiple types of variables:

### Customer Attributes

- customer_id
- age
- income
- country
- loyalty_member
- signup_date

### Behavioral Variables

- total_orders
- total_spent
- average_order_value
- days_since_last_purchase
- website_visits
- app_usage
- discount_usage

### Transactional Variables

- order_date
- order_value
- product_category
- promotion
- marketing_campaign

### Temporal Variables

- month
- weekday
- seasonal patterns
- rolling revenue statistics
- lag features

The synthetic data incorporates realistic behaviors including:

- seasonal fluctuations
- promotions and campaigns
- gradual platform growth
- random demand variability

---

# Project Structure

The project is organized into multiple notebooks representing each stage of the data science workflow.
ecommerce-analytics-forecasting
│
├── notebooks
│   ├── 01_dataset_generation.ipynb
│   ├── 02_exploratory_analysis.ipynb
│   ├── 03_feature_engineering.ipynb
│   ├── 04_customer_segmentation.ipynb
│   ├── 05_sales_forecasting.ipynb
│   └── 06_model_explainability.ipynb
│
├── data
│   ├── raw
│   └── processed
│
├── figures
│
├── src
│
├── requirements.txt
│
└── README.md

---

# Methodology

## Exploratory Data Analysis

Exploratory analysis was conducted to understand the structure and dynamics of the dataset.

Key analyses included:

- revenue trend analysis
- customer purchasing patterns
- seasonal behavior
- correlation analysis

---

## Feature Engineering

Several predictive features were created to improve model performance.

Examples include:

- lag features
- rolling averages
- rolling standard deviation
- temporal encodings
- behavioral metrics

These features capture both short-term and long-term patterns in purchasing behavior.

---

## Customer Segmentation

Clustering algorithms were used to identify distinct customer groups.

Algorithms evaluated:

- K-Means
- Hierarchical Clustering
- DBSCAN

Customer segments can support:

- targeted promotions
- retention campaigns
- personalized recommendations

---

## Sales Forecasting

Machine learning models were trained to predict daily revenue.

Models evaluated:

- Linear Regression
- Random Forest
- Gradient Boosting
- XGBoost

Evaluation metrics:

- MAE
- RMSE
- R²
- MAPE

Residual diagnostics and forecast visualizations were also used to assess model performance.

---

# Model Explainability

Machine learning models can be difficult to interpret.

To address this challenge, SHAP (SHapley Additive Explanations) was used to interpret the forecasting model.

![SHAP Summary](figures/shap_summary_plot.png)

SHAP analysis provides both global and local explanations of model predictions.

Global explanations identify which variables most strongly influence predictions.

Local explanations show how individual features contribute to specific predictions.

This transparency helps increase trust in machine learning systems.

---

# Key Insights

Several insights emerged from the analysis.

### Revenue Drivers

The most influential predictors of revenue include:

- daily order volume
- recent revenue trends
- rolling revenue statistics
- temporal patterns such as day-of-week

### Forecasting Performance

Ensemble models significantly outperform simple baseline forecasting methods.

Gradient Boosting achieved the best overall performance across evaluation metrics.

### Customer Behavior

Customer segmentation reveals distinct purchasing patterns that can inform marketing strategies.

---

# Business Applications

This analysis supports several real-world business decisions:

Inventory planning

Forecasting demand helps reduce stockouts and overstock situations.

Marketing strategy

Customer segmentation enables targeted promotional campaigns.

Operational planning

Revenue forecasts support logistics and staffing decisions.

Financial planning

Sales forecasts inform budgeting and revenue projections.

---

# Technologies Used

Python ecosystem:

- pandas
- numpy
- scikit-learn
- xgboost
- shap
- matplotlib
- seaborn
- statsmodels

---

# Future Improvements

Potential extensions of this project include:

- product-level demand forecasting
- real-time forecasting dashboards
- automated model retraining pipelines
- deployment as an API or web application

---

# Author

Emerson Antonio da Silva

Data Science Portfolio Project

E-commerce Analytics and Sales Forecasting