# Introduce
Imagine we are the member of a Retail/Telcos company and we wants to fuel its growth by Data-driven approach. This Series has 6 part research about 6 core problem of business:
- Part 1: [Customer Segmentation](https://github.com/ToanToan110/CustomerSegmentation)
- Part 2: [Churn Prediction](https://github.com/ToanToan110/ChurnPrediction)
- Part 3: [Customer's Life Time Value](https://github.com/ToanToan110/CustomerLifeTimeValue)
- Part 4: [Sales Prediction](https://github.com/ToanToan110/SalesPrediction)
- Part 5: [Market ResponseModel](https://github.com/ToanToan110/MarketResponseModel)
- Part 6: [A/B Testing](https://github.com/ToanToan110/A-B-Testing)

# About this Project
**Customer Life Time Value (CLV):** This is an measure that represents the total profit earned throughout a customer life cycle, determine which customers are worth investing in and exploiting.
If we can measure the future value our customer will provide, we can both regulate our relationship with them and adopt a more value-added approach for the medium to long term within our company. 

=> This will also play a significant role in determining the budget allocated for marketing activities



## Prerequisites
Package: Pandas, Matplotlib, Numpy

Techniques: K-means

## Resources 
Dataset: This notebook use [Retail Dataset](https://www.kaggle.com/datasets/vijayuv/onlineretail) on Kaggle

# Approach
The formula to calculate Life time value is:

          CLTV = (Customer Value / Churn Rate) × Profit Margin


With:
- CLTV = (Customer Value / Churn Rate) × Profit Margin
- Customer Value = Average Order Value * Purchase Frequency
- Average Order Value = Total Price / Total Transaction
- Purchase Frequency = Total Transaction / Total Number of Customers
- Churn Rate = 1 - Repeat Rate
- Repeat Rate = The rate of customers who have made multiple purchases divided by the total number of customers.
- Profit Margin = Total Price * 0.10

# Calculate the cusomer life time value:
This function is used to calculate the CLV of each customer:
```Python
cltv_c["Average Order Value"] = cltv_c["Total Price"].sum() / cltv_c["Total Transaction"].sum()
cltv_c["Purchase Frequency"] = cltv_c["Total Transaction"] / cltv_c.shape[0]
cltv_c['Profit Margin'] = cltv_c['Total Price'] * 0.10
repeat_rate = cltv_c[cltv_c["Total Transaction"] > 1].shape[0] / cltv_c.shape[0]

churn_rate = 1 - repeat_rate
cltv_c['Customer Value'] = cltv_c['Average Order Value'] * cltv_c["Purchase Frequency"]
cltv_c["CLV"] = (cltv_c["Customer Value"] / churn_rate) * cltv_c["Profit Margin"]

cltv_c.reset_index(inplace = True)
cltv_c.head()
```

And the output of that process is:

![image](https://github.com/ToanToan110/CustomerLifeTimeValue/assets/64849001/de616644-2eea-47a1-bcc0-b573c8f44e6b)

Overview the distribution of CLV:
![image](https://github.com/ToanToan110/CustomerLifeTimeValue/assets/64849001/bc0f9c8a-dc40-4b00-869a-6f36ed59f4d8)

# Training model to predict CLV:
For data sets with small dimensions and few records, models belonging to the decision tree family are suitable. Include: Decision Tree Regression, Random Forest, K-Nearest Neighbors.
We use K-nearest to traning this data

![image](https://github.com/ToanToan110/CustomerLifeTimeValue/assets/64849001/e1a03a67-2420-4529-9ac3-920e4e03e6f0)

Sumup:
- On average for a customer, the model's prediction is about $62000 off => This error is to large
- The model explains 83% of the variation in the dependent variable
---
# Next step:
Build a classifier to cluster customer base on their CLV
