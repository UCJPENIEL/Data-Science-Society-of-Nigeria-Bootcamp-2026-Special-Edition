# Data-Science-Society-of-Nigeria-Bootcamp-2026-Special-Edition

# 📊 Sales Performance & Returns Analysis Dashboard

## DSN AI Bootcamp 2026 — Data Analytics Track

This project was completed as part of the **DSN AI Bootcamp 2026 Data Analytics Track**.

The task went beyond simply creating charts from the provided dataset. The objective was to **audit the supplied management data and dashboard, validate the underlying records, identify data-quality and calculation issues, clean and transform the data, and develop a more reliable management dashboard for business decision-making.**

The final solution was developed in **Microsoft Power BI**, with particular attention given to data validation before drawing business conclusions.

---

## 📌 Project Overview

Management dashboards are only as reliable as the data and calculations behind them.

During the initial audit of the supplied dataset, several issues were discovered that could affect the accuracy of reported business performance. These included duplicate records, inconsistent categorical labels, missing cost values, and discrepancies between reported revenue and revenue calculated from the underlying transaction fields.

Rather than immediately visualizing the data, the project followed a **validate → clean → reconcile → analyze → visualize** workflow.

The final result is an interactive **Sales Performance & Returns Analysis Dashboard** designed to provide management with a clearer and more trustworthy view of business performance.

---

## 🎯 Project Objectives

The project aimed to:

- Audit the supplied dataset and existing management reporting.
- Identify data-quality issues that could distort business insights.
- Validate important numerical and categorical fields.
- Remove duplicate transaction records.
- Standardize inconsistent values.
- Investigate missing cost information.
- Recalculate and validate transaction revenue.
- Preserve both reported and calculated values for auditability.
- Build reliable business KPIs.
- Analyze sales, profitability, product, geographic, channel, and return performance.
- Develop an interactive Power BI dashboard that supports management decision-making.

---

## 📂 Dataset

The original dataset contained:

- **432 rows**
- **16 columns**

During the audit, **12 exact duplicate transaction IDs/records** were identified.

After duplicate removal, the validated dataset contained:

- **420 records**

The dataset contains transaction-level information covering areas such as:

- Sales transactions
- Products and product categories
- Units sold
- Unit prices
- Discounts
- Revenue
- Costs
- Sales channels
- Geographic locations
- Customer information
- Returns
- Transaction dates

---

## 🔍 Data Audit & Validation

Before performing the final analysis, the dataset was systematically audited.

### Issues Identified

| Data Quality Issue | Result |
|---|---:|
| Original records | 432 |
| Exact duplicate records identified | 12 |
| Records after duplicate removal | 420 |
| State formatting inconsistencies | 5 |
| Product category label inconsistencies | 3 |
| Missing cost values | 31 |
| Revenue reconciliation anomalies | 22 |

Several important fields also passed basic validation checks, including:

- Unit Price
- Discount values
- Transaction dates
- Sales channels
- Units sold

Some fields, such as customer classification, returns, and unusually high quantities, were treated carefully because determining whether they were truly incorrect would require additional business rules rather than assumptions.

This distinction was important to the project: **unusual data was not automatically treated as bad data.**

---

## 🧹 Data Cleaning & Transformation

The cleaning process was carried out while preserving the original data for traceability.

### Key Cleaning Steps

1. Preserved the original dataset as **Raw Data**.
2. Created a separate cleaned version for analysis.
3. Removed exact duplicate transaction records.
4. Standardized inconsistent **State** values.
5. Standardized inconsistent **Product Category** labels.
6. Investigated missing cost values before applying corrections.
7. Checked numerical fields for invalid or unreasonable values.
8. Validated transaction dates and categorical fields.
9. Reconciled reported revenue against independently calculated revenue.
10. Created validation fields to make discrepancies traceable.

---

## 💰 Revenue Validation

One of the most important parts of the project was validating the reported revenue.

Expected transaction revenue was calculated using:

```text
Calculated Revenue =
Units × Unit Price × (1 - Discount Percentage)
```

The calculated result was compared with the revenue originally reported in the dataset.

Additional fields were maintained conceptually to distinguish:

```text
Reported Revenue
Calculated Revenue
Revenue Difference
Revenue Validation Status
Corrected Revenue
```

This approach made it possible to identify transactions where the reported revenue did not agree with the underlying transaction details.

A total of **22 revenue reconciliation anomalies** were identified during the audit.

Instead of silently overwriting the original values, the validation process maintained traceability between the supplied figures and the corrected analytical values.

---

## 📊 Dashboard

### Sales Performance & Returns Analysis Dashboard

The final Power BI dashboard provides management with an interactive overview of business performance using the validated dataset.

The dashboard focuses on several key areas:

### Sales Performance

Tracks overall business sales and revenue performance and allows management to understand how sales are distributed across the business.

### Profitability

