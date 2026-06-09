## 🫀 CardioRisk ML — Cardiovascular Risk Prediction

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat&logo=python&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.4-F7931E?style=flat&logo=scikit-learn&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-2.0-FF6600?style=flat)
![SMOTE](https://img.shields.io/badge/imbalanced--learn-SMOTE-8A2BE2?style=flat)
![Champion](https://img.shields.io/badge/Champion-Logistic%20Regression%20AUC%200.866-E74C3C?style=flat)
![Status](https://img.shields.io/badge/Status-Complete-2ECC71?style=flat)

---

### Apresentação

[Ver apresentação completa (PPTX)](./presentation/CardioRisk_ML_Presentation.pptx)

#### Vista prévia da apresentação

As principais diapositivas do projecto estão disponíveis como imagens para facilitar uma rápida visualização:

📁 `figures/presentation/`

![Slide 1](figures/presentation/00.jpg)
![Slide 2](figures/presentation/01.jpg)
![Slide 3](figures/presentation/02.jpg)
![Slide 4](figures/presentation/03.jpg)
![Slide 5](figures/presentation/04.jpg)
![Slide 6](figures/presentation/05.jpg)
![Slide 7](figures/presentation/06.jpg)
![Slide 8](figures/presentation/07.jpg)
![Slide 9](figures/presentation/08.jpg)
![Slide 10](figures/presentation/09.jpg)

---

### Introdução

End-to-end machine learning pipeline for **binary classification of cardiovascular risk** in adult patients, built around a synthetic clinical dataset of **10,000 records** calibrated against the Framingham Heart Study and NHANES.

The project answers three clinical questions:

- Which factors most drive cardiovascular risk?
- Can a machine learning model reliably identify at-risk patients preventively?
- What probability threshold maximises clinical utility in a screening context?

---

### ⚙️ Pipeline

| Stage | Detail |
|---|---|
| **Data Generation** | Synthetic dataset, 10,000 patients, calibrated vs Framingham & NHANES |
| **EDA** | Distribution analysis, correlation heatmaps, sex-stratified comparisons |
| **Preprocessing** | Ordinal/one-hot encoding, 8 engineered features, 80/20 split, StandardScaler, SMOTE |
| **Modelling** | 6 algorithms, 5-fold CV, composite scoring (Recall × 0.40 + AUC × 0.40) |
| **Storytelling** | Clinical narrative, threshold analysis, v1→v2 optimisation impact |

**Engineered features:**

| Feature | Clinical rationale |
|---|---|
| `ldl_hdl_ratio` | Atherogenic index — LDL/HDL ratio (ideal < 3.0) |
| `tg_hdl_ratio` | Triglyceride/HDL ratio — insulin resistance proxy (ideal < 2.0) |
| `pulse_pressure` | Systolic − Diastolic BP — arterial stiffness marker (>60 mmHg = risk) |
| `metabolic_score` | NCEP-ATP III criteria count: BMI, triglycerides, HDL, BP, glucose |
| `lifestyle_score` | Composite of physical activity, diet quality, and sleep (0–1) |
| `abdominal_obesity` | Waist flag: ≥102 cm (men) or ≥88 cm (women) |
| `age_x_diabetes` | Age × diabetes — compounding glycaemic risk with ageing |
| `smoking_x_htn` | Smoking × hypertension — atherogenic co-occurrence |

---

### 📊 Results

| Model | Accuracy | Recall | F1 | AUC | Score |
|---|---|---|---|---|---|
| **Logistic Regression ⭐** | **0.792** | **0.747** | **0.743** | **0.866** | **0.759** |
| SVM | 0.792 | 0.738 | 0.741 | 0.856 | 0.751 |
| Gradient Boosting | 0.786 | 0.719 | 0.730 | 0.863 | 0.745 |
| Random Forest | 0.780 | 0.723 | 0.726 | 0.854 | 0.742 |
| XGBoost | 0.792 | 0.706 | 0.732 | 0.865 | 0.741 |
| Decision Tree | 0.750 | 0.672 | 0.684 | 0.791 | 0.691 |

> ⭐ Champion: Logistic Regression — best Recall+AUC in preventive screening context.

**Recommended screening threshold: t = 0.35**

- Recall: **0.863** (~9 in 10 high-risk patients identified)
- Precision: 0.650 (clinically acceptable — missed event >> unnecessary follow-up)

---

### 🚀 How to Run

```bash
pip install -r requirements.txt
jupyter notebook notebooks/01_data_generation.ipynb
```

> All notebooks are seeded (`random_state = 42`) and fully reproducible. Run them in order.
