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
**Đến đây có hai hướng tiếp cận để tính toán CLV:**


1.   Tính toán dựa trên một khoảng thời gian cụ thể trên bộ dữ liệu
2.   Tính toán dự trên công thức:

          CTV = Avg Revenue * N_month * Rt_rate


Trong đó:
- Avg Revenue: Average monthly purchase made by the customer in the active customer window.
- N_month : Number of months in the CLV prediction period
- Rt_rate : Overall retention rate of all customers
---

