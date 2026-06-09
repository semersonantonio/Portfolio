# 📊 Data Science Portfolio — Emerson Antonio da Silva

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/semersonantonio)
[![Email](https://img.shields.io/badge/Email-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:s.emersonantonio@gmail.com)

> Data Science student at UNIR · AI QA Engineer Intern at ObviousFuture · Madrid, Spain

This repository showcases end-to-end Data Science projects focused on predictive analytics, machine learning, and operational optimization, with emphasis on real-world business applications.

---

## 🗂️ Projects

| # | Project | Domain | Tech | Status |
|---|---|---|---|---|
| 01 | [🐾 Mexikans Analytics — Demand Forecasting for Veterinary Clinics](./ES_MexikansVeterinaryNetwork) | Healthcare / Operations | Python, Pandas, Scikit-learn | ✅ Complete |
| 02 | [🫀 CardioRisk ML — Cardiovascular Risk Prediction](./CardioRisk_ML) | Healthcare / Machine Learning | Python, Scikit-learn, XGBoost, SMOTE | ✅ Complete |

---

## 01 · Mexikans Analytics — Demand Forecasting for Veterinary Clinics

**Folder:** `ES_MexikansVeterinaryNetwork`

End-to-end Data Science project focused on analysing and predicting operational demand in a network of veterinary clinics.

### Business Problem

Veterinary clinic networks face significant variability in daily demand, which directly impacts:

- Staff allocation
- Service capacity
- Waiting times
- Overall operational efficiency

Without accurate forecasting, clinics operate reactively, leading to inefficiencies in resource utilisation and service quality.

**Objective:** Anticipate demand and support operational planning through data-driven models.

### Key Highlights

- Exploratory Data Analysis (EDA) on clinic visit patterns
- Feature engineering from temporal and categorical variables
- Multiple regression and time-series forecasting models evaluated
- Business-oriented insights and recommendations

---

## 02 · CardioRisk ML — Cardiovascular Risk Prediction

**Folder:** `CardioRisk_ML`

End-to-end machine learning pipeline for binary classification of cardiovascular risk in a synthetic clinical dataset of 10,000 adult patients, calibrated against the Framingham Heart Study and NHANES.

### Clinical Questions

This project addresses three clinical questions:

- Which clinical and lifestyle factors most drive cardiovascular risk?
- Can a machine learning model reliably identify at-risk patients preventively?
- What probability threshold maximises clinical utility in a screening context?

### Key Highlights

- Synthetic dataset of 10,000 patients with 29 clinical, lifestyle, and demographic variables
- 8 engineered clinical features: LDL/HDL ratio, metabolic syndrome score, lifestyle score, and 3 interaction terms
- 6 algorithms evaluated with 5-fold cross-validation and a composite clinical scoring metric (Recall × 0.40 + AUC × 0.40)
- Champion model: Logistic Regression — AUC 0.866, Recall 0.747 at default threshold
- At screening threshold t = 0.35: Recall 0.863 (~9 in 10 high-risk patients correctly identified)
- Includes a 10-slide presentation deck summarising all findings

---

## 📬 Contact

- **LinkedIn:** [linkedin.com/in/semersonantonio](https://linkedin.com/in/semersonantonio)
- **Email:** s.emersonantonio@gmail.com
- **Location:** Madrid, Spain
