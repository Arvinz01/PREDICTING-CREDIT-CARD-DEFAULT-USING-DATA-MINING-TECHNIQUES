# 💳 Credit Card Default Prediction 

A collaborative machine learning project that predicts whether a credit card client will default on their next payment, using the UCI **Default of Credit Card Clients** dataset.

---

## 📌 Project Overview

This project applies the full data science pipeline — from raw data ingestion to model deployment mockup — to solve a real-world binary classification problem in the financial domain. The dataset contains demographic and payment history data for **30,000 credit card clients** in Taiwan.

**Target variable:** `DEFAULT` — whether a client will default on their next payment (1 = Yes, 0 = No)

---

## 👥 Team Structure & Responsibilities

| Member | Role | Deliverables |
|--------|------|--------------|
| **Member 1** | Dataset Understanding & Preprocessing | Cleaned CSV, train/test splits, preprocessing pipeline (`.pkl`) |
| **Member 2** | Exploratory Data Analysis (EDA) | Statistical summaries, distribution plots, correlation heatmap, SMOTE |
| **Member 1** | Model Development & Training | Baseline + tuned models (Logistic Regression, Random Forest, MLP Neural Network) |
| **Member 2** | Model Evaluation & Application Mockup | Performance comparison, Figma app mockup |

---

## 📂 Project Structure

```Predicting Credit Card Default Risk Using Data Mining Techniques
│
├── Code.ipynb                     # Main Jupyter Notebook (all members)
├── default of credit card clients.xls   # Raw dataset (UCI)
├── Report.pdf                     # Final project report
│
└── member1_outputs/
    ├── data_cleaned.csv                 # Cleaned dataset
    ├── X_train.csv                      # Training features
    ├── X_test.csv                       # Test features
    ├── y_train.csv                      # Training labels
    ├── y_test.csv                       # Test labels
    └── preprocessor.pkl                 # Fitted sklearn preprocessor
```

---

## 🔧 Methodology

### 1. Data Preprocessing (Member 1)
- Loaded UCI dataset, renamed columns for consistency (`PAY_0` → `PAY_1`, target → `DEFAULT`)
- Fixed invalid categorical codes in `EDUCATION` (codes 0, 5, 6 → mapped to "Others") and `MARRIAGE` (code 0 → "Others")
- Performed stratified 80/20 train-test split
- Built a `ColumnTransformer` pipeline: `StandardScaler` for numeric features, `OneHotEncoder` for categoricals

### 2. Exploratory Data Analysis (Member 2)
- Class imbalance analysis (default rate ≈ 22%)
- Demographic breakdown (SEX, EDUCATION, MARRIAGE) vs. default rate
- Credit limit and age distributions
- Repayment status trends across 6 months (`PAY_1` to `PAY_6`)
- Bill amount and payment amount trends
- Full correlation heatmap
- Applied **SMOTE** (Synthetic Minority Oversampling Technique) to handle class imbalance for model training

### 3. Model Training (Member 1)
Three models were trained and compared:

| Model | Type |
|-------|------|
| Logistic Regression | Linear baseline |
| Random Forest | Ensemble / non-linear |
| MLP Neural Network | Deep learning |

Each model went through:
- **Baseline training** on SMOTE-resampled data
- **Hyperparameter tuning** via `GridSearchCV` optimizing for **F1-Score**

### 4. Evaluation (Member 2)
Models evaluated on five metrics:
- **Accuracy**
- **Precision**
- **Recall**
- **F1-Score**
- **ROC-AUC**

A Figma application mockup was also developed to demonstrate a potential real-world deployment interface.

---

## 📊 Dataset

- **Source:** [UCI Machine Learning Repository — Default of Credit Card Clients](https://archive.ics.uci.edu/ml/datasets/default+of+credit+card+clients)
- **Records:** 30,000 clients
- **Features:** 23 features including credit limit, demographics, repayment history, bill amounts, and payment amounts
- **Target:** Binary — default payment next month (1 = Yes, 0 = No)

---

## 🛠️ Tech Stack

- **Language:** Python 3
- **Environment:** JupyterLab
- **Libraries:**
  - `pandas`, `numpy` — data manipulation
  - `matplotlib`, `seaborn` — visualization
  - `scikit-learn` — preprocessing, modeling, evaluation
  - `imbalanced-learn` — SMOTE
  - `joblib` — model/pipeline serialization
  - `xlrd` — reading legacy `.xls` files

---

## 🚀 Getting Started

### Prerequisites
```bash
pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn joblib xlrd==2.0.1
```

### Run the Notebook
1. Clone this repository
2. Place `default of credit card clients.xls` in the root directory
3. Open `Code_(P60).ipynb` in JupyterLab or Jupyter Notebook
4. Run all cells sequentially (Member 1 outputs are required by subsequent sections)

---

## 📱 Application Mockup

A UI prototype for a credit default risk assessment tool was designed in Figma:
🔗 [View Application Mockup](https://laurel-food-52616486.figma.site/portfolio)

---


