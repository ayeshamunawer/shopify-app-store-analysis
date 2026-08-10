# 💡 Analyst Memo — Shopify App Store Insights

**Dashboard:** Shopify App Store Analysis

**Reporting Period:** 2018–2024

---

## Key Insight

The Shopify App Store analysis includes **500 applications and 7,980 customer reviews**, with an overall average rating of **4.19 out of 5**. Merchant satisfaction is generally strong based on the high average rating; however, developer engagement with customer feedback is relatively limited, with developers replying to approximately **24.80% of reviews**.

Review activity has increased substantially over time. The Overview and Trend Analysis dashboards show a strong upward trend in the number of reviews from 2018 through 2024. The Trend Analysis page shows a **91.09% review growth rate**, approximately **4,000 reviews YTD**, and **365 reviews MTD**, demonstrating continued growth in merchant engagement with app reviews.

Category-level analysis also shows differences in review activity across the marketplace. The category breakdown identifies **SEO** as one of the highest-review categories displayed in the dashboard, indicating strong merchant engagement in this area.

---

## Business Impact

The high average rating of **4.19** suggests that merchants generally have positive experiences with Shopify applications. Maintaining this level of satisfaction is important for marketplace trust and continued merchant adoption of apps.

At the same time, the **24.80% developer reply rate** indicates an opportunity to increase developer participation in customer conversations. Responding to reviews can provide developers with opportunities to address concerns, clarify issues, and demonstrate responsiveness to merchants.

The strong increase in review activity over time also provides Shopify with a growing source of merchant feedback. Monitoring review volume, ratings, and category-level activity can help identify areas of strong marketplace engagement and potential opportunities for improvement.

---

## Recommendation

Shopify should encourage app developers to respond more consistently to customer reviews, particularly as review activity continues to increase. Improving developer engagement could strengthen relationships between merchants and app developers while creating additional opportunities to address customer concerns.

Shopify should also continue monitoring review activity by category and over time. Categories with high review volume can provide valuable insight into areas where merchants are highly engaged, while changes in review growth can help identify emerging marketplace trends.

Future analysis could also examine whether developer replies are associated with changes in ratings, helpful votes, or long-term review activity.

---

# Dashboard Overview

The Power BI report contains two report pages: **Overview** and **Trend Analysis**.

## Overview

The Overview page provides a high-level summary of the Shopify App Store marketplace.

### Key Performance Indicators

| KPI | Result |
|---|---:|
| Total Apps | 500 |
| Total Reviews | 7,980 |
| Average Rating | 4.19 |
| Developer Reply % | 24.80% |

### Overview Visuals

The Overview page includes:

- Total applications
- Total customer reviews
- Average customer rating
- Developer reply percentage
- Review trends by year
- Review volume by app category
- App-level review and rating information
- Category filter
- Year filter
- Free-plan filter
- Page navigation between report pages

---

## Trend Analysis

The Trend Analysis page focuses on changes in review activity over time and applies Power BI time-intelligence concepts.

### Key Trend Metrics

| Metric | Result |
|---|---:|
| Review Growth % | 91.09% |
| Reviews YTD | Approximately 4,000 |
| Reviews MTD | 365 |

The page includes:

- Total reviews by year
- Reviews from the previous year
- Review growth percentage
- Reviews YTD
- Reviews MTD
- Year slicer
- Category slicer
- Navigation between Overview and Trend Analysis

The trend visuals show that review activity increased substantially between 2018 and 2024.

---

# Data Sources

The analysis uses two CSV datasets:

### apps.csv

Contains information about Shopify applications, including:

- `app_id`
- `app_name`
- `developer`
- `category_name`
- `launch_date`
- `has_free_plan`
- `monthly_price_usd`

### reviews.csv

Contains customer review information, including:

- `review_id`
- `app_id`
- `rating`
- `posted_at`
- `has_developer_reply`
- `helpful_count`

---

# Data Cleaning

The raw datasets were cleaned using **Power Query** before analysis.

The following transformations were applied:

- Trimmed extra spaces from application names and developer names
- Replaced missing developer names with `Unknown Developer`
- Standardized category names using Capitalize Each Word
- Removed duplicate review records using `review_id`
- Removed invalid ratings outside the 1–5 range
- Converted review dates using the appropriate date/locale settings
- Converted developer reply values from `Yes`/`No` to `1`/`0`
- Reviewed and corrected column data types

---

# Data Model

The Power BI report uses three primary tables:

- `apps`
- `reviews`
- `dim_date`

The `apps` table is connected to the `reviews` table using `app_id`.

The `dim_date` table is connected to the `reviews` table using the review date.

This model supports filtering, aggregation, and time-intelligence calculations throughout the report.

---

# DAX Measures

Key measures used in the dashboard include:

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

# Tools

The project was developed using:

- Microsoft Power BI
- Power Query
- DAX
- GitHub

---
# Repository Structure
shopify-app-store-analysis
│
├── README.md
├── report.pbix
│
├── data
│   ├── apps.csv
│   └── reviews.csv
│
└── screenshots
    ├── overview_page.png
    ├── trend_analysis_page.png
    └── model_view.png

    
