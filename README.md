# 🏦 Bankruptcy Prediction using Machine Learning
### 📉 Predicting Company Financial Health 

---

## 💡 What Problem Are We Solving?

**Problem:** Can we predict if a company will go bankrupt?  

**Why It's Important:**
- 💰 Investors need to know if companies are risky investments  
- 🏦 Banks want to avoid lending to failing companies  
- 👷 Early warning can save jobs and prevent financial losses  
- 📊 Helps in making informed business decisions  

**🎯 Goal:** Build a machine learning model to predict bankruptcy with high accuracy using **18 financial indicators**

---

## 🧩 Dataset Overview

**Training Dataset:**
- 62,789 companies analyzed  
- 58,586 alive companies (93.3%)  
- 4,203 failed companies (6.7%)

**Test Dataset:**
- 15,893 companies to predict  

**Features – 18 Financial Variables:**
X1: Current Assets, X2: Cost of Goods Sold, X3: Depreciation & Amortization, X4: EBITDA, X5: Inventory,  
X6: Net Income, X7: Total Receivables, X8: Market Value, X9: Net Sales, X10: Total Assets,  
X11: Total Long-Term Debt, X12: EBIT, X13: Gross Profit, X14: Total Current Liabilities,  
X15: Retained Earnings, X16: Total Revenue, X17: Total Liabilities, X18: Total Operating Expenses  

---

## ⚖️ The Challenge – Imbalanced Data

**The Problem:**  
- 93% of companies are alive  
- Only 7% failed  
- Model might predict everyone as alive and still achieve 93% accuracy — useless in real life  

**Our Solution – SMOTE Technique:**  
- **SMOTE** = Synthetic Minority Over-sampling Technique  
- Generates synthetic examples of failed companies  
- Balances the dataset for better learning  

**📊 Before vs After SMOTE:**
| Status | Count Before | Count After |
|--------|--------------|-------------|
| Alive  | 58,586 | 58,586 |
| Failed | 4,203  | 58,586 |

✅ *Perfectly Balanced for Training*

---

## 🔄 Data Preparation Pipeline

1. **Load Data**  
   - Read CSV files and verified data quality  

2. **Feature Selection**  
   - Selected 18 key financial indicators (X1–X18)  

3. **Encode Target Variable**  
   - Alive → 0  
   - Failed → 1  

4. **Feature Scaling**  
   - Used `StandardScaler` to normalize all numerical features  

5. **Balance Dataset**  
   - Applied **SMOTE** to ensure equal class representation  

---

## 🤖 Models We Tested

| Model | Description | Accuracy | Verdict |
|--------|--------------|-----------|-----------|
| **Logistic Regression** | Simple linear baseline | 38% | ❌ Poor |
| **XGBoost** | Gradient boosting algorithm | 87.75% | ✅ Good |
| **Random Forest** | Ensemble of decision trees | **93.21%** | 🏆 **Winner** |

---

## 🌲 Why Random Forest Won

**How It Works:**  
- Builds 100+ decision trees on random subsets of data  
- Each tree gives a prediction ("Alive" or "Failed")  
- Final result is decided by **majority vote**

**Advantages:**  
✅ Less overfitting  
✅ Handles non-linear data  
✅ Provides feature importance  
✅ Robust and stable  

---

## 📈 Model Performance Metrics

| Metric | Score | Meaning |
|--------|--------|----------|
| **Accuracy** | 93.21% | 93 out of 100 predictions correct |
| **Precision** | 92.29% | When model predicts “failed,” it’s right 92% of the time |
| **Recall** | 94.29% | Catches 94% of actual bankruptcies |
| **F1-Score** | 93.18% | Excellent balance between precision and recall |

💬 *Conclusion: Reliable early warning model for real-world bankruptcy prediction.*

---

## 🔁 Cross-Validation Results

| Test Split | Accuracy |
|-------------|-----------|
| Fold 1 | 87.31% |
| Fold 2 | 94.90% |
| Fold 3 | 95.17% |
| Fold 4 | 94.52% |
| Fold 5 | 94.14% |

**Average Accuracy:** 93.21%  
**Standard Deviation:** 2.97%  
✅ *Stable and production-ready model.*

---

## 💰 Top 10 Most Important Financial Features

| Rank | Feature | Description |
|------|----------|-------------|
| 1 | **Net Income (X6)** | Strongest bankruptcy indicator |
| 2 | **Retained Earnings (X15)** | Long-term profit stability |
| 3 | **Total Assets (X10)** | Company’s size & resources |
| 4 | **EBIT (X12)** | Core operational profitability |
| 5 | **Total Liabilities (X17)** | Debt burden risk |
| 6 | **Total Revenue (X16)** | Growth potential |
| 7 | **EBITDA (X4)** | Cash generation strength |
| 8 | **Gross Profit (X13)** | Profitability ratio |
| 9 | **Long-Term Debt (X11)** | Debt obligations |
| 10 | **Current Liabilities (X14)** | Short-term liquidity risk |

