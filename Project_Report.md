# FINANCIAL ANALYTICS & RISK REPORTING SYSTEM

**Project Type:** Financial Analytics and Credit Risk Analysis  
**Dataset:** LendingClub Loan Dataset  
**Primary Tools:** Python, MySQL, Machine Learning, Plotly  
**Author:** Parth Manohar Kairamkonda  
**Academic Project Report**

---

# 1. Executive Summary

The Financial Analytics and Risk Reporting System is an end-to-end data analytics project developed to analyse loan portfolio performance and identify potential credit risks.

The project uses LendingClub loan data to examine borrower repayment outcomes, analyse credit grades, calculate default rates and develop machine learning models for credit risk prediction.

Python was used for data cleaning, analysis and machine learning. MySQL was used for database storage and SQL-based reporting. An interactive dashboard was developed using Plotly to present financial KPIs and credit risk insights.

The project demonstrates how financial data analytics and predictive modelling can support better risk monitoring and financial decision-making.

# 2. Problem Statement

Financial institutions need to monitor loan portfolios and identify borrowers who may have a higher probability of default.

Analysing large loan datasets manually can make it difficult to identify risk patterns, monitor portfolio performance and generate timely reports.

This project addresses the problem by developing a data-driven system that combines portfolio analytics, SQL reporting, machine learning and interactive visualisation.

# 3. Project Objectives

- Analyse loan portfolio performance.
- Calculate total loan amounts and average loan values.
- Identify default patterns across credit grades.
- Analyse monthly loan portfolio trends.
- Develop machine learning models for credit risk classification.
- Compare model performance using evaluation metrics.
- Create an interactive financial risk dashboard.
- Generate insights to support financial risk monitoring.

# 4. Dataset Description

**Dataset Source:** LendingClub Loan Dataset

The project uses a sample of 100,000 loan records.

| Dataset Detail | Description |
|---|---|
| Total records | 100,000 |
| Available columns | 151 |
| Resolved loan records | 87,892 |
| Reporting period | October–December 2015 |
| Target variable | default_flag |

### Target Variable

- 0 – Fully Paid
- 1 – Charged Off or Default

Loans with unresolved statuses, such as Current and Late, were excluded from model training and default-rate calculations.

# 5. Technologies Used

| Technology | Application |
|---|---|
| Python | Data analysis and modelling |
| Pandas | Data cleaning and manipulation |
| NumPy | Numerical operations |
| Matplotlib | Data visualisation |
| Plotly | Interactive dashboard |
| Scikit-learn | Machine learning |
| MySQL | Database management |
| SQLAlchemy | Python–MySQL connectivity |
| Jupyter Notebook | Development environment |

# 6. Project Methodology

The project followed these stages:

### 6.1 Data Collection

The LendingClub dataset was downloaded and imported into the Jupyter Notebook environment using Pandas.

A sample of 100,000 records was selected for analysis.

### 6.2 Data Cleaning and Preparation

The dataset was examined for:

- Missing values
- Duplicate records
- Incorrect data types
- Unnecessary columns
- Invalid numerical values

Relevant numerical and categorical features were selected for further analysis.

Missing numerical values were handled using median imputation, while categorical missing values were handled using the most frequent value.

### 6.3 Database Management

A MySQL database named `financial_risk_db` was created.

The loan records were loaded into a table named `loans`.

SQL queries were used to analyse:

- Total loan count
- Total loan amount
- Average loan amount
- Loan status distribution
- Default rates by credit grade

### 6.4 Exploratory Data Analysis

The analysis focused on understanding the relationship between credit grades and repayment outcomes.

Credit grades A through G were compared using default rates.

Monthly loan issue cohorts were also analysed to understand changes in loan volume and eventual default outcomes.

# 7. Portfolio Analysis Results

The following results were obtained from the 100,000-record sample.

| Metric | Result |
|---|---:|
| Total Loans | 100,000 |
| Total Loan Amount | $1,505,586,100 |
| Average Loan Amount | $15,055.86 |
| Resolved Loans | 87,892 |
| Default Loans | 17,604 |
| Overall Default Rate | 20.03% |

The default rate was calculated using resolved loans only.

### 7.1 Default Rate by Credit Grade

| Credit Grade | Default Rate |
|---|---:|
| A | 5.32% |
| B | 13.20% |
| C | 23.70% |
| D | 34.48% |
| E | 43.84% |
| F | 52.81% |
| G | 59.05% |

**Finding:**

Default rates increased consistently from Grade A to Grade G.

Grade G borrowers had approximately 11 times the default rate of Grade A borrowers in the analysed sample.

This indicates a strong relationship between credit grade and observed repayment risk.

### 7.2 Monthly Portfolio Analysis

| Month | Total Loans | Loan Amount | Default Loans | Default Rate |
|---|---:|---:|---:|---:|
| October 2015 | 16,133 | $230,259,375 | 2,959 | 18.34% |
| November 2015 | 32,756 | $473,026,500 | 6,508 | 19.87% |
| December 2015 | 39,003 | $560,278,125 | 8,137 | 20.86% |

**Findings:**

- December had the highest loan volume.
- December also had the highest observed default rate.
- The default rate increased by approximately 2.52 percentage points between October and December.

These figures represent eventual repayment outcomes grouped by loan issue month, not defaults occurring within those calendar months.

# 8. Machine Learning Implementation

