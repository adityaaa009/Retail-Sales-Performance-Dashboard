![Dashboard Preview](https://github.com/adityaaa009/Retail-Sales-Performance-Dashboard/blob/main/Retail%20Sales%20Performance%20Dashboard.png)
# Retail Electronics Pricing & Profitability Dashboard
 
**Tool:** Tableau  
**Role:** Data Analyst Intern @ Capgemini India (Apr 2026 – Jun 2026)  
**Type:** Team case study — individual contribution documented below
 
## Overview
 
This dashboard was part of a 5-member team case study analyzing sales performance for a retail electronics chain operating across multiple stores and regions. The team worked from a relational dataset (Sales, Stores, Products) and split analysis across 10 business questions, two per member.
 
This repo documents my individual contribution: a product-focused dashboard answering two questions —
 
1. **How does product pricing affect sales volume?**
2. **What is the contribution of each category to total revenue?**
## Data Schema
 
The source data was structured across three related tables:
 
| Table | Columns |
|---|---|
| **Sales** | SaleID, Date, StoreID, ProductID, Quantity, Revenue |
| **Stores** | StoreID, Region, Manager |
| **Products** | ProductID, Category, Price, Cost |
 
**Relationships:**
- `Sales.StoreID → Stores.StoreID` (Many-to-One)
- `Sales.ProductID → Products.ProductID` (Many-to-One)
> **Note on data:** The dataset was provided for the internship case study and is not publicly shareable. This repo includes the schema, methodology, and dashboard screenshots for reference. No raw or sample data is included to avoid misrepresenting figures.
 
## Approach
 
To answer the two assigned questions, I built a single dashboard combining two cross-filtered visuals:
 
**1. Profit Margin vs. Total Profit (Bar Chart)**
- Ranked products by profit margin (%) and total profit ($) side by side
- Used to spot products that look profitable on margin alone but contribute little in absolute terms, and vice versa
**2. Average Selling Price vs. Sales Volume (Scatter Plot)**
- Plotted each product by average selling price against units sold
- Divided into four quadrants (high price/high sales, high price/low sales, low price/high sales, low price/low sales) using average lines as reference
- Used to visually identify pricing inefficiencies — e.g., products priced high but selling low volume, which flagged candidates for price correction
Both visuals were linked with dynamic cross-filtering, so clicking a product/category in one chart filters the other, enabling drill-down from category-level to SKU-level in a single click.
 
## Dashboard
 
![Dashboard Screenshot](./dashboard-screenshot.png)
 
**Key metrics on this view:**
- Revenue: $1.60M
- Total Profit: $466.94K
- Profit Margin: 29.24%
- Sales Volume: 2,311 units
- Average Selling Price: $691.10
## Key Insights
 
- Products in the **high-price/low-sales** quadrant (e.g., premium SKUs) were flagged as pricing-inefficient — high margin per unit but suppressed volume, suggesting room for price testing.
- Products in the **low-price/high-sales** quadrant were volume drivers but with thinner margins, useful for identifying which categories to bundle or upsell alongside.
- iPhone 15 Pro was the single largest contributor to total profit despite a mid-range profit margin (27%), showing that volume can outweigh margin percentage in absolute profit contribution.
- Category-level filtering showed a concentration of profit in a small number of SKUs, informing recommendations on where the product strategy team should focus pricing corrections first.
## What I'd Do Differently
 
- Add a time dimension (the Sales table included Date) to show whether pricing sensitivity changed seasonally
- Break out category contribution to revenue as its own dedicated visual rather than relying on filter interaction alone
