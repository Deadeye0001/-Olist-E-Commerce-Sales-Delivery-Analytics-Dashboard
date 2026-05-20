# -Olist-E-Commerce-Sales-Delivery-Analytics-Dashboard

## Project Overview
This project is an end-to-end Power BI dashboard built using the Brazilian E-Commerce Public Dataset by Olist. The project focuses on analyzing sales performance, customer behavior, delivery efficiency, and customer satisfaction to generate business insights for decision-making.

The dashboard helps businesses monitor KPIs, identify trends, and improve operational efficiency using data-driven insights.

---

# Problem Statement

The company operates a large multi-seller e-commerce marketplace and wants to improve:

- Revenue growth
- Customer retention
- Delivery performance
- Customer satisfaction
- Seller performance tracking

However, the business lacks a centralized reporting system that can provide actionable insights across sales, customers, logistics, and reviews.

This Power BI solution helps stakeholders monitor KPIs and identify areas requiring operational improvement.

---

# Dashboard Pages

## 1. Sales Performance Dashboard
Analyzes:
- Revenue trends
- Order volume
- Product category performance
- Seller contribution
- Monthly sales growth

## 2. Customer Behavior Dashboard
Analyzes:
- Repeat customers
- Customer purchasing patterns
- Average order value
- Customer segmentation
- Payment preferences

## 3. Delivery & Logistics Dashboard
Analyzes:
- Delivery delays
- Shipping performance
- Freight costs
- State-wise delivery analysis
- Logistics efficiency

## 4. Customer Satisfaction Dashboard
Analyzes:
- Review scores
- Satisfaction trends
- Low-rated orders
- Correlation between delays and ratings
- Customer feedback insights

---

# Business Questions & Insights

## Sales Performance Questions

### 1. How many total orders were successfully delivered?
**Insight:**  
The dashboard tracks delivered orders separately from canceled or unavailable orders to measure actual business performance.

### 2. Which product categories generate the highest revenue?
**Insight:**  
Top-performing product categories contribute a major share of total revenue and should receive increased inventory and marketing focus.

### 3. Which sellers contribute the most revenue?
**Insight:**  
High-performing sellers can be identified and rewarded while low-performing sellers can be monitored for improvement.

### 4. What are the monthly sales trends?
**Insight:**  
The dashboard identifies seasonal demand patterns and growth periods that help in forecasting and inventory planning.

### 5. Which states generate the highest number of orders?
**Insight:**  
Regional demand analysis helps businesses optimize marketing campaigns and delivery operations.

---

## Customer Behavior Questions

### 6. How many repeat customers does the platform have?
**Insight:**  
Repeat customer analysis helps measure customer loyalty and retention.

### 7. What is the average order value?
**Insight:**  
Average order value helps evaluate customer spending behavior and pricing strategies.

### 8. Which payment methods are most preferred?
**Insight:**  
Understanding payment preferences helps optimize checkout experiences and payment partnerships.

### 9. Which customers generate the highest lifetime value?
**Insight:**  
High-value customers can be targeted through loyalty programs and personalized marketing.

### 10. What are the customer purchase trends over time?
**Insight:**  
The dashboard identifies customer buying cycles and growth in customer engagement.

---

## Delivery & Logistics Questions

### 11. Which states experience the highest delivery delays?
**Insight:**  
Regional delivery bottlenecks help identify areas requiring logistics optimization.

### 12. What is the average delivery time?
**Insight:**  
Delivery performance monitoring helps improve operational efficiency and customer experience.

### 13. How does freight cost impact revenue?
**Insight:**  
Freight analysis helps balance profitability and shipping efficiency.

### 14. Which orders were delivered late?
**Insight:**  
Late delivery tracking helps reduce customer dissatisfaction and operational delays.

### 15. What is the relationship between shipping time and customer satisfaction?
**Insight:**  
Longer shipping times generally result in lower customer ratings.

---

## Customer Satisfaction Questions

### 16. What is the average review score?
**Insight:**  
The dashboard measures overall customer satisfaction using review scores.

### 17. Which product categories receive the lowest ratings?
**Insight:**  
Poorly rated categories indicate product quality or service issues.

### 18. How do delayed deliveries affect review ratings?
**Insight:**  
Customers are more likely to provide low ratings when deliveries are delayed.

### 19. Which sellers receive the best customer ratings?
**Insight:**  
Seller-level review analysis helps identify reliable and high-quality sellers.

### 20. What percentage of reviews are positive vs negative?
**Insight:**  
Review sentiment trends help businesses monitor customer perception.

---

# Data Model

The project follows a Star Schema model.

## Fact Tables
- fact_orders
- fact_order_items
- fact_payments
- fact_reviews

## Dimension Tables
- dim_customers
- dim_products
- dim_sellers
- dim_date
- dim_geolocation

---

# Tools & Technologies Used

| Tool | Purpose |
|------|----------|
| Microsoft Excel | Initial data exploration |
| Power Query | Data cleaning and transformation |
| Power BI | Dashboard creation and reporting |
| DAX | KPI calculations and business metrics |
| Data Modeling | Relationship building and schema design |

---

# Data Cleaning & Transformation

The following preprocessing steps were performed:

- Removed duplicate records
- Handled null values
- Renamed tables into fact and dimension format
- Applied proper data types
- Standardized text formatting using Trim, Clean, and Proper Case
- Created relationships between tables
- Built calculated columns and DAX measures

---

# Sample DAX Measures

## Total Orders
```DAX
Total_Orders =
CALCULATE(
    DISTINCTCOUNT(fact_orders[order_id]),
    fact_orders[order_status] = "delivered"
)
```

## Total Revenue
```DAX
Total_Revenue =
SUM(fact_order_items[price])
```

## Average Order Value
```DAX
Average_Order_Value =
DIVIDE([Total_Revenue], [Total_Orders])
```

## Repeat Customers
```DAX
Repeat_Customers =
CALCULATE(
    DISTINCTCOUNT(fact_orders[customer_id]),
    FILTER(
        VALUES(fact_orders[customer_id]),
        CALCULATE(COUNT(fact_orders[order_id])) > 1
    )
)
```

---

# Key Insights From the Dashboard

- A small group of sellers contributes a large portion of total revenue.
- Delayed deliveries strongly impact customer satisfaction.
- Some product categories consistently outperform others in both revenue and reviews.
- Repeat customers contribute significantly to total sales.
- Freight costs vary heavily across states and affect profitability.

---

# Project Learning Outcomes

Through this project, the following skills were practiced:

- Data Cleaning
- Data Modeling
- DAX Calculations
- Dashboard Design
- Business Analysis
- KPI Development
- Visualization Best Practices
- End-to-End Power BI Workflow

---

# File Included

- `ecommerce_analysis.pbix`

---

# Author

Amit Singh Bisht

Data Analyst | Power BI | SQL | Excel | Python
