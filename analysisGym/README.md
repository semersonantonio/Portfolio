{\rtf1\ansi\ansicpg1252\cocoartf2822
\cocoatextscaling0\cocoaplatform0{\fonttbl\f0\fswiss\fcharset0 Helvetica;\f1\froman\fcharset0 Times-Roman;}
{\colortbl;\red255\green255\blue255;\red0\green0\blue0;}
{\*\expandedcolortbl;;\cssrgb\c0\c0\c0;}
\paperw11900\paperh16840\margl1440\margr1440\vieww11520\viewh8400\viewkind0
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural\partightenfactor0

\f0\fs24 \cf0 # Gym Member Churn Prediction\
\
A complete Data Science project that analyzes gym member behavior and builds a machine learning model to predict customer churn.\
\
The project combines behavioral analytics, feature engineering, machine learning and explainability to identify members at risk of canceling their subscriptions.\
\
\
---\
\
\
# Business Problem\
\
Customer churn is one of the most critical challenges for subscription-based businesses such as gyms.\
\
When members cancel their memberships, the business loses recurring revenue and increases customer acquisition costs.\
\
Predicting churn allows the company to:\
\
\'95 identify members at risk of cancellation  \
\'95 intervene with targeted retention strategies  \
\'95 improve customer lifetime value  \
\
This project simulates a real-world gym environment and builds a churn prediction model based on behavioral and transactional data.\
\
\
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural\partightenfactor0
\cf0 ---\
\
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural\partightenfactor0
\cf0 \
## Project Motivation\
\
Before transitioning into Data Science, I spent **8 years working as a professional fitness trainer** in the gym industry.\
\
During this time, I observed firsthand one of the biggest challenges faced by gyms: **member retention**. Many members join with strong motivation but gradually reduce their attendance before eventually canceling their memberships.\
\
This behavioral pattern raised an interesting question from a data perspective:\
\
**Can we identify early signals that indicate when a member is likely to cancel?**\
\
As I began studying Data Science, I realized that this problem could be approached using behavioral analytics and machine learning techniques.\
\
This project was created as a way to combine:\
\
\'95 my **domain experience in the fitness industry**  \
\'95 my **technical training in Data Science**  \
\
By simulating a realistic gym dataset and analyzing member behavior, the goal of this project is to build a model capable of identifying early signs of disengagement and predicting churn risk.\
\
This type of analysis can help gyms design **proactive retention strategies** and improve long-term customer relationships.\
\
\
---\
\
\
# Dataset\
\
The project uses a **synthetic dataset generator** to simulate gym operations.\
\
Three datasets are generated:\
\
### Members\
\
Contains demographic and membership information.\
\
| Column | Description |\
|------|-------------|\
member_id | unique member identifier |\
age | member age |\
gender | gender |\
city | location |\
signup_channel | acquisition channel |\
plan_type | membership plan |\
join_date | membership start date |\
cancel_date | cancellation date |\
\
\
---\
\
\
### Check-ins\
\
Represents gym attendance history.\
\
| Column | Description |\
|------|-------------|\
member_id | member identifier |\
date | check-in date |\
hour | visit hour |\
\
This dataset captures **behavioral engagement patterns**.\
\
\
---\
\
\
### Payments\
\
Contains membership payment transactions.\
\
| Column | Description |\
|------|-------------|\
member_id | member identifier |\
date | payment date |\
amount | payment value |\
plan_type | membership plan |\
\
This dataset is used to calculate **customer lifetime value (CLV)**.\
\
\
---\
\
\
# Exploratory Data Analysis\
\
The project analyzes several behavioral patterns.\
\
Key analyses include:\
\
\'95 age distribution  \
\'95 gender composition  \
\'95 membership plan distribution  \
\'95 training frequency  \
\'95 churn rate analysis  \
\'95 engagement patterns  \
\
Example insight:\
\
> Members who churn tend to visit the gym significantly less frequently than active members.\
\
This indicates that declining engagement is a strong indicator of churn risk.\
\
\
---\
\
\
# Feature Engineering\
\
Raw operational data is transformed into behavioral metrics.\
\
Key engineered features include:\
\
| Feature | Description |\
|------|-------------|\
avg_weekly_visits | normalized training frequency |\
training_consistency | regularity of attendance |\
visit_trend | change in recent activity |\
engagement_decay | decline in engagement |\
days_since_last_visit | recency of activity |\
lifetime_value | total revenue generated |\
\
These features capture both **long-term engagement** and **recent behavioral changes**.\
\
\
---\
\
\
# Machine Learning Model\
\
The churn prediction model is trained using a **Gradient Boosting Classifier**.\
\
### Features used\
\
\pard\pardeftab720\sa240\partightenfactor0

\f1 \cf0 \expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 age\
membership_days\
total_checkins\
avg_weekly_visits\
training_consistency\
lifetime_valueage\
\
\pard\tx720\tx1440\tx2160\tx2880\tx3600\tx4320\tx5040\tx5760\tx6480\tx7200\tx7920\tx8640\pardirnatural\partightenfactor0

\f0 \cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 ---\
\

\f1 \expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 \
\pard\pardeftab720\sa240\partightenfactor0
\cf0 ### Model evaluation\
| Metric | Score |\
|------|------|\
Accuracy | ~0.85 |\
ROC-AUC | ~0.92 |\
The model demonstrates strong ability to distinguish between active members and those at risk of churn.\
\
---\
\
# Model Explainability\
\
SHAP values are used to interpret model predictions.\
\
Key drivers of churn:\
1\uc0\u65039 \u8419  Average weekly visits  \
2\uc0\u65039 \u8419  Training consistency  \
3\uc0\u65039 \u8419  Membership duration  \
Results confirm that **behavioral engagement is the strongest predictor of churn**.\
\
---\
\
# Business Impact\
The model enables the gym to proactively identify members at risk of canceling.\
\
Potential applications:\
\
\'95 targeted retention campaigns  \
\'95 engagement reminders  \
\'95 personalized training programs  \
\'95 promotional offers  \
\
By focusing retention efforts on high-risk members, the gym can reduce churn and increase customer lifetime value.\
\
---\
\
# Technologies Used\
Python  \
Pandas  \
NumPy  \
Matplotlib  \
Seaborn  \
Scikit-Learn  \
SHAP  \
\
---\
\
# How to Run the Project\
1\uc0\u65039 \u8419  Generate the synthetic dataset\
run dataBase.ipynb\
\
2\uc0\u65039 \u8419  Run the analysis notebook\
run analysisGym.ipynb\
\
The notebook performs:\
\
\'95 exploratory analysis  \
\'95 feature engineering  \
\'95 churn prediction modeling  \
\'95 model explainability  \
\
---\
\
# Future Improvements\
\
Possible next steps for the project:\
\
\'95 cross-validation for model robustness  \
\'95 hyperparameter tuning  \
\'95 comparison with additional algorithms  \
\'95 retention cohort analysis  \
\'95 deployment with Streamlit dashboard  \
\
---\
\
# Author\
Emerson Antonio da Silva\
Data Science project developed as a portfolio case study focused on churn prediction and behavioral analytics.\
\
\pard\pardeftab720\partightenfactor0

\f0 \cf0 \kerning1\expnd0\expndtw0 \outl0\strokewidth0 \
}