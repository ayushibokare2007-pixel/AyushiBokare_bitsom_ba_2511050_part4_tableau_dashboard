# Retail Executive Dashboard – Tableau Project

## Business Problem Summary

The retail leadership team requires an executive dashboard to monitor business performance across sales, profitability, customer segments, product categories, shipping performance, discounts, and product returns. The objective is to identify growth opportunities, operational inefficiencies, and profitability risks through interactive visual analytics.

---

## Dataset Description

Dataset File:

```text
data/dashboard_sales_data.xlsx
```

The dataset contains retail transaction data including:

* Order information
* Customer details
* Geographic information
* Product categories and sub-categories
* Sales and profit metrics
* Discounts
* Shipping details
* Delivery performance
* Product returns
* Customer ratings
* Campaign channels

### Key Fields

| Field            | Description                        |
| ---------------- | ---------------------------------- |
| order_id         | Unique order identifier            |
| order_date       | Date order was placed              |
| ship_date        | Date order was shipped             |
| customer_segment | Customer segment classification    |
| region           | Geographic region                  |
| state            | State information                  |
| category         | Product category                   |
| sub_category     | Product sub-category               |
| sales            | Revenue generated                  |
| profit           | Profit earned                      |
| discount         | Discount percentage                |
| return_flag      | Return indicator (0 = No, 1 = Yes) |
| delivery_days    | Shipping duration                  |
| ship_mode        | Shipping method                    |

---

## Tableau Workbook Description

Workbook File:

```text
tableau/executive_dashboard.twbx
```

The Tableau workbook contains:

1. Sales Trend View
2. Regional Performance View
3. Category Profitability View
4. Customer Segment View
5. Shipping Performance View
6. Discount vs Profit View
7. Return Analysis View
8. Executive Dashboard

The workbook includes interactive filters, calculated fields, KPI cards, and dashboard actions.

---

## Calculated Fields Created

### 1. Profit Margin

```tableau
SUM([profit]) / SUM([sales])
```

Purpose:
Measures profitability as a percentage of sales.

---

### 2. Cost

```tableau
SUM([sales]) - SUM([profit])
```

Purpose:
Calculates estimated cost associated with sales.

---

### 3. Average Order Value

```tableau
SUM([sales]) / COUNTD([order_id])
```

Purpose:
Measures average revenue generated per order.

---

### 4. Return Rate

```tableau
SUM([return_flag]) / COUNTD([order_id])
```

Purpose:
Measures percentage of returned orders.

---

### 5. Shipping Delay Bucket

```tableau
IF [delivery_days] <= 2 THEN "Fast (0-2 Days)"
ELSEIF [delivery_days] <= 5 THEN "Normal (3-5 Days)"
ELSEIF [delivery_days] <= 7 THEN "Slow (6-7 Days)"
ELSE "Very Slow (8+ Days)"
END
```

Purpose:
Categorizes delivery performance into meaningful groups.

---

## Dashboard Components

### KPI Cards

* Total Sales
* Total Profit
* Profit Margin %
* Return Rate %

### Visualizations

* Monthly Sales Trend
* Regional Sales and Profit Analysis
* Category and Sub-Category Profitability
* Customer Segment Comparison
* Shipping Performance Analysis
* Discount vs Profit Relationship
* Return Pattern Analysis

---

## Filters and Interactions Used

### Interactive Filters

* Region
* Category
* Customer Segment
* Ship Mode
* Order Date

### Dashboard Actions

A filter action has been implemented where selecting a region updates all dashboard views dynamically, enabling focused business analysis.

---

## Key Business Insights

### Sales Performance

Sales demonstrate seasonal fluctuations, indicating varying customer demand throughout the year.

### Regional Performance

Certain regions contribute significantly more sales and profit than others, suggesting stronger market penetration.

### Category Profitability

Some product categories generate high revenue but lower profitability, indicating margin optimization opportunities.

### Customer Segments

Customer segments contribute differently to sales and profits, highlighting opportunities for targeted marketing strategies.

### Discount Impact

Higher discount levels are frequently associated with lower profitability.

### Shipping Performance

Certain shipping modes experience longer delivery times, potentially affecting customer satisfaction.

### Return Patterns

Returns are concentrated within specific categories and regions, indicating potential product or fulfillment issues.

### Growth Opportunities

High-performing categories and regions provide opportunities for business expansion and investment.

---

## Dashboard Story Summary

The dashboard reveals that while overall sales performance remains strong, profitability is influenced by regional differences, discount strategies, delivery performance, and return rates.

Leadership should focus on:

* Improving profit margins
* Reducing return rates
* Optimizing discount strategies
* Enhancing shipping efficiency
* Investing in high-performing categories and regions

The dashboard provides a comprehensive view of operational and financial performance to support data-driven decision-making.

---

## Assumptions and Limitations

### Assumptions

* Return Flag values:

  * 0 = Not Returned
  * 1 = Returned
* Delivery Days accurately represent shipping duration.
* Sales and Profit values are correctly recorded.
* Order IDs are unique transaction identifiers.

### Limitations

* No inventory information available.
* No customer lifetime value data.
* No marketing spend information.
* No competitor benchmarking data.
* No product cost breakdown beyond estimated cost calculation.

---

## Screenshots Included

The repository contains the following dashboard screenshots:

```text
screenshots/full_dashboard.png
screenshots/sales_trend_view.png
screenshots/regional_performance_view.png
screenshots/category_profitability_view.png
screenshots/filter_interaction_view.png
```

These screenshots demonstrate dashboard functionality, visualization quality, and interactive filtering capabilities.

---

## Repository Structure

```text
part4_tableau_dashboard/
├── data/
│   └── dashboard_sales_data.xlsx
├── tableau/
│   └── executive_dashboard.twbx
├── outputs/
│   ├── dashboard_story.md
│   ├── business_insights.md
│   └── chart_selection_justification.md
├── screenshots/
│   ├── full_dashboard.png
│   ├── sales_trend_view.png
│   ├── regional_performance_view.png
│   ├── category_profitability_view.png
│   └── filter_interaction_view.png
└── README.md
```

This project demonstrates the application of Tableau for executive reporting, business intelligence, interactive dashboarding, and data-driven decision support.
