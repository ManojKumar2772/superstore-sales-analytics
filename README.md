# Superstore Sales Analytics — End-to-End Data Analysis Project

## Project Overview
This project performs a complete end-to-end sales analysis on the 
Superstore dataset covering 9,994 transactions across 4 years 
(2014–2017) in the United States. The project combines descriptive 
analytics, customer segmentation using machine learning, and 
predictive sales forecasting to deliver actionable business insights.

## Tools & Technologies
-- SQL (SQLite) — data extraction and validation
- Python (Pandas, Matplotlib, Scikit-learn, Prophet) — analysis and ML
- Power BI — 4-page interactive dashboard

## Dataset
- Source: Kaggle — Superstore Dataset
- 9,994 rows, 21 columns
- Period: 2014–2017
- 793 unique customers

---


### Pipeline
Raw Data → SQLite Database → SQL Queries → 
Python Analysis → Power BI Dashboard
## Part 0 — SQL Layer (SQLite)
### Why SQL First
In real-world analytics, data lives in databases before 
it reaches analysts. This project replicates that workflow 
by loading the Superstore dataset into a SQLite database 
and answering all 6 business questions through SQL before 
validating with Python.

### Business Questions Answered in SQL

**1. Business Overview**
- Total Revenue: $2.3M | Total Profit: $286K | 
  Margin: 12.47%

**2. Category Performance**
- Technology leads at 17.39% margin
- Furniture trails at only 2.49% margin

**3. Sub-Category Performance**
- Labels (44.4%), Paper (43.4%) highest margin
- Tables (-8.56%), Bookcases (-3.02%) loss-making

**4. Discount Impact**
- Average profit turns negative beyond 20% discount
- 50% discount orders lose $310 per order on average

**5. Regional Performance**
- West leads at 14.94% | Central weakest at 7.92%

**6. Yearly Trend**
- Revenue grew from $484K (2014) to $733K (2017)
- Margin improved 2014-2016 then declined in 2017

### Advanced Query — Top 5 Most Profitable Customers

| Rank | Customer ID | Total Profit |
|------|-------------|--------------|
| 1 | TC-20980 | $8,981 |
| 2 | RB-19360 | $6,976 |
| 3 | SC-20095 | $5,757 |
| 4 | HL-15040 | $5,622 |
| 5 | AB-10105 | $5,444 |

### SQL Validation
All SQL results confirmed matching Python analysis — 
proving consistency across tools and validating 
analytical approach.

### Tools
- SQLite (via Python sqlite3 library)
- pandas read_sql_query for result display
- Jupyter Notebook for documentation
```

---

**Also update your CV skills section:**

Under Languages & Tools add:
```
SQLite
```

And update the project title line from:
```
Python | Power BI | Scikit-learn | Prophet
```
To:
```
Python | SQL | Power BI | Scikit-learn | Prophet
## Part 1 — Sales Performance Analysis

### Business Questions Answered
1. Which product categories and sub-categories are profitable?
2. Are discounts helping or hurting profit margins?
3. Which regions are underperforming?
4. Which customer segments are most valuable?
5. Are there seasonal patterns to capitalize on?
6. What is the overall business health and trend?

### Key Findings

**Business Overview**
- Total Revenue: $2.3M | Total Profit: $286K | 
  Profit Margin: 12.47%
- Overall margin is below the healthy retail benchmark of 15-30%
- Revenue grew 56% from 2015-2017 but profit margin declined 
  in 2017 — suggesting margin is being sacrificed for volume

**Product Performance**
- Furniture generates $742K in sales but only 2.49% profit margin
- Tables (-8.56%), Bookcases (-3.02%) and Supplies (-2.55%) are 
  actively loss-making sub-categories
- Labels (44.4%), Paper (43.4%) and Envelopes (42.3%) are the 
  highest margin sub-categories

**Discount Impact**
- Discounts above 20% consistently produce negative average profit
- Orders with 50% discount lose approximately $300 per order
- Discounting is a major driver of the low overall profit margin

**Regional Performance**
- West region leads with 14.94% profit margin
- Central region underperforms at only 7.92% margin
- Nearly 2x margin gap between best and worst regions

**Customer Segments**
- Consumer segment drives highest revenue ($1.2M) but 
  lowest margin (11.55%)