Two classification algorithms were developed to predict potential loan defaults.

### 8.1 Selected Features

The model used borrower and loan characteristics, including:

- Loan amount
- Loan term
- Interest rate
- Installment
- Credit grade
- Sub-grade
- Employment length
- Home ownership
- Annual income
- Verification status
- Loan purpose
- Debt-to-income ratio
- Delinquency history
- FICO score range
- Open credit accounts
- Public records
- Revolving balance
- Revolving utilisation
- Total credit accounts

### 8.2 Data Splitting

A chronological train-test split was used.

- Training data: October and November 2015.
- Testing data: December 2015.

The test set contained 39,003 records.

This approach evaluates the models on a later loan-issue cohort than the training data.

### 8.3 Logistic Regression

Logistic Regression was developed as the primary classification model.

The preprocessing pipeline included:

- Median imputation for numerical features.
- Standard scaling for numerical features.
- Most-frequent imputation for categorical features.
- One-hot encoding for categorical features.
- Class balancing during model training.

### 8.4 Random Forest

Random Forest was developed as a comparison model using the same feature set, preprocessing pipeline and train-test split.

# 9. Model Evaluation

Both models were evaluated at a classification threshold of 0.50.

| Evaluation Metric | Logistic Regression | Random Forest |
|---|---:|---:|
| Accuracy | 66.01% | 67.86% |
| Precision | 34.33% | 35.32% |
| Recall | 68.91% | 65.01% |
| F1 Score | 45.82% | 45.77% |
| ROC-AUC | 73.69% | 73.46% |

### 9.1 Model Selection

Logistic Regression was selected as the primary model.

It achieved:

- Higher recall.
- Slightly higher F1 score.
- Slightly higher ROC-AUC.

Random Forest achieved higher accuracy and precision.

Logistic Regression was preferred because identifying a larger proportion of actual defaults is important in credit risk monitoring.

### 9.2 Confusion Matrix

Logistic Regression at the 0.50 threshold:

| | Predicted Paid | Predicted Default |
|---|---:|---:|
| Actual Paid | 20,138 | 10,728 |
| Actual Default | 2,530 | 5,607 |

The model correctly identified 5,607 defaults and missed 2,530 actual defaults in the test set.

The model also produced 10,728 false-positive default predictions.

This highlights the trade-off between identifying risky borrowers and incorrectly classifying borrowers who eventually repay.

# 10. Interactive Financial Risk Dashboard

An interactive dashboard was developed using Plotly.

### Dashboard Components

1. **Default Rate by Credit Grade:** Compares default rates across grades A–G.
2. **Monthly Default Rate Trend:** Displays the change in observed default rates across the three issue-month cohorts.
3. **Monthly Loan Portfolio Amount:** Shows loan amounts issued in each month.
4. **Model Performance – ROC-AUC:** Compares the predictive performance of Logistic Regression and Random Forest.

### Key Performance Indicators

The dashboard includes:

- Total Loans: 100,000
- Portfolio Value: $1.51 Billion
- Average Loan Amount: $15,055.86
- Default Rate: 20.03%

The dashboard was exported as an interactive HTML file.

**Dashboard Location:** `reports/financial_risk_dashboard.html`

# 11. Business Recommendations

Based on the analysis, the following recommendations are proposed:

### 11.1 Risk-Based Lending

Higher-risk credit grades should receive more detailed borrower assessment before lending decisions are made.

### 11.2 Enhanced Monitoring

Borrowers in higher-risk segments should be monitored more closely for repayment difficulties.

### 11.3 Predictive Risk Assessment

The Logistic Regression model can support preliminary borrower risk identification, subject to further validation.

### 11.4 Regular Portfolio Reporting

Financial analysts should regularly monitor loan volume, portfolio value, repayment outcomes and credit-grade performance.

### 11.5 Model Improvement

Future model development should focus on improving predictive performance, evaluating classification thresholds and reducing false-positive predictions.

# 12. Project Limitations

- The analysis uses a 100,000-record sample rather than the complete LendingClub dataset.
- The sample covers only three months in 2015.
- The model's performance may not generalise to other periods or lending environments.
- The classification results should not be used as the sole basis for actual lending decisions.
- The project focuses on loan portfolio and credit risk reporting rather than actual corporate profit-and-loss or balance-sheet reporting.

# 13. Future Scope

The project can be extended through:

- Integration with Power BI or Qlik Sense.
- Automated monthly financial reporting.
- Additional machine learning algorithms.
- Hyperparameter tuning and model optimisation.
- Analysis of larger historical datasets.
- Web-based deployment of the risk dashboard.
- Automated alerts for changes in portfolio risk.

# 14. Conclusion

The Financial Analytics and Risk Reporting System demonstrates how data analytics, SQL, machine learning and interactive dashboards can be combined to analyse financial loan portfolios.

The analysis identified a clear increase in default rates across lower credit grades and highlighted changes in default rates across the three loan-issue cohorts.

Two machine learning models were developed and evaluated. Logistic Regression was selected as the primary model based on its recall, F1 score and ROC-AUC performance.

The interactive dashboard provides a consolidated view of portfolio performance and credit risk indicators.

Overall, the project demonstrates the practical application of data science and financial analytics techniques to credit risk monitoring and reporting.

---

**Project Developed By:**  
Parth Manohar Kairamkonda

**Project:** Financial Analytics & Risk Reporting System
