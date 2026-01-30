# Loan Portfolio Performance & Risk Trend Analysis (June–August 2014)

## Overview
This project analyzes **loan portfolio performance and credit risk trends** for FinanceZ between **June and August 2014**.  
The objective is to support **Risk and Operations management** in understanding how portfolio size, delinquency, and write-offs evolved over time, and whether credit quality deteriorated as lending activity changed.

The project follows a **SQL-first BI workflow**, using Tableau for visualization and PowerPoint for executive reporting.

---

## Business Questions
The analysis addresses the following questions:

- Did the loan portfolio grow between June and August?
- How did delinquency and write-off exposure change over the same period?
- Did credit risk deteriorate relative to portfolio growth?
- Are changes driven by loan counts or dollar exposure?

---

## Data Description
The dataset consists of **three monthly CSV files** (June, July, August 2014) with identical schemas.  
Each row represents a loan snapshot as of the observation date.

**Key fields:**
- `ID` – Loan identifier  
- `Dlq_stat` – Loan status (`Current`, `Delinquent`, `WriteOff`)  
- `amounts` – Outstanding loan balance  
- `obs_date` – Observation date  
- `Dlq_days` – Days past due (if delinquent)  
- `Vertical1` – Loan origination channel  
- `Province1` – Province of origination  

---

## Tools & Technologies
- **SQL (MySQL)** – data cleaning, integration, and aggregation  
- **DataGrip** – SQL development environment  
- **Tableau** – trend visualization  
- **PowerPoint / Google Slides** – executive presentation  

---

## Methodology

### 1. Data Cleaning
- Removed inconsistent quotation artifacts from categorical fields
- Standardized loan status, vertical, and province values
- Ensured consistent schema across all monthly datasets

### 2. Data Integration
Monthly datasets were **stacked (UNION ALL)** into a single table to enable time-series analysis.

### 3. Monthly Aggregation
A monthly summary table was created to support trend analysis, including:
- Total number of loans
- Total outstanding balance
- Delinquent and write-off outstanding amounts
- Delinquency rates by **count** and **amount**

This approach ensured that Tableau was used primarily for visualization rather than heavy computation.

### 4. Visualization & Reporting
Key metrics were visualized as **month-over-month trends** and summarized in a **2–3 slide executive deck**, focusing on:
- Portfolio growth
- Risk exposure
- Credit quality changes

---

## Key Findings
- Portfolio size remained stable from June to July and increased in August
- Delinquent and write-off dollar exposure increased significantly in August
- Delinquency rate by amount rose from ~0.9% in July to ~1.45% in August
- Credit risk deterioration outpaced portfolio growth, indicating emerging stress in loan quality

---

## Deliverables
- Cleaned and aggregated SQL tables
- Tableau trend visualizations
- Executive slide deck summarizing findings
- Reproducible SQL scripts for end-to-end analysis

---

## Repository Structure

