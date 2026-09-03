# Olist E-Commerce Analytics: End-to-End Power BI Architecture

## Executive Summary
This project delivers a comprehensive, C-Level Power BI dashboard analyzing the operations of **Olist**, the largest department store in Brazilian e-commerce. By engineering a raw relational database into a robust Star Schema, this dashboard provides actionable insights into sales performance, logistics bottlenecks, customer sentiment, and financial health.

---

## Data Architecture & Engineering
Handling the Olist dataset required rigorous data cleansing and complex relationship modeling to ensure 100% data integrity before visualization.
* **Cartesian Explosion Resolution:** Solved a critical many-to-many relationship artifact between the `order_items` and `payments` tables that artificially inflated total revenue to $32M. Re-engineered the calculation via custom DAX and UI overlay techniques to reflect the true **$18.96M** net revenue.
* **Locale & Floating-Point Corrections:** Standardized monetary variables (e.g., `freight_value`) by enforcing US Locale settings in Power Query, preventing decimal miscalculations caused by regional comma/dot formatting.
* **DAX Time Intelligence:** Created custom DAX columns to convert native Portuguese/Spanish month string values into chronologically sorted, professional English formats.

---

## Interactive Dashboard Views & Key Insights

### 1. Executive Overview
Focuses on macro-level KPIs, spatial revenue distribution, and peak purchasing hours.
* **Insight:** São Paulo (SP) heavily dominates the market volume. Peak purchasing activity consistently occurs between 10:00 AM and 10:00 PM, indicating a strong correlation with regular waking hours rather than late-night shopping.
> *(View below)*
![Executive Overview](Page 1.png)

### 2. Sales & Category Analysis
Analyzes top-performing product categories and average freight costs against order volume.
* **Insight:** *Health & Beauty* and *Watches & Gifts* are the primary revenue drivers. The scatter plot reveals that high freight costs do not strictly deter order volume in premium categories.
> *(View below)*
![Sales & Category Analysis](Page 2.png)

### 3. Logistics & Customer Sentiment
Explores the critical relationship between delivery performance and customer review scores.
* **Insight:** There is a severe, quantifiable negative correlation between delivery delays and customer satisfaction. While the global average rating is 4.16, delayed orders drastically pull down the score, requiring immediate operational intervention in the slowest regions like AP and AM.
> *(View below)*
![Logistics & Customer Sentiment](Page 3.png)

### 4. Financial Health & Payments
Breaks down payment types, cash flow, and installment habits.
* **Insight:** Customers utilizing higher installment plans (up to 12 months) generate significantly larger average order values. Credit cards account for over 73% of all transactions, making seamless payment gateway integrations vital for Olist's cash flow.
> *(View below)*
![Financial Health & Payments](Page 4.png)

---

## Tech Stack
* **Data Visualization & UI/UX:** Power BI (Custom semantic coloring, SaaS-style layout, overlay cards)
* **Data Transformation:** Power Query, SQL
* **Data Modeling:** DAX, Star Schema design

*Designed and Developed by Esma Sahin*