Evaluates the relationship between revenue, cost, and profit to provide a clearer picture of financial performance.

### Product Performance

Compares products and product categories to identify stronger and weaker contributors to overall business performance.

### Geographic Performance

Analyzes performance across states/locations to reveal geographic differences in sales activity.

### Sales Channel Performance

Examines how different sales channels contribute to overall performance.

### Returns Analysis

Evaluates product returns and includes analysis such as:

**Return Rate by Sales Channel**

This helps management identify channels associated with relatively higher or lower levels of returned transactions.

---

## 📈 Key Performance Indicators

The dashboard was designed around management-focused KPIs such as:

- Total Revenue
- Total Cost
- Total Profit
- Profit Margin
- Units Sold
- Number of Transactions
- Returns
- Return Rate

These KPIs provide a high-level view of business performance while the supporting visuals allow users to investigate the factors driving those results.

---

## 🧠 Analytical Approach

A major principle followed throughout this project was:

> **Validate before action.**

The goal was not simply to produce an attractive dashboard.

The workflow ensured that business recommendations were based on data that had first been investigated and validated.

The analytical process therefore followed:

```text
Raw Data
    ↓
Data Audit
    ↓
Data Validation
    ↓
Data Cleaning
    ↓
Revenue Reconciliation
    ↓
Data Transformation
    ↓
KPI Development
    ↓
Exploratory Analysis
    ↓
Power BI Dashboard
    ↓
Business Insights
```

---

## 💡 Key Lessons From the Analysis

The project demonstrated several important principles of real-world data analytics.

### 1. Dashboard numbers should not automatically be trusted

A polished dashboard can still contain misleading results when the underlying dataset contains duplicates, missing values, inconsistent labels, or calculation errors.

### 2. Duplicate transactions can distort business performance

The identification of **12 duplicate records** showed why transaction-level uniqueness should be checked before calculating aggregate KPIs.

### 3. Revenue should be independently validated

The discovery of **22 revenue reconciliation anomalies** demonstrated the importance of checking reported financial metrics against their underlying components.

### 4. Missing values require investigation, not automatic replacement

The **31 missing cost values** were treated as a business-validation problem rather than simply filling them with an arbitrary mean or median.

### 5. Unusual values are not necessarily errors

Some records may look abnormal while still representing legitimate business activity. Without sufficient business rules, such observations should be flagged for investigation rather than automatically removed.

### 6. Data cleaning should remain auditable

Preserving the original values while creating calculated, validation, and corrected fields makes the analytical process easier to explain and defend.

---

## 🛠️ Tools & Technologies

### Microsoft Power BI

Used for:

- Data transformation
- Data modelling
- DAX calculations
- KPI development
- Interactive visualization
- Dashboard development

### Power Query

Used for:

- Data profiling
- Duplicate identification and removal
- Missing-value investigation
- Category standardization
- Data-type validation
- Data cleaning and transformation

### DAX

Used to create analytical measures and management KPIs required by the dashboard.

---

## 📁 Suggested Repository Structure

```text
DSN-Data-Analytics-Track/
│
├── README.md
│
├── data/
│   ├── raw/
│   └── cleaned/
│
├── dashboard/
│   └── Sales_Performance_Returns_Dashboard.pbix
│
├── screenshots/
│   └── dashboard.png
│
├── report/
│   └── DSN_Data_Analytics_Track_Submission.pdf
│
└── documentation/
    └── data_validation_notes.md
```

---

## 🚀 Project Outcome

The final outcome was not simply a redesigned dashboard.

The project transformed the supplied dataset into a more **validated, traceable, and decision-ready analytical solution**.

Starting with **432 records**, the data was audited and reduced to **420 records after removing 12 exact duplicates**. Additional quality problems—including inconsistent categorical labels, **31 missing cost values**, and **22 revenue reconciliation anomalies**—were identified and investigated before the final analysis.

The resulting Power BI dashboard provides management with a clearer view of **sales performance, profitability, product performance, geographic performance, sales channels, and returns**.

Most importantly, the project demonstrates an end-to-end analytics workflow in which **data quality and validation come before visualization and business recommendations**.

---

## 🎓 Project Context

**Program:** DSN AI Bootcamp 2026  
**Track:** Data Analytics  
**Project Type:** Data Audit, Validation, Business Analysis & Dashboard Development  
**Dashboard:** Sales Performance & Returns Analysis Dashboard  
**Primary Tool:** Microsoft Power BI

---

## 👤 Author

**Ugochukwu Joshua Toluwaleke**

Data Analyst | Python | SQL | Power BI | Machine Learning

This project forms part of my practical data analytics portfolio, demonstrating my ability to move beyond visualization into **data validation, analytical reasoning, business intelligence, and decision-focused reporting**.

---

## ⭐ Repository Note

If you found this project useful, feel free to explore the repository and review the analytical workflow used to transform raw transactional data into actionable business insights.