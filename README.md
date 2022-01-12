# Sprocket Central Pty Ltd company Customers Classification Project Overview - KPMG Virtual Intership

Sprocket Central Pty Ltd, is a medium size bike & cycling accessories organisation, it has a large dataset relating to its customers, the client provided me with four different datasets including customers transactions,customers demographics and customers addresses, new potential customers dataset. Their marketing team want to optimise their marketing strategy by effectively analysing the dataset they provided.

Here are the steps of the project:

**•** Assessment of data quality and completeness in preparation for analysis
**•** Analyse the customers and reveal some important insights
**•** Applied RFM segmentation to segment customers into four different segments (Platinum,Gold,Silver,Bronze)
**•** Created a model by Desicion Tree by using the existent customers features to train a Classification model (with 99% accuracy)
**•** Used the model on the new customers dataset with similar features to predicte what type each new customer would be

# Python Packages Used:
Pandas, numpy, sklearn, matplotlib, seaborn

# Data Cleaning
## Customers Transactions Dataset
**•** Ammended the missing value in online_order, brand, product line, product class, product size, standard cost and product_first_sold_date columns
**•** Converted the types of list price, standard cost columns from object to numeric
**•** Converted The Transactions date column from object into datetime
**•** Extracted year,month,day from transaction date column

## Customer Demographics Dataset
**•** Ammended the missing value in last_name, DOB, job_title, job_industry_category, default, tenure columns
**•** Converted past_3_years_bike_related_purchases, tenure from object into numeric
**•** Converted DOB column from object into datetime
**•** Extracted Age column from DOB column

## New Customers List Dataset
**•** Ammended the missing value in job_title, job_industry_category columns
**•** Delete wrong information in Gender columns
**•** Extracted Age column from DOB column

# EDA Analysis
After Data cleaning, I conducted an Exploratory data analysis on data by joining three old customers datasets

- Univariate Analysis:

1. From the distribution of prices, we notice that we have a normally distributed data with no outliers, the average of the prices is 1107.
2. Standard cost have a positively skewed (right-skewed) distribution with some outliers, the average of the cost in dollars is 555.
3. Ages distribution graph shows the data is normally distributed with few outliers at 80 and 90 ages, the data are mostly distributed between 20s and 70s, and most of our customers' ages range from 30s to mid 40s, the average age is 43
4. The amount of orders along the year is almost the same, but the highest time in the year is in the start and end of the summer in months July,August & October, the reason could be people want to buy bikes to spend their summer vacation.
5. Mass customers represents 50% of the orders, Affluent customers represents 24% of the orders, High net worth customers represents 25% of the orders.
6. Most of our orders are done in NSW state in Ausrtalia which has 50% of total orders, VIC and QLD have 22%, 21% respectively
7. Distribution of orders between men and women are almost the same, 50% of our orders are from women and 48% are from men.
8. Most of our customers work at manufacturing industry.

- Bivariate Analysis:
1. Women who owns a car buy more bikes than women who don't and Men who do not own a car buy more than Men who do.
2. In most of the states, women buy more than men, whereas men buy more in Victoria and new south wales
3. For online orders, women order bikes more than men.
4. Most profitable product from our products is WeareA2B brand

- Mulitvariate distributions:

1. Most of the revenue has been produced by mass customers by female.
2. Manufacturing industry produced more revenue than other industries by male customers.
3. There are no strong correlations among numerical data.

- Unusual distributions:
1. The Age had some outliers should be removed.
2. Standard cost had some outliers should be removed.

# RFM Analysis
In aim to target high value customers, I conducted a RFM Model and segmented customers into four different segments (Platinum, Gold, Silver, Bronze)
The RFM model is based on three quantitative factors:
- Recency: How recently a customer has made a purchase
- Frequency: How often a customer makes a purchase
- Monetary Value: How much money a customer spends on purchases

# Model Building
- Converted the categorical features into binary
   1. one hot encoding for the nomial categorical variables
   2. label encoding for the ordinal categorical variables
- Using Decision Tree & Random Forest classifier to build model, both of them got about 99% accuracy
- Predict each new customers' type by using the model I created
