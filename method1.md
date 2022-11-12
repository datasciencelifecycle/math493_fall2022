---
layout: page
title: Logistic Regression
---

We built a logistic regression model to predict whether a merchant will churn. We divide the dataset, 70% designated to training the models, and 30% designated to testing the models.

## First, we create a model aggregated around orders. 

These are the variables we use to make the model:
- `total_spent`, amount spent (Rp - Indonesia) per order
- `quantity_purchased`, number of items purchased per order
- `num_skus`, number of unique SKUs per order
- `c_tenure`, number of months the merchant has been purchasing at time of order
- `days_since`, number of days since the last order


<img width="584" alt="Screen Shot 2022-11-10 at 11 39 55 PM" src="https://user-images.githubusercontent.com/78067504/201389957-288d583e-7827-4297-8587-9c6c60dadfcb.png">

**This model has an accuracy of 0.89 in predicting churners on the testing dataset.**

The ROC curve for the model is below:

![Unknown](https://user-images.githubusercontent.com/78067504/201390245-6c832f03-7932-4dcd-9971-d7c8fc046426.png)

**This model has an accuracy of 0.32 in predicting churners on the full dataset.**

The ROC curve for the full dataset is below:

![Unknown-4](https://user-images.githubusercontent.com/78067504/201496680-7e17ecff-2237-4bdd-b9c7-1016b2dc36b4.png)


## Second, we create a model aggregated around merchants.

These are the variables we use to make the model:
- `avg_unique_sku_per_order`, average unique SKUs per order
- `avg_unique_top_cat_per_order`, average unique top categories per order
- `avg_unique_sub_cat_per_order`, average unique subcategories per order 
- `avg_spent_per_order`, average spent (Rp) per order
- `tenure_month`, number of months the merchant has been purchasing
- `avg_units_per_order`, average number items purchased per order


<img width="655" alt="Screen Shot 2022-11-11 at 11 01 55 AM" src="https://user-images.githubusercontent.com/78067504/201392013-e00352a7-34bb-4e83-a8a1-cfde805b4818.png">

**This model has an accuracy of 0.83 in predicting churners on the testing dataset.**

The ROC curve for the model is below:

![Unknown-2](https://user-images.githubusercontent.com/78067504/201392455-cb5e534b-6f37-499d-8ec5-52caeb9cb245.png)


**This model has an accuracy of 0.25 in predicting churners on the full dataset.**

The ROC curve for the full dataset is below:

![Unknown-3](https://user-images.githubusercontent.com/78067504/201496718-0d22b37a-e1a5-4729-8c8a-d8941fff73f8.png)
