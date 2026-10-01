# 📊 Churn Analysis & Customer Intelligence

An end-to-end **customer churn and revenue analytics project** for an OTT subscription platform. The project combines **SQL, Python, data cleaning, feature engineering, exploratory data analysis, and visualization** to identify high-risk customer segments, quantify revenue at risk, and translate customer behavior into actionable retention strategies.

---

## 🎯 Business Problem

In the highly competitive OTT industry, customer retention is critical for sustainable revenue growth.

The objective of this project is to answer key business questions such as:

* Which customers are most likely to churn?
* Which subscription plans have the highest churn?
* How does contract type affect customer retention?
* Which states or customer segments show unusual churn behavior?
* How much revenue is at risk due to high-risk customers?
* Does customer support activity correlate with churn?
* Which customers should the business prioritize for retention?

The project goes beyond descriptive analysis by converting these findings into **business-focused retention actions**.

---

## 🛠️ Tech Stack

* **SQL / SQLite** – Relational data extraction and analysis
* **Python** – Analytics and automation
* **Pandas** – Data manipulation and analysis
* **NumPy** – Numerical operations and feature engineering
* **Matplotlib** – Data visualization
* **Seaborn** – Statistical and behavioral visualization
* **Jupyter Notebook** – Analysis and reporting

---

## 🗂️ Dataset Structure

The analysis uses a relational database named **`customer_churn`** consisting of three primary tables.

### `db_customer`

| Column       | Description                |
| ------------ | -------------------------- |
| `customerid` | Unique customer identifier |
| `name`       | Customer name              |
| `country`    | Customer country           |
| `state`      | Customer state             |
| `gender`     | Customer gender            |
| `dob`        | Date of birth              |
| `interests`  | Customer interests         |
| `pincode`    | Customer postal code       |

### `db_subscription`

| Column                    | Description                 |
| ------------------------- | --------------------------- |
| `customerid`              | Customer identifier         |
| `subscription_start_date` | Subscription start date     |
| `subscription_type`       | Subscription category       |
| `renewal_date`            | Subscription renewal date   |
| `plan_type`               | Basic / Standard / Premium  |
| `contract_type`           | Monthly / Annual            |
| `cancellation_date`       | Cancellation date           |
| `cancellation_reason`     | Reason for cancellation     |
| `monthly_charges`         | Monthly subscription charge |
| `cltv`                    | Customer Lifetime Value     |
| `churn_score`             | Customer churn-risk score   |

### `db_support`

| Column           | Description                 |
| ---------------- | --------------------------- |
| `customerid`     | Customer identifier         |
| `complaint_date` | Date of complaint           |
| `escalations`    | Support escalation count    |
| `csat_score`     | Customer satisfaction score |
| `comment`        | Customer support comment    |

---

## 🔄 Project Workflow

```text
                 ┌─────────────────────┐
                 │  SQLite Database    │
                 │   customer_churn    │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │   SQL Extraction    │
                 │  Multi-table JOINs  │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │    Data Cleaning    │
                 │ Pandas + NumPy      │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │ Feature Engineering │
                 │ Tenure / Risk / KPI │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │   Exploratory       │
                 │   Data Analysis     │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │   Visualization     │
                 │ Matplotlib/Seaborn  │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │ Business Insights   │
                 │ & Action Items      │
                 └─────────────────────┘
```

---

## 🔍 Key Analysis Areas

### 1. Relational Data Extraction

Connected Python with the SQLite database using `sqlite3` and `pandas` to extract and combine customer, subscription, and support data.

Key operations included:

* SQL queries
* Multi-table joins
* Filtering
* Aggregations
* Grouping
* Importing SQL results into Pandas

---

### 2. Data Cleaning

Performed data-quality checks and preprocessing including:

* Handling missing and null values
* Correcting data types
* Renaming columns
* Selecting relevant columns
* Validating customer records
* Checking duplicate and inconsistent records
* Preparing date fields for analysis

---

### 3. Feature Engineering

Created analytical features required for customer intelligence, including:

* Customer tenure
* Customer age
* Churn indicators
* Churn-risk segments
* Revenue-at-risk indicators
* Contract and subscription cohorts
* Customer-level support metrics

---

## 📈 Key KPIs

| KPI                                 | Definition                                                      |
| ----------------------------------- | --------------------------------------------------------------- |
| **Churn Rate**                      | Churned Customers / Total Customers                             |
| **Retention Rate**                  | 1 − Churn Rate                                                  |
| **Churn by Plan**                   | Churn rate grouped by Basic, Standard and Premium plans         |
| **Churn by Geography**              | Churn rate by country and state                                 |
| **ARPU**                            | Revenue / Active Customers                                      |
| **Average Tenure**                  | Average customer subscription duration                          |
| **Revenue at Risk**                 | Revenue associated with high churn-risk customers               |
| **Escalation Rate**                 | Escalations / Complaints × 100                                  |
| **Average Complaints per Customer** | Total Complaints / Unique Customers                             |
| **Support–Churn Relationship**      | Churn comparison between customers with and without escalations |

