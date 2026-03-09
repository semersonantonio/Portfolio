# E-commerce Customer Analytics and Sales Forecasting

End-to-end Data Science project simulating a realistic analytics pipeline for an e-commerce platform.

This project demonstrates how machine learning and data analysis can be applied to:

- understand customer purchasing behavior
- segment customers for targeted marketing
- forecast future revenue
- interpret machine learning models

The project replicates the workflow typically used in real-world data science environments.

---

# Project Overview

E-commerce companies generate large volumes of behavioral and transactional data.  
Analyzing this data allows businesses to better understand customer behavior and predict future demand.

This project builds a complete machine learning pipeline for:

Customer analytics

- identifying customer segments
- understanding purchasing behavior
- supporting targeted marketing strategies

Sales forecasting

- predicting future revenue
- identifying demand trends
- supporting operational planning

---

# Visual Overview

Below are key visualizations generated during the analysis.

---

## Revenue Distribution

This visualization shows how revenue is distributed across different engagement segments.

![Revenue by Engagement](figures/exploratory_analysis/revenue_by_engagement_segment.png)

---

## Revenue Contribution (Pareto Analysis)

The Pareto curve highlights that a small portion of customers contributes a large share of total revenue.

![Pareto Revenue Curve](figures/exploratory_analysis/pareto_revenue_curve.png)

---

## Loyalty vs Non-Loyalty Customers

Loyalty program members typically generate higher revenue compared to non-members.

![Loyalty Revenue](figures/exploratory_analysis/loyalty_vs_non_loyalty_revenue.png)

---

## Forecasting Model Performance

Multiple machine learning models were evaluated for predicting daily revenue.

![Model Comparison](figures/sales_forecasting/model_rmse_comparison.png)

Tree-based ensemble models significantly outperform simple baseline forecasts.

---

## Forecast vs Actual Revenue

The best-performing model captures both overall trends and short-term fluctuations in sales.

![Forecast vs Actual](figures/sales_forecasting/forecast_vs_actual.png)

---

## Feature Importance

Feature importance analysis identifies the most influential predictors of revenue.

![Feature Importance](figures/sales_forecasting/feature_importance.png)

Key drivers include:

- daily order volume
- recent revenue trends
- rolling averages
- temporal features

---

## Model Explainability

SHAP explainability techniques were used to interpret the forecasting model.

![SHAP Summary](figures/model_explainability/shap_summary_plot.png)

SHAP values help explain how individual variables influence model predictions.

---

# Dataset

Since real-world e-commerce datasets are typically proprietary, this project generates a synthetic dataset designed to mimic realistic online retail behavior.

The dataset includes several categories of variables.

### Customer attributes

- customer_id
- age
- income
- country
- loyalty membership
- signup date

### Behavioral variables

- total orders
- total spent
- average order value
- days since last purchase
- website visits
- app usage
- discount usage

### Transaction variables

- order date
- order value
- product category
- promotion flag
- marketing campaigns

### Temporal features

- day of week
- month
- seasonal indicators
- rolling statistics
- lag variables

The synthetic dataset incorporates realistic dynamics such as:

- seasonal demand patterns
- promotional campaigns
- gradual platform growth
- random purchasing variability


---

# Project Workflow

The project is organized into several notebooks representing each stage of the data science pipeline.

---

## 1 Dataset Generation

Synthetic e-commerce data is generated to simulate realistic customer behavior and transactional activity.

Key characteristics:

- seasonal demand patterns
- promotional effects
- customer behavior variability
- long-term growth trends

---

## 2 Exploratory Data Analysis

Exploratory analysis investigates the structure and patterns within the dataset.

Key analyses include:

- revenue trends
- purchasing seasonality
- behavioral correlations
- distribution of customer metrics

---

## 3 Feature Engineering

New predictive features are created to improve machine learning performance.

Examples include:

- lag features
- rolling averages
- rolling volatility
- RFM-style metrics
- temporal encodings

These features capture both short-term and long-term patterns in purchasing behavior.

---

## 4 Customer Segmentation

Clustering techniques are applied to identify groups of customers with similar purchasing patterns.

Algorithms evaluated include:

- K-Means
- Hierarchical Clustering
- DBSCAN

Customer segmentation can support:

- targeted marketing campaigns
- loyalty programs
- personalized promotions

---

## 5 Sales Forecasting

Machine learning models are trained to forecast daily revenue.

Models evaluated:

- Linear Regression
- Random Forest
- Gradient Boosting
- XGBoost

Evaluation metrics include:

- MAE
- RMSE
- R²
- MAPE

Residual diagnostics and forecast visualizations are used to validate model performance.

---

## 6 Model Explainability

To understand model behavior, SHAP explainability techniques are applied.

The analysis includes:

- global feature importance
- SHAP summary plots
- feature dependence analysis
- local prediction explanations

Explainability provides transparency into how the forecasting model generates predictions.

---

# Key Insights

Several insights emerged from the analysis.

### Revenue drivers

Revenue predictions are strongly influenced by:

- order volume
- recent purchasing activity
- rolling revenue statistics
- temporal purchasing patterns

### Forecasting performance

Ensemble machine learning models significantly outperform simple baseline forecasts.

Gradient Boosting achieved the best predictive performance.

### Customer behavior

Customer segmentation reveals distinct purchasing patterns that can inform marketing strategies.

---

# Business Applications

This analysis supports several real-world business decisions.

### Inventory planning

Demand forecasts help reduce stockouts and excess inventory.

### Marketing strategy

Customer segmentation enables targeted promotional campaigns.

### Operational planning

Revenue forecasts support logistics and staffing decisions.

### Financial planning

Sales forecasts inform budgeting and revenue projections.

---

# Technologies Used

Python ecosystem

Main libraries:

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

Possible extensions of this project include:

- product-level demand forecasting
- real-time forecasting dashboards
- automated model retraining pipelines
- deployment of forecasting models as an API

---

# Author

Emerson Antonio da Silva

Data Science Portfolio Project

E-commerce Customer Analytics and Sales Forecasting
