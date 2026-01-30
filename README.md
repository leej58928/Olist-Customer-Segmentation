# Olist Customer Segmentation & High-Value Customer Prediction (RFM)

## Overview  
This project turns raw multi-table Olist e-commerce transactions into actionable customer segments and a simple, interpretable model that identifies high-value customers.

Instead of treating all customers as homogeneous, the workflow uses RFM features (Recency, Frequency, Monetary) to uncover behavioral segments and translate them into business decision signals.

The notebook follows a narrative format:  
**Question → Method → Output → Interpretation → Next Step**

---

## Business Framing  
In marketplaces like Olist, customer value is typically imbalanced:
- most customers purchase once and never return  
- a small minority contributes disproportionate revenue  

This means growth and retention strategy should focus on:
1) identifying high-value customers early  
2) protecting high-spend revenue segments  
3) designing cluster-specific marketing and CX programs  

---

## Objective  
1. Build an analysis-ready dataset from raw Olist tables (orders, payments, customers)  
2. Engineer customer-level RFM features  
3. Segment customers using clustering to uncover natural behavior groups  
4. Define a “high-value customer” segment  
5. Train an interpretable model (Logistic Regression) to predict high-value customers using RFM signals  

---

## Dataset & Preparation  
Raw Olist data is distributed across multiple tables.  
This project builds a clean order-level table by:
- filtering delivered orders only  
- aggregating payment records per order to avoid double counting  
- joining customer identifiers  

---

## Analytical Approach  

### 1) RFM Feature Engineering  
Customer-level features:
- **Recency**: days since last purchase  
- **Frequency**: number of unique orders  
- **Monetary**: total spend  

A reference date (day after the most recent purchase) is used for consistent recency calculation.

---

### 2) Customer Segmentation (KMeans Clustering)  
Because RFM variables have different scales, features are standardized before clustering.

Clustering reveals distinct behavioral groups, including:
- a high-monetary segment (high-ticket buyers)
- a repeat-buyer segment
- low-value majority segments (recent vs dormant)

This segmentation enables cluster-specific marketing and retention strategy.

---

### 3) High-Value Customer Prediction (Logistic Regression)  
Segmentation explains *what groups exist*, but businesses often need to predict who is likely to become high-value.

This project:
- defines the highest monetary cluster as "high value"
- trains logistic regression to predict high-value customers using RFM signals
- interprets coefficients as business drivers

---

## Key Insights  
- Marketplace customer value is highly imbalanced: most customers purchase once, while a small segment drives revenue.  
- Clustering uncovers distinct segments with different business strategies (VIP protection vs repeat conversion vs win-back).  
- Monetary is the strongest driver of high-value classification; recency matters; frequency adds nuance once spend is controlled.  

---

## Insight → Action Translation  
This workflow supports real business programs such as:
- identifying VIP high-ticket customers for premium CX and retention  
- prioritizing cross-sell and upsell for high-monetary buyers  
- reactivating dormant customers with controlled-cost win-back campaigns  
- using model scores to focus marketing resources on top-value cohorts  

---

## Tools & Techniques  
- Python (Pandas, NumPy)  
- Feature engineering (RFM)  
- KMeans clustering + StandardScaler  
- Logistic Regression (interpretable classification)  
- Model interpretation via coefficients  

---

## Author  
Jihoo Lee — Data Analytics Portfolio Project
