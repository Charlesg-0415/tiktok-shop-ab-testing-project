# TikTok Shop A/B Testing Project

## Project Overview

This project simulates an end-to-end A/B testing workflow for a TikTok Shop-style e-commerce feature rollout. The hypothetical feature is a seller-facing content conversion tool designed to improve the transition from product views to purchases.

Using public e-commerce event data, this project builds a full analytics pipeline from raw event ingestion to database modeling, SQL-based metric extraction, statistical testing, and business recommendation.

## Objective

The main business question is:

> Does the new seller-facing feature improve product conversion rate compared with the existing experience?

The primary metric is purchase conversion rate:

```text
Conversion Rate = Number of Purchased Sessions / Number of Product View Sessions
```
The hypotheses for the A/B test are:

```text
H0: The treatment group and control group have the same conversion rate.
H1: The treatment group has a higher conversion rate than the control group.
```

## Methodology

The analysis will include:

```text
1. Data cleaning and validation
2. Database schema design
3. SQL-based metric aggregation
4. Treatment/control assignment simulation
5. Conversion rate comparison
6. Two-proportion z-test
7. Confidence interval estimation
8. Logistic regression adjustment
9. Business recommendation based on statistical and practical significance
```

## Project Scope

This project covers the full experimentation analytics workflow:

```text
1. Define business problem and experiment hypothesis
2. Collect and inspect public e-commerce event data
3. Clean raw event logs and construct analysis-ready variables
4. Design a relational database schema for event-level and session-level data
5. Load processed data into PostgreSQL or SQLite
6. Use SQL to extract experiment-ready metrics
7. Simulate treatment and control assignment
8. Evaluate conversion lift using statistical tests
9. Run regression-adjusted analysis for robustness
10. Translate results into business recommendations
```

## Data Source

The main dataset planned for this project is the RetailRocket e-commerce behavior dataset, which contains user event logs such as product views, add-to-cart events, and transactions.

Because real TikTok Shop experiment logs are not publicly available, this project uses public e-commerce behavior data to simulate a TikTok Shop-style feature rollout.

Key event types:

- `view`: a user viewed a product
- `addtocart`: a user added a product to cart
- `transaction`: a user purchased a product

These events will be transformed into session-level conversion metrics.

## Tech Stack

- Python
- SQL
- PostgreSQL or SQLite
- pandas
- numpy
- scipy / statsmodels
- matplotlib / seaborn
- Jupyter Notebook

## Repository Structure

```text
tiktok-shop-ab-testing-project/
├── README.md
├── data/
│   ├── raw/                  # Raw public datasets, not tracked by Git
│   ├── processed/            # Cleaned intermediate datasets
│   └── sample/               # Small sample files for demonstration
│
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_database_validation.ipynb
│   ├── 03_ab_testing_analysis.ipynb
│   └── 04_report_figures.ipynb
│
├── src/
│   ├── config.py
│   ├── db_connection.py
│   ├── load_data.py
│   ├── clean_events.py
│   ├── build_experiment_table.py
│   └── run_ab_test.py
│
├── sql/
│   ├── 01_create_tables.sql
│   ├── 02_load_raw_data.sql
│   ├── 03_create_experiment_assignment.sql
│   ├── 04_build_session_metrics.sql
│   └── 05_analysis_queries.sql
│
├── reports/
│   ├── figures/
│   └── final_report.pdf
│
├── requirements.txt
└── .gitignore