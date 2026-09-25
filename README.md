# Customer-Shopping-Behaviour-Analysis_BI
# Customer Shopping Behavior Analysis

A business intelligence project analyzing 3,900 customer transactions from a clothing retailer to uncover spending patterns, product performance, and subscription behavior, then turning those findings into an interactive Power BI dashboard and a set of concrete business recommendations.

## Overview

The project moves through a full analytics pipeline: raw CSV data is cleaned and reshaped in Python, loaded into PostgreSQL to answer ten business questions in SQL, then brought into Power BI for an interactive dashboard a non-technical stakeholder can explore on their own.

## Dataset

- **Rows:** 3,900 transactions
- **Columns:** 18, covering customer demographics (age, gender, location, subscription status), purchase details (item, category, amount, season, size, color), and shopping behavior (discount applied, previous purchases, purchase frequency, review rating, shipping type)
- **Missing data:** 37 values in `review_rating`, imputed using the median rating per product category

## Tech Stack

| Stage | Tool |
|---|---|
| Data cleaning & feature engineering | Python (pandas) |
| Data storage & querying | PostgreSQL |
| Dashboard & visualization | Power BI |

## Repository Structure

```
.
├── data/
│   └── customer_shopping_data.csv       # raw dataset
├── notebooks/
│   └── data_cleaning.ipynb              # cleaning, imputation, feature engineering
├── sql/
│   └── business_queries.sql             # the 10 business-question queries
├── dashboard/
│   └── customer_shopping_dashboard.pbix # Power BI dashboard
├── report/
│   └── Customer_Shopping_Behavior_Analysis_Report.pdf
└── README.md
```

> Adjust the folder names above to match how you've actually organized the repo.

## Data Preparation

- Loaded and inspected with `.info()` and `.describe()`
- Imputed missing `review_rating` values using the median per category
- Standardized all column names to `snake_case`
- Engineered `age_group` (binned) and `purchase_frequency_days`
- Dropped `promo_code_used`, redundant with `discount_applied`
- Loaded the cleaned dataset into PostgreSQL for SQL analysis

## Key Questions Answered in SQL

1. Revenue by gender
2. High-spending customers who still use discounts
3. Top 5 products by average rating
4. Standard vs. Express shipping, average purchase amount
5. Subscribers vs. non-subscribers, spend and revenue
6. Products most dependent on discounting
7. Customer segmentation (New / Returning / Loyal)
8. Top 3 products per category
9. Repeat buyers vs. subscription status
10. Revenue by age group

## Dashboard

The Power BI dashboard surfaces three headline KPIs (3.9K customers, $59.76 average purchase amount, 3.75 average review rating) alongside filters for subscription status, gender, category, and shipping type, plus revenue and sales breakdowns by category and age group.

## Key Findings

- Subscribers make up only 27% of customers despite spending at nearly the same rate as non-subscribers
- 2,518 repeat buyers (>5 purchases) are not subscribed
- Hats, sneakers, coats, sweaters, and pants are discounted close to half the time
- Young Adult and Middle-aged customers generate the most revenue

## Recommendations

- Grow the subscriber base
- Build a loyalty program targeting repeat buyers
- Review discount policy on high-discount-dependency products
- Prioritize top-rated products in marketing
- Focus spend on high-revenue age groups and Express shipping users

## Author

Hiba Chaabouni
