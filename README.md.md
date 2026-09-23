# Bank Loan & Credit Risk Analytics

## 📌 Project Overview

**Bank Loan & Credit Risk Analytics** is an end-to-end Data Analytics project focused on analyzing loan applications, approval performance, borrower characteristics, loan amounts, and credit-risk patterns.

The project uses **Python/Pandas for data preparation and exploratory analysis, SQL for business analysis, and Power BI for interactive dashboard reporting**.

The final Power BI report contains three analytical pages:

1. **Overview**
2. **Default & Risk Analysis**
3. **Application & Customer Analysis**

This project demonstrates practical skills relevant to **Data Analyst, Banking Analyst, Credit Risk Analyst, MIS Analyst, and Business Analyst** roles.

---

## 🎯 Business Problem

Banks and lending organizations need a consolidated view of their loan application pipeline and credit-risk profile.

The analysis helps answer questions such as:

- How many loan applications were received?
- How many applications were approved, pending, or rejected?
- What is the approval rate?
- What is the default rate?
- Which age and income groups have the highest application volumes?
- How does credit score relate to default rate?
- How does debt-to-income behavior relate to default risk?
- Which employment groups show higher default rates?
- How are loan amounts distributed across income and risk categories?
- Which loan durations are most frequently selected?

---

## 🎯 Project Objectives

- Profile and clean the loan application dataset using Python/Pandas.
- Perform exploratory data analysis.
- Use SQL to answer business and credit-risk questions.
- Analyze approval, rejection, pending, and default patterns.
- Analyze borrower demographics and financial characteristics.
- Create risk segments using credit score, income, debt-to-income and loan-risk categories.
- Build a Power BI data model and dedicated DateTable.
- Create DAX measures for important KPIs.
- Build an interactive three-page Power BI dashboard.
- Generate business insights and management recommendations.

---

## 🗂️ Dataset

The project uses a **20,000-record banking loan application dataset with 48 fields**.

### Main Data Areas

| Area | Example Fields |
|---|---|
| Application | ApplicationDate, LoanApproved, ApplicationStatus |
| Customer | Age, EducationLevel, MaritalStatus, NumberOfDependents |
| Income & Employment | AnnualIncome, MonthlyIncome, EmploymentStatus, JobTenure |
| Credit Profile | CreditScore, PreviousLoanDefaults, BankruptcyHistory, PaymentHistory |
| Loan | LoanAmount, LoanDuration, LoanPurpose, InterestRate |
| Financial Position | SavingsAccountBalance, CheckingAccountBalance, TotalAssets, TotalLiabilities, NetWorth |
| Debt | MonthlyDebtPayments, DebtToIncomeRatio, TotalDebtToIncomeRatio |
| Risk | RiskScore, LoanRiskCategory, DefaultFlag |
| Derived Segments | Income_Group, Age_Group, Credit_Score_Group, Debt_Income_Category, Loan_Amount_Group |

---

## 🛠️ Technology Stack

| Tool | Purpose |
|---|---|
| **Python / Pandas** | Data cleaning, profiling, transformation and exploratory analysis |
| **SQL / MySQL** | Business queries, KPI calculations and risk analysis |
| **Power BI** | Data modeling, DAX, visualization and interactive dashboard |
| **Power Query** | Data preparation inside Power BI |
| **GitHub** | Project version control and portfolio presentation |

---

# 🔹 Project Workflow

```text
Raw Banking Dataset
        ↓
Python / Pandas
        ↓
Data Cleaning & EDA
        ↓
SQL Business Analysis
        ↓
Power BI Data Modeling
        ↓
DAX Measures
        ↓
Interactive Dashboard
        ↓
Business Insights & Recommendations
```

---

# 🐍 Python / Pandas Analysis

Python was used as the primary data-preparation and exploratory-analysis layer.

### Activities performed

- Dataset structure inspection
- Data-type validation
- Missing-value checks
- Duplicate checks
- Date validation
- Categorical-value standardization
- Numerical-field validation
- Customer and loan segmentation
- Exploratory analysis
- Preparation of analysis-ready data

### Main analytical segments

- Age groups
- Income groups
- Credit-score groups
- Loan-amount groups
- Debt-to-income categories
- Loan-risk categories
- Employment status
- Homeownership status
- Loan purpose
- Loan duration

---

# 🗄️ SQL Analysis

SQL was used to answer business questions from the cleaned banking dataset.

### SQL analysis included

