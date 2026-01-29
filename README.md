# Loan-Performance-Analysis

Loan Portfolio Performance & Risk Trend Analysis
Overview

This project analyzes the loan portfolio performance and credit risk trends for FinanceZ between June and August 2014.
The goal is to help Risk and Operations management understand how portfolio size, delinquency, and write-offs evolved over time, and whether credit quality deteriorated as lending activity changed.

The analysis focuses on trend detection, risk concentration, and clear executive communication, using SQL for data preparation and Tableau for visualization.

Business Questions

The analysis answers the following key questions:

Did the loan portfolio grow between June and August?

How did delinquency and write-off exposure change over the same period?

Did credit risk deteriorate relative to portfolio growth?

Are observed changes driven by loan counts or by dollar exposure?

Data Description

The dataset consists of three monthly CSV files (June, July, August 2014) with identical schemas.
Each row represents a loan snapshot as of a given observation date.

Key fields:

ID: Loan identifier

Dlq_stat: Loan status (Current, Delinquent, WriteOff)

amounts: Outstanding loan balance

obs_date: Observation date

Dlq_days: Days past due (if delinquent)

Vertical1: Loan origination channel

Province1: Province of origination

Tools & Technologies

SQL (MySQL) – data cleaning, transformation, aggregation

DataGrip – SQL development environment

Tableau – trend visualization

PowerPoint / Google Slides – executive presentation

Methodology
1. Data Cleaning

Removed inconsistent quotation artifacts from categorical fields

Standardized loan status, vertical, and province values

Ensured consistent schema across all months

2. Data Integration

Monthly datasets were stacked (UNION ALL) into a single table to enable time-series analysis:

SELECT * FROM data_06
UNION ALL
SELECT * FROM data_07
UNION ALL
SELECT * FROM data_08;

3. Monthly Aggregation

A monthly trend table was created to support executive reporting:

Total number of loans

Total outstanding balance

Delinquent and write-off outstanding amounts

Delinquency rates by count and amount

This ensured Tableau focused on visualization rather than heavy computation.

4. Visualization & Reporting

Key metrics were visualized as month-over-month trends and summarized in a 2–3 slide executive deck, emphasizing:

Portfolio growth

Risk exposure

Credit quality changes

Key Findings

Portfolio size remained stable from June to July and increased in August

Delinquent and write-off dollar exposure increased significantly in August

Delinquency rate by amount rose from ~0.9% in July to ~1.45% in August

Credit risk deterioration outpaced portfolio growth, indicating emerging stress in loan quality

Deliverables

Cleaned and aggregated SQL tables

Tableau trend visualizations

Executive slide deck summarizing findings

Reproducible SQL scripts for end-to-end analysis

Repository Structure
├── sql/
│   ├── data_cleaning.sql
│   ├── monthly_trend_aggregation.sql
│
├── data/
│   ├── loan_data_june.csv
│   ├── loan_data_july.csv
│   ├── loan_data_august.csv
│
├── tableau/
│   └── loan_performance_trends.twbx
│
├── presentation/
│   └── Loan_Performance_Trend_June_August_2014.pdf
│
└── README.md

Notes

This project emphasizes BI best practices:

SQL-first data modeling

Separation of data preparation and visualization

Clear linkage between metrics and business decisions

Executive-focused storytelling

Author

Fei Wang
Business Intelligence / Data Analytics
