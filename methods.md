---
layout: page
title: Methods
---

**Data**

### The Dataset

To perform our analysis, we used FMCG data from an Indonesian distribution center. The raw data contained the following attributes
- `order_id`, which identifies which order the particular `sku_id` was placed (categorical),
- `placed_at`, an attribute with information on when an order is placed within the time-series (datetime), 
- `merchant_id`, an attribute where each merchant was given a specific identification number (categorical),
- `sku_id`,  an attribute that distinguishes which good was purchased, (categorical)
- `top_cat_id`, an overarching umbrella category of good such as "cooking", identified by a corresponding number (categorical),
- `sub_cat_id`, a more specific category where the good was classified (categorical),
- `qty`, the amount of which a good has been purchased (numerical), and finally
- `price`, the price paid for one particular `sku_id` at time `placed_at`.

### Preprocessing

We took the data and aggregated by individual order, keeping the `merchant_id` attribute. For the model-building process, we needed binary variable that determined whether or not a merchant was a 'churner'. To determine if this merchant is a churner, we selected merchants who were contained in the data set but had not logged any orders for the final two months of the data.

We grouped by the `order_id` and used the `qty` attribute to find the total quantity of goods purchased in a given order as `quantity_purchased`, and also determined the number of unique SKU's in each order as `num_sku`. We then found the total order price to determine how much was spent on a given order, as `total_spent`.

### Tools

Most of our work was done in a jupyter notebook [`Churning_ID.ipynb`](https://colab.research.google.com/drive/1W0jr3GvOdy2G07TeULOVP9usARw0QYT_?usp=sharing). We made use of the following packages:
- `pandas`
- `numpy`
- `sklearn'
- `scipy.stats`

### Workflow

Our analysis featured an iterative process of data preparation, modeling, model evaluation. We found some of our assumptions in the modeling process required adjusting our data preparation.
