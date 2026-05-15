# Bank Loan Data Analysis Project

## Overview

This project focuses on analyzing bank loan data to extract meaningful insights about lending patterns, borrower behavior, and financial performance. The analysis is performed using Python with libraries like Pandas, NumPy, Matplotlib, and Seaborn.

## Objective

The goal of this project is to:

* Analyze loan applications and funding trends
* Identify good vs bad loans
* Evaluate borrower financial health
* Visualize key business insights using charts and dashboards

## Dataset

* File: `financial_loan.xlsx`
* Contains details about:

  * Loan applications
  * Loan amount (funded & received)
  * Interest rates
  * Debt-to-Income (DTI)
  * Loan status
  * Borrower details (employment, home ownership, etc.)

##  Key Performance Indicators (KPIs)

###  General KPIs

* Total Loan Applications
* Month-to-Date (MTD) Loan Applications
* Total Funded Amount
* MTD Funded Amount
* Total Amount Received
* MTD Amount Received
* Average Interest Rate
* Average Debt-to-Income (DTI)

---

###  Good vs Bad Loan Analysis

####  Good Loans

* Fully Paid / Current loans
* Good Loan Application %
* Good Loan Funded Amount
* Good Loan Total Received Amount

####  Bad Loans

* Charged Off / Defaulted loans
* Bad Loan Application %
* Bad Loan Funded Amount
* Bad Loan Total Received Amount

---

##  Visualizations

The project includes multiple visualizations to understand trends and patterns:

*  **Monthly Trends (Line/Area Chart)**
  → Shows loan applications and funding over time

*  **Regional Analysis (Bar Chart)**
  → Loan distribution across states

*  **Loan Term Analysis (Donut Chart)**
  → Distribution of loan terms

*  **Employment Length Analysis (Bar Chart)**
  → Impact of employment history on loans

*  **Loan Purpose Breakdown (Bar Chart)**
  → Reasons for taking loans

*  **Home Ownership Analysis (Heatmap)**
  → Loan distribution by ownership type

---

##  Tools & Technologies

* Python 
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Jupyter Notebook / VS Code

---

##  Key Insights

* Majority of loans are concentrated among **Mortgage and Rent categories**
* Loan applications show **monthly trends and seasonality**
* Good loans significantly outweigh bad loans, indicating **portfolio stability**
* Employment length and loan purpose influence loan distribution

---

##  Project Structure

```
 Bank Loan Project
 ┣  financial_loan.xlsx
 ┣  Bank Loan Project.ipynb
 ┣  Problem Statement.pptx
 ┗  README.md
```

---

##  How to Run

1. Clone the repository

```bash
git clone https://github.com/your-username/bank-loan-analysis.git
```

2. Install dependencies

```bash
pip install pandas numpy matplotlib seaborn openpyxl
```

3. Run the notebook

```bash
jupyter notebook
```

---

##  Future Improvements

* Build an interactive dashboard using Plotly or Power BI
* Add predictive modeling (loan default prediction)
* Deploy as a web app

---


## 👤 Author

**Madhavan Shanmugam**

*Data Analyst | Python | Power BI | SQL | Advanced Excel*

---

