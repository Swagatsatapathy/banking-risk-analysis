# banking-risk-analysis
This project focuses on risk analytics in the banking sector by analyzing customer data to understand income levels, engagement patterns, and their correlation with potential loan risks. The analysis was performed using **Python (Pandas, Seaborn, Matplotlib)** and **Excel** on a real-world styled dataset of 3000 bank clients.

---

## 📌 Problem Statement

To understand how customer data can be used to reduce financial risk while offering loans. The project explores patterns in income, loan exposure, deposit behaviors, and other attributes to help banks classify risk-prone clients.

---

## 🧰 Tools & Libraries Used

- Python  
  - `pandas`  
  - `numpy`  
  - `matplotlib`  
  - `seaborn`  
  - `warnings`, `datetime`
- Excel (for preliminary inspection and data formatting)
- Jupyter Notebook

---

## 📁 Dataset Overview

The dataset includes information about 3000 clients with the following columns:

- Demographics: `Age`, `Nationality`, `Occupation`, `GenderId`
- Financials: `Estimated Income`, `Credit Card Balance`, `Bank Loans`, `Deposits`, `Savings`
- Risk & Engagement: `Properties Owned`, `Risk Weighting`, `Joined Bank`, `Fee Structure`, `Loyalty Classification`
- Account Types: `Checking`, `Savings`, `Business Lending`, `Foreign Currency`

---

## 🧹 Data Cleaning & Preprocessing

- Converted **"Joined Bank"** dates to calculate **Engagement Days**
- Created **Income Bands** using `pd.cut()`:
  ```python
  bins = [0, 100000, 300000, float('inf')]
  labels = ["Low", "Mid", "High"]
  df["Income Band"] = pd.cut(df["Estimated Income"], bins=bins, labels=labels, right=False)
Handled missing/null values and ensured proper data types

Extracted categorical and numerical features for segmented analysis

📊 Exploratory Data Analysis (EDA)
🔹 Univariate Analysis
Count plots for all categorical features: BRId, Fee Structure, Risk Weighting, etc.

Histograms of numerical columns such as Estimated Income, Bank Loans, and Credit Card Balance

🔹 Bivariate Analysis
Compared features across Nationality and other dimensions using countplot() with hue

🔹 Numerical Analysis
Distribution plots using histplot() with KDE overlays

Heatmap to visualize correlation among continuous features:

sns.heatmap(correlation_matrix, annot=True, cmap='crest', fmt=".2f")
🔍 Key Insights
Mid-income band clients formed the majority (~50%+), followed by Low and then High.

Strong correlations were found between:

Bank Deposits and Checking/Saving/Foreign Accounts

Clients with high balance in one account tend to have high across others.

Risk Weighting is distributed among 5 levels, helping classify clients’ financial behavior patterns.

📂 Project Structure
banking-risk-analysis/
├── data/
│   └── Banking.csv
├── notebooks/
│   └── banking_risk_analysis.ipynb
├── images/
│   └── charts and plots
├── README.md
👨‍💻 Author
Swagat Satapathy
📧 Email: satapathyswagat778@gmail.com
