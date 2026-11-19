# Financial Analytics & Risk Reporting System

### Lending Portfolio Analysis | Credit Risk Prediction | Financial Reporting

An end-to-end financial analytics project that combines Python, SQL, Machine Learning and interactive dashboards to analyse loan portfolio performance and identify potential credit risks.

---

## Project Overview

The Financial Analytics & Risk Reporting System analyses LendingClub loan data to understand portfolio performance, evaluate borrower credit risk and generate actionable business insights.

The project includes data cleaning, SQL-based analysis, machine learning classification models and an interactive financial risk dashboard.

## Objectives

- Analyse loan portfolio performance.
- Identify high-risk borrower segments.
- Calculate default rates across credit grades.
- Monitor monthly loan portfolio trends.
- Develop machine learning models for credit risk prediction.
- Generate visual reports to support financial decision-making.

## Technology Stack

| Technology | Purpose |

| Python | Data processing and analysis |
| Pandas & NumPy | Data cleaning and manipulation |
| Matplotlib | Data visualization |
| Plotly | Interactive dashboard |
| Scikit-learn | Machine learning |
| MySQL | Financial data storage and SQL analysis |
| Jupyter Notebook | Development environment |

## Project Architecture

1. Data Collection – LendingClub loan dataset.
2. Data Preparation – Cleaning, handling missing values and selecting features.
3. Database Management – Loading loan records into MySQL.
4. SQL Analytics – Portfolio summaries and credit-grade risk analysis.
5. Machine Learning – Logistic Regression and Random Forest.
6. Reporting – Portfolio KPIs and risk analysis.
7. Dashboard – Interactive financial risk visualizations.

## Dataset Information

- Source: LendingClub loan dataset.
- Records analysed: 100,000.
- Original columns available: 151.
- Resolved loan records used for modelling: 87,892.
- Reporting period: October–December 2015.

**Target variable:**
- 0 – Fully Paid
- 1 – Charged Off / Default

Loans with unresolved outcomes were excluded from model training.

## Key Portfolio Findings

| Metric | Result |
|---|---:|
| Total Loans | 100,000 |
| Total Loan Amount | $1.506 Billion |
| Average Loan Amount | $15,055.86 |
| Resolved Loans | 87,892 |
| Default Loans | 17,604 |
| Default Rate | 20.03% |

### Credit Grade Risk

Default rates increased as credit grades moved from A to G.

- Grade A: 5.32%
- Grade B: 13.20%
- Grade C: 23.70%
- Grade D: 34.48%
- Grade E: 43.84%
- Grade F: 52.81%
- Grade G: 59.05%

Grade G showed approximately 11 times the default rate of Grade A.

### Monthly Portfolio Trends

| Month | Loans | Default Rate |
|---|---:|---:|
| October 2015 | 16,133 | 18.34% |
| November 2015 | 32,756 | 19.87% |
| December 2015 | 39,003 | 20.86% |

The observed default rate increased across the three loan-issue cohorts.

## Machine Learning Models

Two classification algorithms were developed and evaluated.

| Evaluation Metric | Logistic Regression | Random Forest |
|---|---:|---:|
| Accuracy | 66.01% | 67.86% |
| Precision | 34.33% | 35.32% |
| Recall | 68.91% | 65.01% |
| F1 Score | 45.82% | 45.77% |
| ROC-AUC | 73.69% | 73.46% |

**Selected Model: Logistic Regression**

Logistic Regression was selected as the primary model because it achieved slightly higher recall, F1 score and ROC-AUC at the common 0.50 classification threshold.

Random Forest was retained as a comparison model.

## Interactive Dashboard

The dashboard includes:

1. Default Rate by Credit Grade.
2. Monthly Default Rate Trend.
3. Monthly Loan Portfolio Amount.
4. Model Performance – ROC-AUC.

It also displays four portfolio KPI cards:
- Total Loans
- Portfolio Value
- Average Loan Amount
- Default Rate

Dashboard file: `reports/financial_risk_dashboard.html`

## Business Recommendations

- Strengthen risk assessment for higher-risk credit grades.
- Monitor borrower repayment behaviour.
- Use predictive modelling to support credit risk assessment.
- Review portfolio performance regularly.
- Evaluate classification thresholds based on business costs.
- Improve models using larger and more recent datasets.

## Project Limitations

- The analysis uses a 100,000-row sample.
- The sample covers only October–December 2015.
- Machine learning results are based on a chronological holdout test.
- The model is a decision-support prototype, not an automated lending decision system.
- This project focuses on loan portfolio and credit risk reporting rather than actual corporate profit-and-loss or balance-sheet reporting.

## Future Scope

- Power BI or Qlik Sense integration.
- Automated reporting using Power Automate.
- Model optimization and hyperparameter tuning.
- Larger historical dataset analysis.
- Deployment through a web-based application.
- Automated monthly risk reports.

## Repository Structure

```text
Financial_Analytics_Risk_System/
│
├── README.md
├── notebooks/
├── data/
├── models/
├── reports/
└── docs/
    └── Project_Report.md
```

## Author

**Parth Manohar Kairamkonda**

Financial Analytics | Data Science | Credit Risk Analysis

GitHub: [parthkairamkonda0044-web](https://github.com/parthkairamkonda0044-web)

---

*Developed as a Financial Analytics and Risk Reporting project.*