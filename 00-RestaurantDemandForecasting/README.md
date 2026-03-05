### Restaurant Demand Forecasting

Machine learning system to forecast **daily restaurant demand** using
time-series features and explainable AI techniques.

---

### Project Overview

Accurate demand forecasting is essential for restaurant operations.
Predicting customer demand allows restaurants to optimize staffing,
inventory planning, and promotional strategies.

This project builds a **machine learning pipeline to forecast daily restaurant demand** using a synthetic dataset that simulates realistic demand drivers.

The project demonstrates an end-to-end **Data Science workflow**, including:

- synthetic dataset generation  
- exploratory data analysis (EDA)  
- feature engineering for time-series data  
- machine learning forecasting models  
- model explainability using SHAP  

The objective is to understand **which factors drive restaurant demand**
and build models capable of predicting future orders.

---

### Business Problem

Restaurants often face unpredictable demand patterns that make
operational planning difficult.

Accurate demand forecasting helps restaurants:

- optimize staff scheduling  
- reduce food waste  
- improve inventory planning  
- plan promotions more effectively  

By anticipating demand fluctuations, restaurant managers can improve
operational efficiency and customer experience.

---

### Machine Learning Workflow

This project follows a structured machine learning pipeline.

#### 1. Dataset Generation

A synthetic dataset simulating restaurant demand was created.

The dataset incorporates realistic drivers such as:

- weekly seasonality  
- yearly seasonality  
- weather conditions  
- promotions  
- local events  
- tourism seasons  
- festival weeks  
- economic slowdown periods  
- long-term demand growth  

---

#### 2. Exploratory Data Analysis

Exploratory analysis was conducted to identify demand patterns and
external drivers.

Key aspects analyzed include:

- demand distribution  
- weekly seasonality  
- monthly seasonality  
- promotion impact  
- weather relationships  
- correlation between variables  

These insights guided the feature engineering process.

---

#### 3. Feature Engineering

Several feature types commonly used in **time-series forecasting** were created.

##### Lag Features

Previous demand values:

- orders_lag_1  
- orders_lag_7  
- orders_lag_14  
- orders_lag_30  

##### Rolling Statistics

Demand trends and volatility:

- rolling_mean_7  
- rolling_mean_14  
- rolling_mean_30  
- rolling_std_7  
- rolling_std_14  

##### Momentum Indicators

Recent demand changes:

- momentum_1_7  
- momentum_7_14  

##### Cyclical Time Encoding

Seasonal transformations:

- dow_sin / dow_cos  
- month_sin / month_cos  

These features allow machine learning models to capture **temporal dynamics and seasonal patterns** in restaurant demand.

---

### Model Training

Multiple machine learning models were evaluated:

- Linear Regression  
- Random Forest  
- Gradient Boosting  

A **baseline forecasting model** using the previous day's demand was also included.

Model performance was evaluated using:

- Mean Absolute Error (MAE)  
- Root Mean Squared Error (RMSE)  

Time-series cross-validation was used to ensure robust evaluation.

---

### Results

The **Gradient Boosting model** achieved the best predictive performance among the evaluated models.

Approximate performance metrics:

- Mean Absolute Error (MAE): ~9 orders  
- Root Mean Squared Error (RMSE): ~12 orders  

The model successfully captures:

- weekly demand patterns  
- seasonal fluctuations  
- the impact of promotions and local events  
- short-term demand dynamics  

---

### Model Explainability

To understand how the forecasting model makes predictions,
**SHAP (SHapley Additive Explanations)** was applied.

This analysis revealed that the most influential demand drivers include:

- base demand level  
- promotions  
- local events  
- rolling demand trends  
- seasonal patterns  

SHAP enables interpretation of both:

- **global feature importance**
- **individual prediction explanations**

This improves transparency and trust in the forecasting model.

---

### Technologies Used

Python libraries used in this project include:

- pandas  
- numpy  
- scikit-learn  
- matplotlib  
- seaborn  
- SHAP  
- joblib  

---

### Key Insights

This project demonstrates how machine learning can be applied to
**restaurant demand forecasting**.

Key insights include:

- restaurant demand exhibits strong weekly patterns  
- promotions and events significantly influence demand  
- lag features and rolling statistics improve forecasting performance  
- explainability techniques reveal the drivers behind model predictions  

---

### Future Improvements

Potential improvements include:

- using real-world datasets  
- experimenting with advanced models such as XGBoost or LightGBM  
- deploying the forecasting model as an API  
- building an interactive demand forecasting dashboard  

---

### Author
Emerson Antonio da Silva

Data Science Portfolio Project

Restaurant Demand Forecasting with Machine Learning
