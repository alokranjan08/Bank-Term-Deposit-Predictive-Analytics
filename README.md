# Bank Term Deposit Predictive Analytics 🏦📈

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![scikit-learn](https://img.shields.io/badge/scikit--learn-latest-orange.svg)
![pandas](https://img.shields.io/badge/pandas-latest-green.svg)
![License](https://img.shields.io/badge/License-MIT-purple.svg)

## 🎯 Project Overview
Banks waste millions on cold calls. This project aims to predict **WHO** to call and **HOW LONG** it will take using the UCI Bank Marketing Dataset (41,000+ records).

The project is structured around 3 core machine learning objectives:
1. **Classification:** Predict whether a customer will subscribe to a term deposit.
2. **Regression:** Estimate the expected duration of a marketing call based on pre-call features.
3. **Time Series Forecasting:** Forecast future monthly subscription rates to help plan campaigns.

## 📂 Project Structure
```text
├── data/
│   ├── BankAdditional.csv        # UCI Dataset (41,188 rows)
│   └── README.md                 
├── notebooks/
│   └── 01_Predictive_Analytics.ipynb  # Main Analysis & Modeling Notebook
├── reports/                      
│   └── BankAnalytics_v2.pptx     # Presentation slides with full methodology & results
├── src/                          # Helper functions (future)
├── models/                       # Serialized machine learning models
├── .gitignore                    
├── requirements.txt              
├── LICENSE                       
└── README.md                     
```

## 🔬 Methodology & Pipeline
1. **Target Encoding & Addressing Imbalance:** Target `y` (11% subscription rate) was encoded and balanced using **SMOTE** (on training data only).
2. **Data Leakage Prevention:** The `duration` feature was strictly excluded from classification models, as call duration is only known *after* a call is completed.
3. **Feature Encoding:** Ordinal variables via `LabelEncoder`, Nominal variables via `One-Hot Encoding`. 
4. **Scaling:** Used `StandardScaler` for distance-based and linear models (LR, NB, SVM).

## 📊 Objective 1: Classification Results
**Goal:** Predict binary subscription outcome (Yes/No).

| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC ⭐ |
|-------|----------|-----------|--------|----------|-----------|
| Logistic Regression | ~79% | 0.75 | 0.72 | 0.73 | 0.84 |
| Naive Bayes | ~74% | 0.70 | 0.68 | 0.69 | 0.80 |
| Decision Tree (max_depth=8) | ~85% | 0.82 | 0.80 | 0.81 | 0.86 |
| **Random Forest (150 trees)** | **~87%** | **0.85** | **0.83** | **0.84** | **0.91** |
| SVM (LinearSVC) | ~80% | 0.77 | 0.74 | 0.75 | 0.85 |

*Note: ROC-AUC is the primary metric due to the highly imbalanced nature of the dataset.*

## ⏱️ Objective 2: Regression
**Goal:** Predict the call duration (seconds) using pre-call features.
- **Linear Regression:** R²: ~0.08 | RMSE: ~195s
- **Decision Tree Regressor (max_depth=8):** R²: ~0.18 | RMSE: ~168s

*Note: Low R² is expected here—call duration is driven by real-time conversation dynamics that pre-call features alone cannot fully capture.*

## 📈 Objective 3: Time Series Forecasting
**Goal:** Forecast the monthly subscription rate to plan future campaigns.
- Model used: **ARIMA(1,1,1)**
- Forecasted 3 future months identifying seasonal peaks in September & October.

## 💡 Key Business Recommendations
1. **Target Seasonal Peaks:** Focus campaigns in May, July & August where historical subscription rates are highest.
2. **Prioritise Key Segments:** Retired & student customers subscribe more—target them first.
3. **Monitor Economic Signals:** Euribor 3-month rate and employment variation rate are top predictors.
4. **Reduce Wasteful Calls:** Use the Random Forest model to filter low-potential customers and cut costs significantly.

## 🚀 How to Run the Project
```bash
git clone https://github.com/alokranjan08/Bank-Term-Deposit-Predictive-Analytics.git
cd Bank-Term-Deposit-Predictive-Analytics
pip install -r requirements.txt
jupyter notebook notebooks/01_Predictive_Analytics.ipynb
```