---

## 📊 Analysis & Visualization

The project uses exploratory data analysis to investigate churn across multiple dimensions:

* Subscription plan
* Contract type
* Geography
* Customer tenure
* Churn-risk score
* Revenue contribution
* Support complaints
* Escalations
* Customer lifetime value
* Churn over time

Visualizations were created using **Matplotlib and Seaborn** to identify behavioral patterns and communicate findings clearly.

---

## 💡 Key Findings

The analysis produced the following business-level findings:

### Customer Retention

* **Churn Rate:** 28.6%
* **Retention Rate:** 71.4%

### Revenue & Customer Value

* **ARPU:** ₹18.8
* **Total Revenue:** 395
* **Revenue Loss Due to Churn:** 74
* **Revenue Loss:** 18%
* **CLTV Lost:** 2,047

### Customer Tenure

* **Average Customer Tenure:** 1,451 days

### Contract Behavior

A significant difference was observed between monthly and annual subscribers:

* **Monthly Churn:** 55.6%
* **Annual Churn:** 8.3%

This indicates a strong relationship between **contract structure and customer retention**, making contract migration a potential retention strategy to investigate further.

### Geographic & Temporal Pattern

* The highest concentration of churn occurred in **September 2024**.
* **Karnataka** was the most affected state in the analyzed dataset.

### Subscription Plan

* The **Basic plan** accounted for the largest share of churn.
* However, churn volume alone does not necessarily indicate the largest revenue impact, making revenue contribution and customer value important dimensions when prioritizing retention efforts.

---

## 🎯 Business Recommendations

Based on the analysis, the following actions can be investigated:

### 1. Investigate the Karnataka Churn Spike

Analyze whether the increase in churn was associated with:

* Pricing changes
* Technical issues
* Service disruptions
* Increased customer complaints
* Support quality
* Competitor activity

### 2. Investigate September 2024

Review product, pricing, and customer-support changes introduced around September 2024 to identify potential drivers behind the churn increase.

### 3. Analyze Monthly-to-Annual Migration

Given the observed churn difference between monthly and annual contracts, evaluate incentives that could encourage suitable monthly customers to move toward annual subscriptions.

### 4. Prioritize High-Risk Customers

Create a retention priority list using:

```text
Churn Risk
     +
Customer Lifetime Value
     +
Support Complaints
     +
Subscription Value
```

Customers with high churn risk and high customer value can be prioritized for proactive retention campaigns.

### 5. Proactive Customer Outreach

Potential retention channels include:

* Email
* SMS
* Customer support calls
* Personalized offers
* Issue resolution campaigns

---

## 🧠 Business Impact

This project demonstrates how raw customer and subscription data can be transformed into a **customer intelligence system**.

Instead of simply calculating churn, the analysis connects:

```text
Customer Behavior
       ↓
Subscription Patterns
       ↓
Support Interactions
       ↓
Churn Risk
       ↓
Revenue at Risk
       ↓
Retention Strategy
```

The final objective is to help businesses identify **which customers are at risk, why they may churn, how much value is at stake, and where retention efforts should be focused.**

---

## 📌 Portfolio Summary

> Engineered an end-to-end churn analytics pipeline for an OTT subscription platform by integrating multi-table customer, subscription, and support data. Developed 20+ KPIs and analyzed churn across contract type, subscription plan, geography, customer tenure, support activity, and churn risk. Identified a significant churn disparity between monthly and annual contracts, quantified revenue and CLTV impact from churn, and translated findings into data-driven customer retention strategies.

---

## 🚀 Skills Demonstrated

* SQL Data Extraction
* Relational Database Analysis
* Python
* Pandas
* NumPy
* SQLite
* Data Cleaning
* Feature Engineering
* Exploratory Data Analysis
* KPI Development
* Customer Segmentation
* Churn Analysis
* Revenue Analysis
* Behavioral Analytics
* Data Visualization
* Business Intelligence
* Actionable Insight Generation

---

## 📁 Project Structure

```text
Churn-Analysis-Customer-Intelligence/
│
├── data/
│   └── customer_churn.db
│
├── notebooks/
│   └── churn_analysis.ipynb
│
├── sql/
│   └── churn_analysis.sql
│
├── visualizations/
│   └── charts/
│
├── README.md
└── requirements.txt
```

---

## 👩‍💻 Author

**Diksha Anand**

Computer Engineering | Data Analytics | Machine Learning

[GitHub](https://github.com/dikshaforsure)