- Total loan applications
- Approved applications
- Pending applications
- Rejected applications
- Approval rate
- Default rate
- Applications by age group
- Applications by income group
- Applications by credit-score group
- Applications by loan duration
- Applications by employment status
- Applications by homeownership status
- Default rate by credit-score group
- Default rate by income group
- Default rate by employment status
- Default rate by loan purpose
- Default rate by debt-to-income category
- Loan amount by income group
- Loan amount by risk category

---

# 📊 Power BI Data Model

Power BI was used for the interactive BI layer.

A dedicated **DateTable** was created and connected to the loan application date.

### DateTable fields

- Date
- Year
- Month Number
- Month Name
- Year Month

### Main model

```text
DateTable
    │
    └──── ApplicationDate
              │
              ▼
      Banking_Cleaned
              │
       ┌──────┼────────┐
       ▼      ▼        ▼
   Customer  Loan     Risk
   Segments  Fields   Fields
```

The model supports filtering and analysis by date, loan purpose, employment status, and other analytical segments.

---

# 📐 Important DAX Measures

### Total Applications

```DAX
Total Applications =
COUNTROWS(Banking_Cleaned)
```

### Total Loan Amount

```DAX
Total Loan Amount =
SUM(Banking_Cleaned[LoanAmount])
```

### Approved Loans

```DAX
Approved Loans =
CALCULATE(
    [Total Applications],
    Banking_Cleaned[LoanApproved] = 1
)
```

### Approval Rate

```DAX
Approval Rate =
DIVIDE(
    [Approved Loans],
    [Total Applications],
    0
)
```

### Default Rate

```DAX
Default Rate =
DIVIDE(
    SUM(Banking_Cleaned[DefaultFlag]),
    [Total Applications],
    0
)
```

> Note: The exact DAX syntax may be adjusted depending on whether `LoanApproved` and `DefaultFlag` are stored as numeric or Boolean fields in the final Power BI model.

---

# 📈 Power BI Dashboard

## Page 1 — Overview

The Overview page provides a high-level view of the loan application portfolio.

### KPI Cards

- **Total Applications:** 20K
- **Total Loan Amount:** 498M
- **Approved Loans:** 5K
- **Default Rate:** 10%
- **Approval Rate:** 24%

### Visuals

- Application Status
- Applications by Age Group
- Loan Amount by Income Group
- Applications by Loan Duration
- Applications by Credit Score Group
- Applications by Homeownership Status
- Loan Amount by Risk Category

### Filters

- Date
- Loan Purpose
- Employment Status

---

## Page 2 — Default & Risk Analysis

This page focuses on credit-risk and default behavior.

### Visuals

- Default Rate by Credit Score Group
- Default Rate by Income Group
- Default Rate by Loan Purpose
- Default Rate by Employment Status
- Default Rate by Debt/Income Category
- Applications by Loan Risk Category

### Dashboard Results

| Analysis | Result |
|---|---:|
| Poor Credit Score Default Rate | 18% |
| Fair Credit Score Default Rate | 12% |
| Good Credit Score Default Rate | 7% |
| Excellent Credit Score Default Rate | 3% |
| Low Income Default Rate | 15% |
| Medium Income Default Rate | 8% |
| High Income Default Rate | 4% |
| Employed Default Rate | 8% |
| Self-Employed Default Rate | 12% |
| Unemployed Default Rate | 20% |
| Low Debt/Income Default Rate | 6% |
| Medium Debt/Income Default Rate | 11% |
| High Debt/Income Default Rate | 18% |

---

## Page 3 — Application & Customer Analysis

This page explores application volume and borrower characteristics.

### Visuals

- Applications by Income Group
- Applications by Age Group
- Loan Amount by Income Group
- Applications by Loan Duration
- Applications by Credit Score Group
- Applications by Homeownership Status
- Loan Risk Category vs Loan Amount

### Key displayed results

- Low Income Applications: **6.8K**
- Medium Income Applications: **7.2K**
- High Income Applications: **5.4K**
- Mortgage Applications: **8.4K**
- Rent Applications: **6.8K**
- Own Applications: **3.2K**
- Other Homeownership: **1.6K**

---

# 📌 Key Results

| KPI | Result |
|---|---:|
| Total Applications | 20,000 |
| Total Loan Amount | 498M |
| Approved Loans | 5,000 |
| Pending Applications | 12,000 |
| Rejected Applications | 3,000 |
| Approval Rate | 24% |
| Default Rate | 10% |
| Low Risk | 62% |
| Medium Risk | 26% |
| High Risk | 12% |

