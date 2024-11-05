# LITA_PROJECT_CUSTOMER_DATA
This is where i documented my second project on data analysis with The Incubator Hub
### Project Title: Customers Data

[Project Overview](project-overview)

Data Sources

Tools Used

Data cleaning and preparations
### Project Overview
---
This Data Analysis project aims to generate insight into the customer performance of the customer data peoject overview to gather enough insint to make reasonable decisions whivh  will enable us to tell compelling stories about our data

### Data Sources
---
The Primary source of data used here is the Customer data project from The Incubator Hub Lita Project

### Tools Used
---
- Microsoft Excel [Download Here](https://www.microsoft.com)
1.  Data Cleaning
2.  Analysis
3.  For Data Visualization
- SQL For querying data
- POWER BI
- Github for Portfolio building
 
### Data cleaning and preparations
---
In the initial phase of the data cleaning and preparations, we performed the following action

1. Data Loading and Inspection.
2. Handling missing variables.
3. Data cleaning and formatting.

### Exploratory Data Analysis
---
EDA involves the exploring of the data to answer some questions about the data such as :

- What is the Average subsciption duration?
- What is the most popular subscription types?
- Subscription patterns

### Data Analysis
---
This is where we include some basic class of codes or the DAX expressions used during your analysis.
```SQL
SELECT Region, COUNT(CustomerID) AS TotalCustomers
FROM [dbo].[LITA capstone data]
GROUP BY Region

SELECT TOP 1 SubscriptionType, COUNT(CustomerID) AS TotalCustomers
FROM [dbo].[LITA capstone data]
GROUP BY SubscriptionType
ORDER BY TotalCustomers DESC

SELECT CustomerID, CustomerName, DATEDIFF(MONTH, SubscriptionStart, SubscriptionEnd) AS SubscriptionDurationMonths
FROM [dbo].[LITA capstone data]
WHERE Canceled = 1 
AND DATEDIFF(MONTH, SubscriptionStart, SubscriptionEnd) <= 6

SELECT AVG(DATEDIFF(DAY, SubscriptionStart, SubscriptionEnd)) / 30.0 AS AvgSubscriptionDurationMonths
FROM [dbo].[LITA capstone data]

SELECT CustomerID, CustomerName, DATEDIFF(MONTH, SubscriptionStart, SubscriptionEnd) AS SubscriptionDurationMonths
FROM [dbo].[LITA capstone data]
WHERE DATEDIFF(MONTH, SubscriptionStart, SubscriptionEnd) > 12

SELECT SubscriptionType, SUM(Revenue) AS TotalRevenue
FROM [dbo].[LITA capstone dataset]
GROUP BY SubscriptionType

SELECT TOP 3 Region, COUNT(CustomerID) AS CanceledSubscriptions
FROM [dbo].[LITA capstone data]
WHERE Canceled = 1
GROUP BY Region
ORDER BY CanceledSubscriptions DESC

SELECT 
    SUM(CASE WHEN Canceled = 0 THEN 1 ELSE 0 END) AS ActiveSubscriptions,
    SUM(CASE WHEN Canceled = 1 THEN 1 ELSE 0 END) AS CanceledSubscriptions
FROM [dbo].[LITA capstone data]
```


### Data Visualization


![Screenshot 2024-11-05 121128](https://github.com/user-attachments/assets/1ee9b43a-bd7b-4e7e-8cb7-6f87f3ede338)


![Screenshot 2024-11-05 121222](https://github.com/user-attachments/assets/49062c61-fa6b-4743-b156-f5b0f674119b)

   ![Screenshot 2024-11-04 212602](https://github.com/user-attachments/assets/988eff92-4264-4807-ae11-2dfe2a3187ae)

