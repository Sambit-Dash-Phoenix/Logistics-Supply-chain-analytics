# Supply Chain Analytics Dashboard | Power BI

A Power BI dashboard for analyzing procurement spend, supplier performance, and logistics and delivery operations. The report brings key operational measures into one place to help users review costs, supplier quality and risk, and delivery reliability.

> **Project type:** Power BI Supply chain project
> **Tools:** Power BI Desktop, Power Query, DAX ,Data modeling
> **Focus areas:** Procurement analytics, supplier performance, logistics analytics

## Dashboard Preview

### Executive Overview
![Supply Chain Analytics Overview](https://github.com/Sambit-Dash-Phoenix/Logistics-Supply-chain-analytics/blob/main/Overview.png)

The overview brings together procurement spend, purchase-order status, supplier risk, and delayed-shipment analysis.

### Supplier & Procurement Performance
![Supplier and Procurement Performance](https://github.com/Sambit-Dash-Phoenix/Logistics-Supply-chain-analytics/blob/main/Supplier%20Performance.png)

Explore supplier pricing variance, supplier performance, monthly price variance, and supplier-level metrics.

### Logistics & Delivery Performance
![Logistics and Delivery Performance](https://github.com/Sambit-Dash-Phoenix/Logistics-Supply-chain-analytics/blob/main/Logistics%20Performance.png)

Review freight cost by transport mode, on-time delivery by region, transit time by carrier, carrier performance against SLA targets, and monthly delivery trends.

### Dashboard Navigation / Landing Page
![Dashboard Landing Page](images/Overview.png)

## Business Problem

Procurement and logistics information can be spread across purchase orders, supplier master data, quantity logs, shipment and carrier records, warehouse data, and monthly targets. This makes it harder to:

- Compare actual procurement spend with monthly targets.
- Identify suppliers or product categories with unfavorable purchase-price variance.
- Monitor supplier quality, delivery scores, and risk levels.
- Track on-time delivery and find delayed shipments by carrier, region, and transport mode.
- Understand freight-cost distribution and carrier performance against service-level targets.

## Project Objectives

- Build a consolidated, three-page Power BI report for executive review and operational analysis.
- Compare actual procurement spend with target spend and review spend variance by category.
- Evaluate suppliers using pricing, quality, delivery, rating, and risk indicators.
- Analyze freight costs, transit times, on-time delivery, and shipment delays.
- Present the results through interactive visuals, slicers, KPI cards, and detail tables.

## Report Pages

| Page | Purpose | Example analysis |
|---|---|---|
| **1. Overview** | Executive summary of procurement and operational health | Actual vs. target spend, spend variance by category, purchase-order status, supplier risk, delayed shipments |
| **2. Supplier & Procurement Performance** | Supplier comparison and procurement cost control | Supplier performance matrix, purchase-price variance by supplier and month, supplier detail table |
| **3. Logistics & Delivery Performance** | Delivery reliability and logistics efficiency | Freight cost by transport mode, on-time delivery by region, carrier OTD vs. SLA, average transit time by carrier |

## Key KPIs

The following values are visible in the supplied dashboard screenshots. They reflect the current report view and may change when slicers or date filters are applied.

| KPI | Displayed value | What it measures |
|---|---:|---|
| Actual procurement spend | 991.94M | Procurement spend in the current report view |
| Total purchase orders | 480 | Purchase-order volume |
| On-time delivery | 63.71% | Share of delivered shipments completed on or before the promised date |
| Average lead time | 10.43 days | Average time from order to actual delivery |
| Rejection rate | 0.82% | Rejected quantity as a share of received quantity |
| Total suppliers | 48 | Suppliers represented in the report |
| Average supplier rating | 4.09 | Average supplier rating |
| Purchase-price variance | 1.12% | Purchase-price variance shown on the supplier page |
| Average quality score | 87.10 | Supplier quality score |
| Average delivery score | 83.31 | Supplier delivery score |
| Total freight cost | 24.13M | Freight cost in the logistics report view |
| Average transit time | 7.96 days | Average shipment transit time |
| Delayed shipments | 487 | Count of delayed shipments |
| Delivery SLA gap | -0.27 | Difference between actual delivery performance and carrier SLA target, as displayed |

**Note:** Spend and freight-cost values are shown in the units/format displayed by the dashboard. Confirm the currency and scale in the model before publishing if they are not already documented in the report.

## Business Questions This Dashboard Helps Explore

- How does actual procurement spend compare with the monthly target?
- Which product categories contribute most to spend variance?
- Which suppliers show higher purchase-price variance?
- How do supplier rating, quality score, delivery score, and risk level compare?
- What proportion of purchase orders are closed, cancelled, or open?
- Which transport modes account for the largest share of freight cost?
- How does on-time delivery vary by region and month?
- Which carriers perform above or below their SLA targets?
- Which carriers have the longest average transit times?
- How are delayed shipments distributed across transport modes, carriers, regions, and product categories?

## Data Model & Analytical Approach

The project brief describes a model with two fact tables at different levels of detail:

- **Procurement actuals:** purchase-order-line grain.
- **Targets:** product-category-by-month grain.
- **Conformed dimensions:** Date and Category filter both fact tables to support valid actual-versus-target comparisons.

The brief also highlights several modeling practices:

- Keep monthly targets separate from purchase-order rows to avoid duplicating target values and inflating totals.
- Use an inactive date relationship with `USERELATIONSHIP` when a measure needs to analyze delivery-date months rather than the default date relationship.
- Choose visuals to answer business questions and reflect the data distribution.

## KPI Definitions

| KPI | Definition |
|---|---|
| Actual Spend | Actual unit price × ordered quantity |
| Total POs | Distinct count of purchase-order IDs |
| On-Time Delivery % | On-time delivered shipments ÷ delivered shipments |
| Average Lead Time | Time from order date to actual delivery date |
| Rejection Rate % | Rejected quantity ÷ received quantity |
| Purchase-Price Variance % | (Actual spend − contract spend) ÷ contract spend |
| Freight Cost | Sum of freight cost |
| SLA Gap | Actual on-time delivery % − carrier SLA target |

## Features

- KPI cards for high-level performance monitoring.
- Monthly trend analysis.
- Actual-versus-target spend comparison.
- Category and supplier-level variance analysis.
- Supplier performance and risk comparison.
- Freight-cost distribution by transport mode.
- Regional delivery performance.
- Carrier SLA comparison and transit-time analysis.
- Interactive filters for date, month, supplier, and quarter where available.

## Tools & Skills Demonstrated

- **Power BI Desktop** — report development and visualization.
- **Power Query** — data preparation and transformation.
- **DAX** — KPI calculations and time-aware measures.
- **Data modeling** — fact-table grain, shared dimensions, and relationship design.
- **Business analysis** — translating procurement and logistics questions into report metrics.

## Repository Contents

Suggested repository structure:

```text
supply-chain-analytics/
├── README.md
├── images/
│   ├── Overview.png
│   ├── Summary.png
│   ├── Supplier Performance.png
│   └── Logistics Performance.png
└── PowerBI/
    └── <your Power BI project files>
```

Add your `.pbip` project and its associated report/model folders under `PowerBI/` (or at the repository root). If you also share a `.pbix`, check GitHub's file-size limits and avoid committing sensitive or confidential data.

## Potential Future Improvements

- Add drill-through pages for supplier and carrier investigations.
- Add tooltip pages explaining KPI definitions and context.
- Include a documented data dictionary and refresh instructions.
- Add a short section describing data quality checks and validation.
- Document additional DAX measures and any assumptions used in the model.

## Disclaimer

This is a portfolio/practice analytics project. The displayed metrics are taken from the current dashboard screenshots and are not independently audited. Interpret the figures in the context of the dataset, filters, and business definitions used in the report.
