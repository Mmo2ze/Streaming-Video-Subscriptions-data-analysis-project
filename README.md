# Subscription Cohort Analysis

A Power BI project analyzing customer subscription retention, churn, and payment behavior.

## Goal
Build a data model and dashboard to understand how long customers stay subscribed, why they leave, and how retention trends over time.

## Data Source
- **Provider:** Maven Analytics
- **File:** Subscription_Cohort_Analysis_Data.csv
- **Rows:** 3,069 subscriptions
- **Date range:** Sep 2022 – Sep 2023

## Data Dictionary

| Field | Description |
|---|---|
| customer_id | Unique customer ID |
| created_date | Date the subscription started |
| canceled_date | Date the subscription ended (placeholder date = still active) |
| subscription_cost | Price in USD ($39/month, constant) |
| subscription_interval | Billing frequency (monthly, constant) |
| was_subscription_paid | Whether payment was successfully collected |

## Columns Added During Cleaning

| Column | Logic |
|---|---|
| subscription_status | Active / Canceled / Payment failed |
| signup_month | First day of the customer's signup month |
| subscription_duration_days | Days between signup and cancellation (blank if active) |

## Data Model
Star schema with two tables:
- **DimDate** — calendar table (Date, Month, MonthNumber, MonthYear, StartOfMonth, Year)
- **Subscription Cohort Analysis Data** — fact table, related to DimDate via `created_date` → `DimDate[Date]` (one-to-many)

## Dashboard
Built in Power BI. Includes:
- KPI cards: Total Subscribers, Active, Canceled, Failed Payments
- Subscription status breakdown (bar chart)
- Cancellations over time (line chart)

## Tools Used
- Power Query (data cleaning)
- Power BI (data model + dashboard)
- Draw.io (project phases diagram)

## Project Phases
1. Data Sources
2. Data Dictionary
3. Data Cleaning
4. Data Modeling
5. Dashboard (Power BI)
