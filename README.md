# saas-revenue-leak-detector

## Problem Statement
SaaS companies lose significant revenue every month through billing errors, unpaid invoices, and unauthorized discounts — most of which go undetected because they're spread across thousands of transactions. This project builds an end-to-end system to detect, quantify, and prioritize revenue leaks.

## Key Findings
**₹40.1 lakh in revenue leakage** detected across 346 customers over 18 months.

| Leak Type | Invoices/Cases | Amount |
|-----------|---------------|--------|
| Overdue Payments | 604 invoices | ₹32.1 lakh |
| Billing Errors | 271 invoices | ₹5.1 lakh |
| Discount Abuse | 280 cases | ₹2.8 lakh |

## Business Recommendation
Prioritize fixing **Enterprise billing errors first** — only 54 errors but ₹2.39 lakh in losses. Highest recovery per fix. A single Enterprise billing error leaks ₹12,000/month and shows as "Paid" in the system — making it the hardest leak to catch manually.

## Tools Used
- **Python** — data generation, analysis (pandas, numpy, faker)
- **SQL** — leak detection queries (SQLite)
- **Power BI** — 4-page interactive dashboard
- **Excel** — data export and intermediary storage

## Project Structure
saas-revenue-leak-detector/
│
├── saas_revenue_leak.ipynb        # Main notebook — data generation + SQL
├── saas_revenue_leak_raw.xlsx     # Raw generated data (5 tables)
├── saas_revenue_leak_analysis.xlsx # Leak analysis output (4 sheets)
├── saas_revenue_leak_detection.pbix # Power BI dashboard
└── screenshots/                   # Dashboard screenshots
    ├── page1_executive_summary.png
    ├── page2_overdue_payments.png
    ├── page3_discount_billing_errors.png
    └── page4_customer_risk_drilldown.png

## Dashboard Pages
1. **Executive Summary** — Total leak amount, KPI cards, leak breakdown
2. **Overdue Payments** — 30/60/90+ day buckets, segment analysis
3. **Discount & Billing Errors** — By promo code, by plan, top offenders
4. **Customer Risk Drilldown** — Red/amber/green risk flagging, filterable

## Dataset
Synthetic dataset of 500 SaaS customers across 18 months generated using Python. Modelled on real SaaS billing patterns — realistic segment distribution, standard 30-day payment terms, and common promo code structures. Three leak types deliberately seeded to simulate real billing system issues.
