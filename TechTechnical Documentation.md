# Technical Documentation

## 📊 Project Overview

This document provides the technical details supporting the Shopify App Store Analysis Power BI report.

The analysis uses application and customer review datasets and applies Power Query, data modeling, DAX, and Power BI visualizations to analyze application performance and review trends.

---

# 🗂️ Data Sources

The analysis uses two CSV datasets.

## `apps.csv`

The applications dataset contains information about Shopify applications, including:

- `app_id`
- `app_name`
- `developer`
- `category_name`
- `launch_date`
- `has_free_plan`
- `monthly_price_usd`

## `reviews.csv`

The reviews dataset contains customer review information, including:

- `review_id`
- `app_id`
- `rating`
- `posted_at`
- `has_developer_reply`
- `helpful_count`

---

# 🧹 Data Cleaning & Preparation

The datasets were prepared using **Power Query**.

Data preparation included:

- Reviewing the structure and data types of the datasets
- Cleaning text fields
- Standardizing category names
- Handling missing developer information
- Removing duplicate review records
- Checking rating values
- Converting review dates to the appropriate date data type
- Converting developer reply values into a format suitable for analysis
- Preparing the datasets for modeling and visualization

---

# 🔗 Data Model

The Power BI report uses three primary tables:

- `apps`
- `reviews`
- `dim_date`

The `apps` table is connected to the `reviews` table using `app_id`.

The `dim_date` table is connected to the `reviews` table using the review date.

The resulting star-schema model supports filtering, aggregation, and time-intelligence calculations throughout the report.

---

# 🧮 DAX Measures

Key measures created for the dashboard include:

- Total Apps
- Total Reviews
- Average Rating
- Developer Reply %
- Reviews Previous Year
- Review Growth %
- Reviews YTD
- Reviews MTD

Time-intelligence calculations use functions including:

- `CALCULATE()`
- `DATEADD()`
- `SAMEPERIODLASTYEAR()`
- `TOTALYTD()`
- `TOTALMTD()`

---

# 📈 Dashboard Calculations

The report includes KPI cards and visualizations supporting:

- Application count
- Review count
- Average rating
- Developer reply percentage
- Year-over-year review comparisons
- Review growth
- Year-to-date review activity
- Month-to-date review activity
- Category-level review analysis

---

# 🛠️ Tools & Technologies

This project was developed using:

- Microsoft Power BI
- Power Query
- DAX
- GitHub
- CSV datasets

---

# 📷 Report Pages

## Overview

The Overview page provides a high-level summary of application and review performance.

Key metrics include:

- Total Apps: **500**
- Total Reviews: **7,980**
- Average Rating: **4.19**
- Developer Reply %: **24.80%**

## Trend Analysis

The Trend Analysis page focuses on review activity over time.

Key metrics include:

- Review Growth: **91.09%**
- Reviews YTD: approximately **4,000**
- Reviews MTD: **365**

---

# 📁 Repository Structure

```text
shopify-app-store-analysis/
│
├── README.md
├── Technical Documentation.md
├── report.pbix
│
├── data/
│   ├── apps.csv
│   └── reviews.csv
│
└── screenshots/
    ├── overview_page.png
    ├── trend_analysis_page.png
    └── model_view.png
