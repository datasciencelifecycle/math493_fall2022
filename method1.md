---
layout: page
title: Logistic Regression
---

We build a logistic regression model to predict whether a merchant will churn. We devide the dataset, 70% designated to training the models, and 30% designated to testing the models.

First, we create a model aggregated around orders. 
These are the variables we use to make the model:
- Amount spent (Rp) per order (total_spent)
- Number of items purchased per order (quantity_purchased)
- Number of unique SKUs per order (num_skus)
- Number of months the merchant has been purchasing at time of order (c_tenure)
- Number of days since the last order (days_since)

<img width="584" alt="Screen Shot 2022-11-10 at 11 39 55 PM" src="https://user-images.githubusercontent.com/78067504/201389957-288d583e-7827-4297-8587-9c6c60dadfcb.png">

This model has accuracy of 0.89 in predicting churners on the testing dataset.

The ROC curve for the model is below:
![Unknown](https://user-images.githubusercontent.com/78067504/201390245-6c832f03-7932-4dcd-9971-d7c8fc046426.png)

Second, we create a model aggregated around merchants.
These are the variables we use to make the model:
- Average unique SKUs per order (avg_unique_sku_per_order)
- Average unique top categories per order (avg_unique_top_cat_per_order)
- Average unique subcategories per order (avg_unique_sub_cat_per_order)
- Average spent(Rp) per order (avg_spent_per_order)
- Number of months the merchant has been purchasing (tenure_month)
- Average number items purchased per order (avg_units_per_order)


Optimization terminated successfully.
         Current function value: 0.277625
         Iterations 8
                               Results: Logit
============================================================================
Model:                   Logit               Pseudo R-squared:    0.429     
Dependent Variable:      churner             AIC:                 158.0306  
Date:                    2022-11-11 05:44    BIC:                 179.4635  
No. Observations:        263                 Log-Likelihood:      -73.015   
Df Model:                5                   LL-Null:             -127.92   
Df Residuals:            257                 LLR p-value:         4.4949e-22
Converged:               1.0000              Scale:               1.0000    
No. Iterations:          8.0000                                             
----------------------------------------------------------------------------
                              Coef.  Std.Err.    z    P>|z|   [0.025  0.975]
----------------------------------------------------------------------------
avg_unique_sku_per_order      0.1482   0.0874  1.6953 0.0900 -0.0231  0.3195
avg_unique_top_cat_per_order -0.3932   0.3856 -1.0196 0.3079 -1.1490  0.3626
avg_unique_sub_cat_per_order  0.0689   0.2633  0.2619 0.7934 -0.4470  0.5849
avg_spent_per_order          -0.0000   0.0000 -0.1845 0.8536 -0.0000  0.0000
tenure_month                 -0.4362   0.0672 -6.4886 0.0000 -0.5679 -0.3044
avg_units_per_order           0.0287   0.0077  3.7384 0.0002  0.0137  0.0437
============================================================================

