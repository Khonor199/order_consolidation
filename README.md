## Project Overview

# Order_consolidation
Analysis of order consolidation into a single cargo unit by the supplier. Its impact on delivery time.

# Analysis of Supplier Order Fulfillment Times

The goal of this research is to identify key issues related to delivery delays caused by the consolidation of shipments by suppliers. The study focuses on analyzing the impact of cargo formation time (`form_days`) on delivery delays and determining critical thresholds where delays become significant.

**Main Problem:**  
Suppliers accumulate orders, set delivery dates, and then send them consolidated, which leads to delays for "older" orders that are waiting in the queue for shipment.

---

## Research Objectives

1. **Determine if there is a relationship between order consolidation and delivery delays.**
2. **Identify the impact of consolidation on delays for "old" orders.**
3. **Find the critical threshold value for `form_days`, after which delays become significant.**

---

## Hypotheses

### Stage 1:
- **Null Hypothesis (H₀):** Consolidation of orders does not increase delivery delays.
- **Alternative Hypothesis (H₁):** Consolidation of orders increases delivery delays.

**Result:** Consolidation as such does not increase overall delivery delays. Differences between consolidated and non-consolidated orders are statistically insignificant.

---

### Stage 2:
- **Null Hypothesis (H₀):** Consolidation of orders does not increase delays for "old" orders.
- **Alternative Hypothesis (H₁):** Consolidation of orders increases delays for "old" orders.

**Result:** The alternative hypothesis is confirmed. "Old" orders in consolidated shipments experience statistically significant delays.

---

### Stage 3:
- **Objective:** Find the threshold value for `form_days` after which delivery delays become critical.

**Result:** The critical threshold for cargo formation time is **6 days**. Delays for "old" orders significantly increase when `form_days` exceeds this value.

---

## Methodology

1. **Data Source:**  
   Data on orders, suppliers, product categories, distribution centers, and time metrics were extracted from the company's database using an SQL query.

2. **Data Processing:**  
   - Calculation of time metrics (`planned_days`, `actual_days`, `delay_days`, `form_days`).  
   - ABC classification of suppliers based on GMV.  
   - Separation of consolidated and non-consolidated orders.  

3. **Data Analysis:**  
   - Visualization of time metric distributions.  
   - Hypothesis testing using statistical methods (Mann-Whitney U-test).  
   - Determination of the `form_days` threshold.  

4. **Machine Learning:**  
   - Use of AutoML to identify the most important factors affecting delivery delays.  
   - Interpretation of results using SHAP analysis.  

---

## Key Results

1. **Main Findings:**
   - Consolidation as such does not increase overall delivery delays.  
   - However, "old" orders in consolidated shipments experience more delays.  
   - The critical threshold for cargo formation time is **6 days**.  

2. **Business Recommendations:**
   - Limit cargo formation time to **5 days**.  
   - Separate "old" and "new" orders during consolidation.  
   - Accelerate order processing for suppliers in category A (44 suppliers account for 74% of revenue).  

3. **Priority Areas:**
   - Focus on major suppliers (category A).  
   - Optimize top product categories (top 10 categories by GMV).  
   - Monitor regional centers with the highest order flow.  

---

## Tools Used

- **Programming Language:** Python  
- **Libraries:** pandas, numpy, scipy, seaborn, matplotlib, shap, and other 
- **Statistical Methods:** Mann-Whitney U-test, SHAP analysis  
- **Visualization Tools:** Matplotlib, Seaborn  

---
