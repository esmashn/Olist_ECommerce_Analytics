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

<img width="1507" height="846" alt="Page 1" src="https://github.com/user-attachments/assets/a2595448-a858-49ea-9046-ed6de8d84706" />


### 2. Sales & Category Analysis
Analyzes top-performing product categories and average freight costs against order volume.
* **Insight:** *Health & Beauty* and *Watches & Gifts* are the primary revenue drivers. The scatter plot reveals that high freight costs do not strictly deter order volume in premium categories.
  
<img width="1500" height="844" alt="Page 2" src="https://github.com/user-attachments/assets/647ce472-811e-4947-8103-bcfae65360e1" />


### 3. Logistics & Customer Sentiment
Explores the critical relationship between delivery performance and customer review scores.
* **Insight:** There is a severe, quantifiable negative correlation between delivery delays and customer satisfaction. While the global average rating is 4.16, delayed orders drastically pull down the score, requiring immediate operational intervention in the slowest regions like AP and AM.

<img width="1501" height="845" alt="Page 3" src="https://github.com/user-attachments/assets/433d9de1-3fcb-49e4-9034-354be35a9108" />


### 4. Financial Health & Payments
Breaks down payment types, cash flow, and installment habits.
* **Insight:** Customers utilizing higher installment plans (up to 12 months) generate significantly larger average order values. Credit cards account for over 73% of all transactions, making seamless payment gateway integrations vital for Olist's cash flow.

<img width="1507" height="845" alt="Page 4" src="https://github.com/user-attachments/assets/5435d98a-2a28-41e6-8b9d-0067c0e47faf" />

---

## Tech Stack
* **Data Visualization & UI/UX:** Power BI (Custom semantic coloring, SaaS-style layout, overlay cards)
* **Data Transformation:** Power Query, SQL
* **Data Modeling:** DAX, Star Schema design

*Designed and Developed by Esma Sahin*
