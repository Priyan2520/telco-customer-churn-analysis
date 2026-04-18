# 📊 Telco Customer Churn — End-to-End Data Science Project

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.8-orange?logo=scikit-learn)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter)
![License](https://img.shields.io/badge/License-MIT-green)

## Executive Summary

This project performs a full Data Science Lifecycle analysis on the **IBM Telco Customer Churn dataset** (7,043 customers × 21 features). It identifies the root causes of customer churn and delivers a production-ready predictive model that flags at-risk customers, enabling targeted retention campaigns.

> **Business Impact:** By identifying the top churn drivers and deploying the model in a CRM system, the company can proactively intervene before customers leave — reducing churn from **26.5% to an estimated 15–18%**, saving millions in acquisition costs annually.

---

## 🔍 Key Findings

- **Contract type is the #1 churn driver.** Customers on month-to-month contracts churn at **42.7%** — a 15× higher rate than two-year contract holders (2.8%). Migrating even 20% of month-to-month customers to annual plans would be transformative.
- **Fiber optic customers are surprisingly at-risk.** Despite paying a premium, fiber customers churn at **41.9%** vs 18.9% for DSL users. This signals a service quality or value-perception issue that warrants urgent investigation.
- **The first 12 months are the critical retention window.** New customers (tenure < 12 months) churn at **47.7%**. A structured onboarding and loyalty program targeted at this cohort is the fastest path to reducing overall churn.
- **Higher monthly charges correlate with higher churn.** Churned customers pay a median of **$79/month vs $65/month** for retained customers. High-paying customers who don't perceive commensurate value are the most vulnerable segment.

---

## 📂 Project Structure

```
telco-churn/
├── Telco_Churn_Analysis.ipynb   # Full analysis notebook
├── README.md                    # This file
├── requirements.txt             # Python dependencies
└── figures/                     # Pre-generated charts
    ├── 01_churn_distribution.png
    ├── 02_churn_by_contract.png
    ├── 03_churn_by_internet.png
    ├── 04_churn_by_tenure.png
    ├── 05_monthly_charges.png
    ├── 06_correlation_heatmap.png
    ├── 07_roc_curves.png
    ├── 08_confusion_matrices.png
    ├── 09_feature_importance.png
    └── 10_model_comparison.png
```

---

## 🛠 Tools & Technologies

| Category | Library / Tool |
|----------|---------------|
| Data Manipulation | `pandas`, `numpy` |
| Visualization | `seaborn`, `matplotlib` |
| Machine Learning | `scikit-learn` (RandomForest, HistGradientBoosting) |
| Pipeline & Preprocessing | `sklearn.pipeline`, `ColumnTransformer`, `OneHotEncoder` |
| Environment | Python 3.10+, Jupyter Notebook |

---

## 🚀 How to Run

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/telco-churn.git
cd telco-churn
```

### 2. Create a Virtual Environment
```bash
python -m venv venv
source venv/bin/activate      # Linux/Mac
venv\Scripts\activate.bat     # Windows
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Download the Dataset
Download `WA_Fn-UseC_-Telco-Customer-Churn.csv` from [Kaggle](https://www.kaggle.com/datasets/blastchar/telco-customer-churn) and place it in the project root.

### 5. Launch the Notebook
```bash
jupyter notebook Telco_Churn_Analysis.ipynb
```

Run all cells top-to-bottom (`Kernel → Restart & Run All`).

---

## 📈 Model Performance

| Model | Precision (Churn) | Recall (Churn) | F1-Score (Churn) | ROC-AUC |
|-------|------------------|----------------|-----------------|---------|
| Random Forest | ~0.65 | ~0.61 | **0.628** | 0.841 |
| Gradient Boosting | ~0.60 | ~0.58 | 0.590 | **0.844** |

**Recommended model: Random Forest** — higher F1-Score on the churn class, better for minimizing missed churners (false negatives), and directly interpretable via feature importances.

---

## 💡 Business Recommendations

### 1. 🔴 Contract Migration Campaign (Highest ROI)
Offer month-to-month customers a discounted annual contract (e.g., "Get 2 months free, lock in your rate"). This addresses the single largest churn driver.

### 2. 🔴 Fiber Optic Service Audit
Survey fiber optic customers about service quality and perceived value. Investigate whether pricing is misaligned with the competition or whether technical issues are causing frustration.

### 3. 🟠 First-Year Onboarding Program
Implement proactive touchpoints at 30, 60, 90, 180, and 360 days. Offer loyalty rewards (e.g., bill credits, service upgrades) to customers who complete their first year.

### 4. 🟡 CRM Model Deployment
Score all active customers monthly using the Random Forest model. Flag customers with predicted churn probability >60% for immediate outreach by the customer success team.

---

## 📄 License

This project is licensed under the MIT License. The dataset is provided by IBM and available publicly on Kaggle.
