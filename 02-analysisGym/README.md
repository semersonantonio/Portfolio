## Gym Member Churn Prediction

A complete Data Science project that analyzes gym member behavior and builds a machine learning model to predict customer churn.

The project combines behavioral analytics, feature engineering, machine learning and explainability to identify members at risk of canceling their subscriptions.

---

### Business Problem

Customer churn is one of the most critical challenges for subscription-based businesses such as gyms.

When members cancel their memberships, the business loses recurring revenue and increases customer acquisition costs.

Predicting churn allows the company to:

- identify members at risk of cancellation
- intervene with targeted retention strategies
- improve customer lifetime value

This project simulates a real-world gym environment and builds a churn prediction model based on behavioral and transactional data.

---

### Project Motivation

Before transitioning into Data Science, I spent **8 years working as a professional fitness trainer** in the gym industry.

During this time, I observed firsthand one of the biggest challenges faced by gyms: **member retention**.

Many members join with strong motivation but gradually reduce their attendance before eventually canceling their memberships.

This behavioral pattern raised an interesting question:

**Can we identify early signals that indicate when a member is likely to cancel?**

This project combines:

- my **domain experience in the fitness industry**
- my **technical training in Data Science**

The goal is to build a model capable of identifying early signs of disengagement and predicting churn risk.

---

### Dataset

The project uses a **synthetic dataset generator** to simulate gym operations.

Three datasets are generated:

#### Members

| Column | Description |
|------|-------------|
| member_id | unique member identifier |
| age | member age |
| gender | gender |
| city | location |
| signup_channel | acquisition channel |
| plan_type | membership plan |
| join_date | membership start date |
| cancel_date | cancellation date |

---

#### Check-ins

Represents gym attendance history.

| Column | Description |
|------|-------------|
| member_id | member identifier |
| date | check-in date |
| hour | visit hour |

---

#### Payments

Contains membership payment transactions.

| Column | Description |
|------|-------------|
| member_id | member identifier |
| date | payment date |
| amount | payment value |
| plan_type | membership plan |

---

### Machine Learning Model

The churn prediction model is trained using a **Gradient Boosting Classifier**.

### Model evaluation

| Metric | Score |
|------|------|
| Accuracy | ~0.85 |
| ROC-AUC | ~0.92 |

The model demonstrates strong ability to distinguish between active members and those at risk of churn.

---

### Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn
- SHAP

---

#### Author

Emerson Antonio da Silva

Data Science project developed as a portfolio case study focused on churn prediction and behavioral analytics.