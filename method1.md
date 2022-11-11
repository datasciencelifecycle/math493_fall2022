---
layout: page
title: Logistic Regression
---

We build a logistic regression model to predict whether a merchant will churn. 

First, we create a model aggregated around orders. 
These are the variables we use to make the model:
- Amount spent (Rp) per order (total_spent)
- Number of items purchased per order (quantity_purchased)
- Number of unique SKUs per order (num_skus)
- Number of months the merchant has been purchasing at time of order (c_tenure)
- Number of days since the last order (days_since)



