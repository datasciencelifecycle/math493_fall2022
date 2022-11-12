---
layout: page
title: Decision Tree Classifier
---


## Introduction
We built a decision tree model to see how effectively it could predict churners based on our data. Decision trees are constructed with nodes and branches. At each node, one of the features of our data is evaluated in order to split the observations in the training process.  We used different metrics, such as entropy or the gini index, to evaluate how to split the data. In the decision tree image, gini is used. A lower value means that the node is more pure.

We hypothesized that current tenure at the time an order was placed could be a valuable predictor, so we built a dataframe indexed by order. The model we built would use the tree to evaluate each order and predict whether the order was made by a churner or a non churner; we would then aggregate the predictions of all of the orders for a merchant and use that to predict whether the merchant was a churner.

## Model
We used the variables total_spent, num_skus, c_tenure, and days_since as our predictors in the model. (Possibly match definitions from Carrie’s page). We split the data into training and testing dataframes, 80% to train and 20% to test.. This produced a model that had 89% accuracy, but we discovered through a confusion matrix that the model predicted that every order came from a merchant that would not churn. All that this model told us was that in our test data, 89% of the merchants making the orders would not churn. 

![tree](https://user-images.githubusercontent.com/98668121/201447446-6cd6bb60-1f19-45bb-88bb-71d28a5774df.png)

## Evaluation
In both iterations of our decision tree, we used a confusion matrix to check how many errors were in our predictions. The two matrices are below and can be evaluated according to the confusion matrix.

![unnamed-2](https://user-images.githubusercontent.com/98668121/201447585-86be9ef7-31d7-4ce9-ae14-65657ba52a47.png)
![unnamed](https://user-images.githubusercontent.com/98668121/201447586-91b7079e-509d-49f1-8cd6-fe985f424569.png)

As an evaluation tactic, we input the same data into a random forest classifier model to confirm that we didn’t have errors in our data analysis. The random forest model confirmed that neither model could make helpful predictions for churners in our dataset. This can be traced back to feature selection, and shows that we did not select significant predictors in our initial analysis of merchant churn probability. Possible future steps could be selecting more features, or constructing more descriptive and interesting predictors. 

