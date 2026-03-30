# Olist Customer Segmentation & High-Value Customer Prediction (RFM)

## Key Results

- Customer value is highly skewed: most customers purchase once, while a small segment drives disproportionate revenue  
- RFM-based clustering reveals distinct segments (high-spend, repeat buyers, dormant users) with different business strategies  
- An interpretable model shows that **monetary is the dominant driver of high-value customers**, with recency and frequency adding supporting signals  

---

## Business Question

How can we identify high-value customers and segment the customer base to support targeted marketing and retention strategies?

---

## What This Solves

In e-commerce marketplaces, customer value is not evenly distributed:

- most customers purchase once and do not return  
- a small minority contributes a large share of total revenue  

This creates a need to:

- identify high-value customers early  
- protect high-revenue segments  
- design segment-specific retention and marketing strategies  

---

## Approach

This project transforms raw multi-table transaction data into customer-level insights:

1. **Build an order-level dataset**
   - filter to delivered orders  
   - aggregate payments per order (avoid double counting)  
   - join customer identifiers  

2. **Engineer RFM features (Recency, Frequency, Monetary)**
   - recency_days  
   - number of orders  
   - total spend  

3. **Segment customers using KMeans clustering**
   - standardize features  
   - identify natural behavioral groups  

4. **Define and model high-value customers**
   - label the highest-value segment  
   - train logistic regression for interpretable classification  

---

## Segmentation Results

Clustering reveals distinct customer segments:

- **High-Monetary Segment (High-Value Customers)**  
  - very high spend (~$1,161 avg)  
  - low purchase frequency  
  → high-ticket buyers  

- **Repeat Buyers**  
  - higher frequency (~2.1 orders)  
  - moderate spend (~$290)  
  → recurring customers  

- **Recent Low-Value Majority**  
  - large group with low spend and recent activity  

- **Dormant Customers**  
  - high recency (inactive for long periods)  
  → likely churned  

This shows that “high value” is not one-dimensional and requires different strategies by segment.

---

## High-Value Customer Prediction

To operationalize segmentation, the highest-value cluster is defined as the “high-value” class.

A logistic regression model is trained using RFM features to identify similar customers.

### Key Drivers

- **Monetary (strong positive effect)** → higher spend strongly increases high-value probability  
- **Recency (negative effect)** → less recent activity reduces value probability  
- **Frequency (context-dependent)** → adds nuance once spend is controlled  

The model is used for **interpretation and prioritization**, not as a production prediction system.

---

## Business Takeaways

This workflow enables:

- **VIP protection strategies** for high-spend customers  
- **LTV growth programs** for repeat buyers  
- **Win-back campaigns** for dormant customers  

Instead of treating all customers equally, teams can allocate resources based on customer value segments.

---

## Dataset

This project uses the Olist e-commerce dataset, combining multiple tables:

- `orders`  
- `payments`  
- `customers`  

The data is transformed into a clean customer-level dataset for analysis.

---

## Tools

- Python  
- Pandas  
- NumPy  
- Scikit-learn (KMeans, Logistic Regression)  
- Jupyter Notebook  
