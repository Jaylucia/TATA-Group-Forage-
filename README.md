# Business Analysis Report – Online Retail Store (TATA Group Project)

## 1. Introduction

The TATA Group engaged me as a Business Analyst to consult for an online retail store. The primary objective of the engagement was to analyze the company’s transactional data and extract actionable insights to inform strategic and marketing decisions for senior leadership. The analysis focuses on identifying revenue drivers, understanding customer behavior, and highlighting opportunities for expansion and growth.  

The leadership team is keen on understanding the business from two perspectives:

1. **Strategic and operational perspective (CEO lens)** – focusing on revenue trends, growth opportunities, and risk exposure.  
2. **Marketing and customer perspective (CMO lens)** – focusing on product performance, customer behavior, and market opportunities.

This report captures the methodology, analysis, key insights, and recommendations based on the available data.

---

## 2. Business Questions

Initially, a broader set of questions was developed to align with both the CEO and CMO perspectives. After refinement, the analysis focused on four high-priority analytical questions:

### CEO Questions (Strategic Lens)
1. Which countries and customer segments contribute the most to overall revenue, and how concentrated is this revenue?  
2. How has revenue trended over time, and are there clear seasonal patterns or growth/decline signals?  
3. What is the customer repeat purchase rate, and how does it impact total revenue?  
4. Who are our highest-value customers, and what proportion of revenue do they drive?

### CMO Questions (Customer and Market Lens)
1. Which products generate the highest revenue, and which drive the highest sales volume?  
2. What product combinations are frequently purchased together?  
3. Which countries show the strongest purchasing behavior (frequency, basket size, or value)?  
4. How does customer purchasing behavior vary across regions (product preferences, order size, or value)?

### Focused Analytical Questions
1. Time series revenue analysis for 2011 (CEO)  
2. Top 10 countries by revenue and quantity sold (CMO)  
3. Top 10 customers by revenue (CMO)  
4. Product demand by country to identify expansion opportunities (CEO)

---

## 3. Data Preparation and Cleaning

The dataset included the following fields: **Invoice Number, Stock Code, Quantity, Invoice Date, Unit Price, Customer ID, and Country**. Initial exploration revealed several data quality issues:

1. **Date Column:**  
   - Inconsistent formats were standardized using locale settings in Power BI.  
   - All dates were converted to a consistent DD/MM/YYYY format for accurate time-series analysis.

2. **Stock Code Column:**  
   - Mixed formats (numeric, alphabetic, alphanumeric) were removed as they were not required for the analysis.

3. **Invoice Number Errors:**  
   - Erroneous records were identified and removed after confirming no impact on analysis.

4. **Quantity Issues:**  
   - Negative quantities were filtered out to maintain accurate revenue and demand calculations.

5. **Customer ID Nulls:**  
   - Missing Customer IDs were labeled as “Guest” for identification but excluded from customer-level analysis.

6. **Data Model Enhancements:**  
   - Created DAX measures:  
     - **Total Revenue** = SUMX(Quantity × Unit Price)  
     - **Total Quantity** = SUM(Quantity)  
   - Built a **Calendar Table** to support aggregation by month and year.

---

## 4. Analysis and Findings

### 4.1 Revenue Trends – 2011 (CEO)

Objective: Analyze revenue trends for the year 2011 on a monthly basis to identify seasonality patterns and inform forecasting.

| Month      | Revenue ($M) |
|------------|--------------|
| January    | 0.69         |
| February   | 0.52         |
| March      | 0.75         |
| April      | 0.80         |
| May        | 0.88         |
| June       | 1.02         |
| July       | 1.10         |
| August     | 1.20         |
| September  | 1.35         |
| October    | 1.45         |
| November   | 1.51         |
| December   | 0.64         |

**Insights:**

- February had the lowest revenue ($0.52M), while November peaked at $1.51M.  
- There is a clear upward trend from August to November, followed by a sharp decline in December.  

**Implications:**

- Further investigation is recommended into seasonal factors (marketing campaigns, promotions, holidays) affecting revenue.  
- Understanding summer/autumn peak drivers can inform strategic decisions for inventory and promotions.

---

### 4.2 Top Revenue-Generating Countries (CMO)

Objective: Identify the top 10 countries by revenue and corresponding quantity sold, excluding the United Kingdom.

**Findings:**

- **Netherlands** generates the second-highest revenue outside the UK ($285K).  
- Revenue is concentrated in a few key international markets.  

**Implications:**

- Targeted marketing campaigns and expansion efforts should prioritize high-performing countries.  
- Quantity sold provides insights into demand versus pricing dynamics in each market.

---

### 4.3 Top Customers by Revenue (CMO)

Objective: Identify the top 10 customers by revenue for retention and engagement strategies.

**Findings:**

- Revenue is diversified; no single customer dominates.  
- Excluding guest transactions, the top 10 customers contribute a significant but not overwhelming portion of total revenue.

**Implications:**

- Low dependency on individual customers reduces revenue volatility risk.  
- High-value customers present an opportunity for loyalty programs and personalized engagement to maintain revenue consistency.

---

### 4.4 Product Demand by Country (CEO)

Objective: Visualize product demand (quantity sold) across countries to identify potential expansion opportunities.

**Findings:**

- Demand varies across countries, with several regions exhibiting high consumption levels.  
- Countries with large demand represent immediate opportunities for geographic expansion.

**Implications:**

- Expansion strategies should focus on high-demand countries.  
- Map visualization with bubble size and labels ensures visibility and facilitates executive decision-making.

---

## 5. Recommendations

1. Investigate seasonal revenue fluctuations to optimize marketing, promotions, and inventory management.  
2. Prioritize expansion efforts in high-demand countries identified in the analysis.  
3. Implement targeted retention strategies for high-value customers, including loyalty programs.  
4. Maintain data quality monitoring processes to address missing Customer IDs, negative quantities, and other anomalies.

---

## 6. Conclusion

The analysis demonstrates that revenue is influenced by seasonal trends, key international markets, and a diversified customer base. High-demand countries and top-performing customers provide actionable insights for expansion, marketing, and retention strategies. Leveraging these findings will enable leadership to make **data-driven decisions** for sustainable growth, improved customer satisfaction, and revenue optimization.

---

## 7. Next Steps

1. Integrate additional datasets (e.g., product categories, costs, promotions) for profitability analysis.  
2. Continuously monitor revenue trends to validate observed seasonal patterns.  
3. Deploy executive dashboards for ongoing review, allowing rapid identification of anomalies and opportunities.  
4. Explore predictive modeling for revenue forecasting and demand planning.

---