---

# 💡 Business Insights

### 1. Application Pipeline

Pending applications represent the largest application-status group at approximately **12K**, indicating a substantial open application pipeline.

### 2. Age Segment

The **26–35 age group** has the highest application volume at approximately **5.2K applications**.

### 3. Income and Loan Amount

The **medium-income group** has the highest aggregate loan amount at approximately **0.42bn**, followed by low income at **0.38bn** and high income at **0.32bn**.

### 4. Credit Risk

The displayed default rate is highest for the **Poor credit-score group (18%)** and lowest for the **Excellent group (3%)**.

### 5. Employment Risk

The displayed default rate is **20% for Unemployed applicants**, compared with **12% for Self-Employed** and **8% for Employed** applicants.

### 6. Debt-to-Income Risk

Default rate increases across the displayed debt/income categories:

**Low: 6% → Medium: 11% → High: 18%**

### 7. Loan Risk Distribution

The dashboard shows:

- Low Risk: **62%**
- Medium Risk: **26%**
- High Risk: **12%**

---

# 🎯 Management Recommendations

- Monitor the high pending-application volume and investigate processing bottlenecks.
- Use credit-score and debt-to-income segmentation for regular credit-risk monitoring.
- Review higher-default segments such as poor credit-score and high debt-to-income groups.
- Analyze medium-income borrowers because this segment has the highest aggregate loan amount in the dashboard.
- Monitor loan demand by duration, particularly the 24-month and 36-month categories.
- Investigate loan-purpose categories with higher displayed default rates.
- Use Power BI slicers during management reviews to investigate changes by date, loan purpose and employment status.

---

# 📚 Skills Demonstrated

### Python

- Python
- Pandas
- Data Cleaning
- Data Profiling
- Data Transformation
- Exploratory Data Analysis
- Segmentation

### SQL

- SELECT
- WHERE
- GROUP BY
- CASE
- Aggregate Functions
- KPI Calculations
- Business Analysis
- Risk Analysis

### Power BI

- Power Query
- Data Modeling
- Relationships
- DateTable
- DAX
- KPI Cards
- Bar Charts
- Donut Charts
- Slicers
- Interactive Dashboard

### Business Analytics

- Loan Application Analysis
- Approval Analysis
- Credit Risk Analysis
- Default Analysis
- Customer Segmentation
- Financial Risk Analysis
- Management Reporting

---

# 📁 GitHub Repository Structure

```text
Bank_Loan_Credit_Risk_Analytics/
│
├── README.md
│
├── Data/
│   ├── banking_data.csv
│   └── Banking_Cleaned.csv
│
├── Python/
│   └── Banking_Data_Analytics.ipynb
│
├── SQL/
│   └── Banking_Loan_Risk_Analysis.sql
│
├── PowerBI/
│   └── Bank_Loan_Credit_Risk_Analytics.pbix
│
├── Documentation/
│   └── Bank_Loan_Credit_Risk_Analytics_Report.docx
│
└── Screenshots/
    ├── Overview.png
    ├── Default_Risk_Analysis.png
    └── Application_Customer_Analysis.png
```

---

# 🖼️ Dashboard Preview

Add your three Power BI dashboard screenshots inside the `Screenshots` folder and display them in this section.

Example:

```markdown
## Dashboard Preview

### Overview
![Overview Dashboard](Screenshots/Overview.png)

### Default & Risk Analysis
![Default & Risk Analysis](Screenshots/Default_Risk_Analysis.png)

### Application & Customer Analysis
![Application & Customer Analysis](Screenshots/Application_Customer_Analysis.png)
```

---

# 📄 Project Documentation

Detailed project documentation is available in the `Documentation` folder.

The documentation covers:

- Executive Summary
- Business Problem
- Objectives
- Dataset
- Data Cleaning
- Python Analysis
- SQL Analysis
- Power BI Model
- DAX Measures
- Dashboard Pages
- Key Results
- Business Insights
- Recommendations
- Skills Demonstrated

---

# 🏁 Conclusion

This project demonstrates a complete banking analytics workflow from raw loan application data through **Python/Pandas data preparation, SQL business analysis and Power BI dashboard development**.

The final dashboard converts loan application and borrower data into measurable KPIs, customer segments and credit-risk insights, demonstrating the ability to translate raw financial data into business-oriented analytics.
