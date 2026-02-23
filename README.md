
# Superstore Sales Analytics — End-to-End Data Analysis Project

## Project Overview
This project performs a complete end-to-end sales analysis on the Superstore dataset 
covering 9,994 transactions across 4 years (2014–2017) in the United States. 
The goal was to identify profitability problems, understand what's driving them, 
and provide actionable business recommendations.

## Business Problem
Superstore is growing in revenue but struggling with profitability. 
The business needed answers to:
- Which products and regions are losing money?
- Are discounts helping or hurting profit?
- Which customer segments are most valuable?
- Are there seasonal patterns to capitalize on?

## Tools Used
- Python (Pandas, Matplotlib, Seaborn) — data cleaning and exploratory analysis
- Power BI — 3-level interactive dashboard

## Dataset
- Source: Kaggle — Superstore Dataset
- 9,994 rows, 21 columns
- Period: 2014–2017

---

## Key Findings

### Business Overview
- Total Revenue: $2.3M | Total Profit: $286K | Profit Margin: 12.47%
- Overall margin is below the healthy retail benchmark of 15–30%
- Revenue grew 56% from 2015–2017 but profit margin declined in 2017

### Product Performance
- Furniture category generates $742K in sales but only 2.49% profit margin
- Tables (-8.56%), Bookcases (-3.02%) and Supplies (-2.55%) are 
  actively loss-making sub-categories
- Labels (44.4%), Paper (43.4%) and Envelopes (42.3%) are 
  the highest margin sub-categories

### Discount Impact
- Discounts above 20% consistently produce negative average profit
- Orders with 50% discount lose approximately $300 on average
- Discounting strategy is a major driver of the low overall margin

### Regional Performance
- West region leads with 14.94% profit margin
- Central region significantly underperforms at only 7.92% margin
- Nearly a 2x margin gap between best and worst performing regions

### Customer Segments
- Consumer segment drives highest revenue ($1.2M) but lowest margin (11.55%)
- Home Office has highest margin (14.03%) despite lowest sales volume
- Untapped growth opportunity exists in the Home Office segment

### Seasonal Trends
- Q1 (January–February) is consistently the weakest period
- November is peak month at $350K in sales
- Q4 drives disproportionate revenue — strong seasonal pattern

---

## Business Recommendations

**1. Cap Discounts at 20%**
Discounts above 20% destroy profit margins. Implement a company-wide 
discount cap with senior approval required for any exception.

**2. Review Tables and Bookcases Product Lines**
Both sub-categories lose money on every sale. Renegotiate supplier 
costs, increase pricing, or consider discontinuing these lines.

**3. Invest in Growing the Home Office Segment**
Highest margin segment but lowest volume. A targeted marketing 
campaign toward freelancers and small business owners could 
significantly improve overall profitability.

**4. Investigate Central Region Operations**
7.92% margin vs 14.94% in the West is an unacceptable gap. 
Conduct a detailed audit of pricing, discounting and product 
mix in the Central region immediately.

**5. Concentrate Marketing and Inventory in Q4**
Shift promotional spend and inventory investment toward Q3–Q4 
to maximize the seasonal demand window and reduce Q1 carrying costs.

---

## Dashboard
3-level interactive Power BI dashboard:
- **Level 1 — Executive Overview:** KPIs, yearly trends, regional margins
- **Level 2 — Category & Segment Analysis:** Product profitability, 
  discount impact, segment comparison
- **Level 3 — Deep Dive / Root Cause:** State-level profit map, 
  scatter analysis, seasonal trends, loss-maker identification

---

## Project Structure
superstore-sales-analytics/
├── data/
│   └── superstore_cleaned.csv
├── notebooks/
│   └── superstore_analysis.ipynb
├── dashboard/
│   └── superstore_dashboard.pbix
└── README.md