- Home Office has highest margin (14.03%) despite lowest 
  sales volume — untapped growth opportunity

**Seasonal Trends**
- Q1 (January-February) is consistently the weakest period
- November is peak month at $350K in sales
- Q4 drives disproportionate revenue

---

## Part 2 — RFM Customer Segmentation

### Methodology
- Calculated Recency, Frequency and Monetary values for 
  793 unique customers
- Scored each customer 1-4 on each RFM dimension using 
  quantile-based scoring (pd.qcut)
- Applied rule-based segmentation using RFM composite scores
- Validated segments using KMeans clustering (K=4) confirmed 
  by Elbow Method
- Standardized features using StandardScaler before clustering

### Customer Segments

| Segment | Customers | Avg Recency | Avg Frequency | Avg Monetary |
|---------|-----------|-------------|---------------|--------------|
| Champion | 200 | 39 days | 19 orders | $4,933 |
| Loyal Customer | 289 | 112 days | 13 orders | $3,358 |
| At Risk | 182 | 164 days | 9 orders | $1,374 |
| Lost | 122 | 379 days | 6 orders | $739 |

### Key Finding
KMeans clustering confirmed rule-based RFM segments with natural 
mathematical groupings. Minor disagreements between methods 
highlight borderline customers worth monitoring closely.

---

## Part 3 — Sales Forecasting (Facebook Prophet)

### Methodology
- Aggregated daily sales from 9,994 transactions
- Applied Facebook Prophet time series forecasting model
- Forecasted 365 days into 2018
- Analyzed trend, weekly seasonality and yearly seasonality 
  components automatically detected by Prophet

### Key Findings

**Trend**
- Daily average sales projected to grow from $1,400 in 2014 
  to $2,600+ by 2019
- Confirms strong and consistent business growth momentum

**Weekly Seasonality**
- Wednesday is the weakest sales day (-$1,000 below average)
- Monday and Friday are the strongest performing days
- Operational insight — avoid major promotions on Wednesdays

**Yearly Seasonality**
- January-February are deeply negative periods
- Strong surge from September through November
- November is the peak month — consistent with manual analysis
- Q4 seasonal pattern confirmed by both manual EDA and 
  Prophet automatically



## Business Recommendations

**1. Cap Discounts at 20%**
Discounts above 20% destroy profit margins. Implement a 
company-wide discount cap with senior approval required 
for any exception.

**2. Review Tables and Bookcases Product Lines**
Both sub-categories lose money on every sale. Renegotiate 
supplier costs, increase pricing, or consider discontinuing 
these lines entirely.

**3. Invest in Growing the Home Office Segment**
Highest margin segment but lowest volume. A targeted marketing 
campaign toward freelancers and small business owners could 
significantly improve overall profitability.

**4. Investigate Central Region Operations**
7.92% margin vs 14.94% in the West is an unacceptable gap. 
Conduct a detailed audit of pricing, discounting and product 
mix in the Central region immediately.

**5. Concentrate Marketing and Inventory in Q4**
Shift promotional spend and inventory investment toward Q3-Q4 
to maximize the seasonal demand window and reduce Q1 
carrying costs.

**6. Launch Retention Campaign for At Risk Customers**
182 customers averaging 164 days since last purchase are 
drifting away. A personalized win-back campaign with targeted 
offers could recover significant revenue before they become Lost.

**7. Protect and Reward Champions**
200 Champion customers average $4,933 in spending. A loyalty 
rewards program targeting this group protects the most 
valuable revenue source.

**8. Avoid Wednesday Promotions**
Prophet weekly analysis reveals Wednesday as the worst sales 
day. Shift promotional activity to Monday and Friday for 
maximum impact.

---

## Dashboard
4-page interactive Power BI dashboard:
- **Page 1 — Executive Overview:** KPIs, yearly trends, 
  regional margins
- **Page 2 — Category & Segment Analysis:** Product 
  profitability, discount impact, segment comparison
- **Page 3 — Deep Dive / Root Cause:** State-level profit 
  map, scatter analysis, seasonal trends, loss-maker 
  identification
- **Page 4 — Customer Segmentation:** RFM segments, 
  KMeans clusters, monetary and recency comparison




