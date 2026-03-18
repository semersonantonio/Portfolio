### Welcome to my Data Science portfolio.

This repository showcases projects focused on predictive analytics, machine learning, and operational optimization, with an emphasis on real-world business applications.

---

## Featured Project

## 01 Mexikans Analytics — Demand Forecasting for Veterinary Clinics  
**Folder:** `ES_MexikansVeterinaryNetwork`

End-to-end Data Science project focused on analyzing and predicting operational demand in a network of veterinary clinics.

---

### Business Problem

Veterinary clinic networks face significant variability in daily demand, which directly impacts:

- staff allocation  
- service capacity  
- waiting times  
- overall operational efficiency  

Without accurate forecasting, clinics operate reactively, leading to inefficiencies in both resource utilization and service quality.

The objective of this project is to anticipate demand and support operational planning through data-driven models.

---

### Dataset Overview

Synthetic dataset designed to simulate a veterinary clinic network:

- 50 clinics  
- 14 cities  
- 13,560 customers  
- 25,000 pets  
- 753,441 visits  
- $111,878,238 total revenue  

The dataset includes detailed operational records, enabling demand analysis at a daily level.

---

### Analytical Approach

The project follows a complete Data Science workflow:

- synthetic data generation  
- exploratory data analysis  
- feature engineering (temporal and behavioral features)  
- clinic segmentation using unsupervised learning  
- demand forecasting using machine learning models  
- model explainability using SHAP  

---

### Model Performance

The best-performing model was **Gradient Boosting**, selected based on comparative evaluation.

Results:

- R² ≈ 0.66  
- MAE ≈ 2–3 visits  
- RMSE ≈ 2.9 visits  

These results indicate that the model captures temporal demand patterns with sufficient accuracy for operational planning.

---

### Key Insights

- Demand follows identifiable temporal patterns  
- Recent demand is the strongest predictor of future visits  
- Clinics operate under different performance profiles  
- Demand is not purely random and can be modeled effectively  

---

### Business Impact

The solution enables:

- improved demand forecasting  
- more efficient staff planning  
- better allocation of clinical resources  
- reduction of operational uncertainty  

This supports a transition from reactive to proactive operational management.

---

### Tools & Technologies

- Python  
- Pandas / NumPy  
- Scikit-learn  
- SHAP  
- Matplotlib / Seaborn  