💡 *Profitability and debt levels are the strongest bankruptcy predictors.*

---

## 🧾 Predictions on Test Data

**Total Companies Tested:** 15,893  

| Prediction | Count | Percentage |
|-------------|--------|-------------|
| Alive | 14,787 | 93.0% |
| Failed | 1,106 | 7.0% |

🧠 *Model successfully identified high-risk companies aligned with historical financial crises (e.g., 2008).*

---

## 🧮 Final Model Comparison

| Model | Accuracy | Precision | Recall | Status |
|--------|-----------|-----------|----------|----------|
| Logistic Regression | 38.00% | 8% | 77% | ❌ Poor |
| XGBoost | 87.75% | 85.85% | 90.30% | ✅ Good |
| **Random Forest** | **93.21%** | **92.29%** | **94.29%** | 🏆 **Best Model** |

**Winner: Random Forest**  
✔ Highest accuracy  
✔ Best balance of precision & recall  
✔ Most reliable & stable results  

---

## 🧠 Tools & Technologies

<img src="https://img.shields.io/badge/-Python-3776AB?logo=python&logoColor=white&style=flat">&nbsp;
<img src="https://img.shields.io/badge/-Google%20Colab-F9AB00?logo=googlecolab&logoColor=white&style=flat">&nbsp;
<img src="https://img.shields.io/badge/-Pandas-150458?logo=pandas&logoColor=white&style=flat">&nbsp;
<img src="https://img.shields.io/badge/-NumPy-013243?logo=numpy&logoColor=white&style=flat">&nbsp;
<img src="https://img.shields.io/badge/-Scikit--Learn-F7931E?logo=scikitlearn&logoColor=white&style=flat">&nbsp;
<img src="https://img.shields.io/badge/-Matplotlib-11557C?logo=plotly&logoColor=white&style=flat">&nbsp;
<img src="https://img.shields.io/badge/-Seaborn-268BD2?logoColor=white&style=flat">&nbsp;
<img src="https://img.shields.io/badge/-XGBoost-EB5E28?logoColor=white&style=flat">&nbsp;
<img src="https://img.shields.io/badge/-Imbalanced--Learn-512DA8?logoColor=white&style=flat">

---

## ⚙️ Implementation Workflow

1. **Data Loading** – Import and verify datasets  
2. **Feature Engineering** – Extract 18 key variables  
3. **Preprocessing** – Encode, scale, and balance data  
4. **Model Training** – Train Random Forest with 100 trees  
5. **Validation** – 5-fold cross-validation  
6. **Prediction** – Generate results on test dataset  
7. **Export** – Save predictions to CSV for deployment  

---

## 💼 Business & Technical Insights

**Business Insights:**
- Net Income & Liabilities are key bankruptcy indicators  
- Debt-to-asset ratio critical for stability  
- Captured 2008 crisis patterns effectively  

**Technical Insights:**
- Ensemble models outperform linear ones  
- SMOTE drastically improved recall  
- Cross-validation proved model stability  
- Feature scaling boosted accuracy  

---

## 🌍 Real-World Applications

🏦 **Banks:** Loan approvals, credit scoring, risk analysis  
📈 **Investors:** Portfolio risk, investment screening  
🏢 **Companies:** Self-assessment, early warnings  
⚖️ **Regulators:** Economic risk monitoring  
💼 **Insurance Firms:** Premium pricing, underwriting  

---

## 🧱 Challenges We Overcame

| Challenge | Solution | Result |
|------------|-----------|---------|
| Imbalanced data | Used SMOTE | Balanced classes |
| Large value ranges | Used StandardScaler | Uniform scaling |
| Overfitting | Cross-validation | Stable results |
| Model confusion | Compared 3 algorithms | Clear best performer |
| Computation time | Parallel processing | Fast training |

---

## 🚀 Future Improvements

- Incorporate **macroeconomic indicators** and **stock data**  
- Add **news sentiment** and **management metrics**  
- Experiment with **LSTM** for time-series predictions  
- Add **Explainability (SHAP values)**  
- Deploy via **Flask/Streamlit** on **AWS/Azure**

---

## 🏁 Project Outcomes

✅ Built AI-powered bankruptcy prediction system  
✅ Achieved **93.21% accuracy** using Random Forest  
✅ Processed **62,789 training** & **15,893 test** companies  
✅ Identified **top financial indicators** of bankruptcy  
✅ Ready for **production deployment**

💬 *With 93% accuracy, this model can help prevent massive financial losses by predicting company failures before they occur.*

---

## 👨‍💻 Author

**Sai Praveen**  
📍 Data Science & Machine Learning Enthusiast  
💬 *“AI is not just predicting numbers — it’s predicting the future of finance.”*  

⭐ *If you found this helpful, give it a star and share it!*
