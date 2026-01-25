# Olist Customer Segmentation & High-Value Customer Prediction

## Overview
This project analyzes real-world Brazilian e-commerce transaction data from Olist
to understand customer purchasing behavior, segment customers based on value,
and identify high-value customers using interpretable models.

The focus is on **analytical reasoning and business insight**, not just modeling.

---

## Business Questions
- How different are customers in terms of purchasing behavior?
- Can we identify high-value customers using transaction history alone?
- Which behavioral signals most strongly indicate high customer value?

---

## Dataset
- Source: Brazilian E-Commerce Public Dataset by Olist (Kaggle)
- Size: ~100K orders, ~93K customers
- Tables used: orders, payments, customers

---

## Methodology
1. **Data Preparation**
   - Filtered delivered orders only
   - Aggregated payments at the order level
   - Built an analysis-ready order-level dataset

2. **Customer Feature Engineering (RFM)**
   - Recency: days since last purchase
   - Frequency: number of orders
   - Monetary: total spending

3. **Customer Segmentation**
   - Standardized RFM features
   - Applied K-Means clustering to identify behavioral segments

4. **High-Value Customer Prediction**
   - Defined high-value customers based on cluster characteristics
   - Trained a Logistic Regression model for interpretability
   - Analyzed coefficients to extract business insights

---

## Key Findings
- Customer value is highly skewed: most customers purchase once, while a small group drives disproportionate revenue.
- Monetary value is the strongest indicator of high-value customers.
- Recency matters: recent purchasers are more likely to be high-value.
- After controlling for monetary value, frequent low-value purchases are less predictive than fewer high-value purchases.

---

## Business Implications
- Early identification of high-spending customers enables targeted retention strategies.
- Retention efforts should prioritize **monetary value and recency**, not purchase frequency alone.
- This workflow can support customer lifetime value optimization and personalized engagement.

---

## Tools & Skills
- Python (Pandas, NumPy, Scikit-learn)
- Customer Segmentation (RFM, Clustering)
- Predictive Modeling (Logistic Regression)
- Business-Oriented Data Analysis
