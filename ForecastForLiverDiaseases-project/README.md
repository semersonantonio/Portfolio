## Liver Disease Prediction  
### Machine Learning Classification Project

#### Overview
This project aims to predict the likelihood of liver disease in patients based on clinical and laboratory attributes. It includes data preprocessing, exploratory data analysis (EDA), feature engineering, model training, hyperparameter optimization, and evaluation of multiple classification algorithms. This work was developed as part of my Data Science learning journey and demonstrates my ability to build end-to-end machine learning solutions.

#### Objectives
- Explore the dataset to identify patterns, trends, and correlations  
- Preprocess the data (cleaning, encoding, scaling, imbalance correction)  
- Train and compare several machine learning classification models  
- Evaluate performance using metrics such as ROC-AUC, accuracy, and confusion matrix  
- Identify the most relevant features for prediction  
- Use the trained model to predict liver disease for a new patient  

#### Dataset
The dataset contains clinical information such as:
- Age  
- Gender  
- Bilirubin levels  
- Enzyme measurements (AST, ALT, etc.)  
- Protein levels  
- Target variable indicating liver disease
If the dataset cannot be uploaded, instructions will be provided for downloading it or replicating the analysis.

#### Technologies and Tools
- Python  
- Pandas  
- NumPy  
- Matplotlib & Seaborn  
- Scikit-learn  
- SMOTE (imbalanced-learn)  
- Joblib  
- Jupyter Notebook  

#### Machine Learning Models Tested
The following models were trained and evaluated:
- Logistic Regression (GridSearchCV)  
- Random Forest (RandomizedSearchCV)  
- K-Nearest Neighbors (KNN)  
- Decision Tree  
- Support Vector Machine (SVM)  

Each model was assessed using:
- Accuracy  
- ROC-AUC  
- Confusion Matrix  
- ROC Curve  
- Feature Importance (when applicable)
A comparison table (df_modelos) summarizes the results.

#### Key Insights
- Features such as bilirubin levels, liver enzymes, and protein ratios showed strong predictive relevance.  
- SMOTE improved model performance by balancing the dataset.  
- Random Forest and SVM demonstrated competitive results across multiple metrics.

#### Prediction for a New Patient
The project includes an example that predicts liver disease probability for a new patient based on clinical measurements.  This demonstrates how the model can be applied in real-life use cases.

#### How to Run the Project
##### 1. Clone the repository
```
git clone https://github.com/YOUR-USER/liver-disease-prediction
```

##### 2. Run the notebook
```
jupyter notebook notebooks/LiverDiseasePrediction.ipynb
```

#### Future Improvements
- Implement SHAP values for deeper explainability  
- Add cross-validation pipelines  
- Deploy a web app using Streamlit  
- Compare with additional algorithms  

#### About Me
I am a Data Science student based in Madrid, focused on machine learning, analytics, and building data-driven solutions.  
Always learning, improving, and working on new projects.

#### Contact
LinkedIn: https://www.linkedin.com/in/semersonantonio/ 
