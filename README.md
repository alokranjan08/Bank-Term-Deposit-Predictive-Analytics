# Bank Term Deposit Predictive Analytics 🏦📈

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![scikit-learn](https://img.shields.io/badge/scikit--learn-latest-orange.svg)
![pandas](https://img.shields.io/badge/pandas-latest-green.svg)
![License](https://img.shields.io/badge/License-MIT-purple.svg)

## Project Overview
This repository contains a comprehensive data science project focused on **Predictive Analytics for Bank Term Deposits**. The goal of this project is to predict whether a client will subscribe to a term deposit based on direct marketing campaigns (phone calls) of a Portuguese banking institution.

By identifying the key drivers of successful subscriptions, the bank can optimize its marketing strategies, reduce campaign costs, and improve conversion rates.

## 📂 Project Structure

```text
├── data/
│   ├── BankAdditional.csv        # Dataset used for modeling
│   └── README.md                 # Data dictionary & info
├── notebooks/
│   └── 01_Predictive_Analytics.ipynb  # Main Jupyter Notebook (EDA, Preprocessing, Modeling)
├── src/                          # Helper functions and scripts (future iterations)
├── models/                       # Serialized machine learning models (.pkl/.joblib)
├── reports/                      # Generated analysis reports and figures
├── .gitignore                    # Ignored files and folders
├── requirements.txt              # Python dependencies to reproduce the environment
├── LICENSE                       # MIT License
└── README.md                     # Project documentation (You are here)
```

## 📊 Dataset Information
The dataset was obtained from the [UCI Machine Learning Repository: Bank Marketing Dataset](https://archive.ics.uci.edu/dataset/222/bank+marketing). 
It contains client data (age, job, marital status, education), campaign attributes (contact communication type, day, month, duration), and social/economic context attributes (employment variation rate, consumer price index, consumer confidence index, euribor 3 month rate).

## 🧪 Methodology
1. **Exploratory Data Analysis (EDA):** Analyzed feature distributions, checked for missing values, and explored correlations.
2. **Data Preprocessing:** Handled categorical encoding, scaled numerical features, and addressed class imbalance using techniques like SMOTE.
3. **Model Selection & Training:** Tested multiple models including Logistic Regression, Random Forest, and Gradient Boosting Classifiers.
4. **Evaluation:** Evaluated models using precision, recall, F1-score, and ROC-AUC. 

## 🚀 How to Run the Project

1. **Clone the repository:**
   ```bash
   git clone https://github.com/alokranjan08/Bank-Term-Deposit-Predictive-Analytics.git
   cd Bank-Term-Deposit-Predictive-Analytics
   ```

2. **Create a virtual environment (optional but recommended):**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the Jupyter Notebook:**
   ```bash
   jupyter notebook
   ```
   Navigate to `notebooks/01_Predictive_Analytics.ipynb` and run the cells.

## 📈 Key Insights & Results
- **Economic Indicators:** Features like the `euribor3m` (Euribor 3 month rate) and `nr.employed` (number of employees) are strong predictors.
- **Call Duration:** The duration of the last contact is highly correlated with successful subscriptions, although it is typically only known after the call ends.
- **Previous Campaigns:** Success in past marketing campaigns strongly increases the likelihood of a future subscription.

*(More detailed model metrics and visualizations can be found within the notebook!)*

## 📜 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
