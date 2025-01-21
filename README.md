# E-Commerce sales analysis

## Table of Contents

- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning Preparation](#data-cleaning-preparation)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis)
- [Findings](#findings)
- [Recommendations](#recommendations)
- [Limitations](#limitations)
- [References](#references)

### Project overview
Quick presentation of the project. Few lines, no need to enter into details now. 
Ex: This data analysis project aims to provide insights into the sales performance of an e-commerce company over the past year. By analyzing various aspects of the sales, we seek to identify trends, make data-driven recommendations, and gain a deeper understanding of the company's performance.

### Data sources
Primary dataset used for this sales analysis
Ex: The primary dataset used for this analysis is the "sales-data.csv" files, containing detailed information about each sale made by the company. 

### Tools
- Google Spreadsheet - data cleaning [Download here](https:this_is_an_example.com)
- SQL - data analysis
- PowerBI - creating report

### Data cleaning preparation
1. Data loading and inspection
2. Handling missing values
3. Data cleaning and formating

### Exploratory data analysis
EDA involved exploring the sales data to answer key questions;
- What is the overall sales trend ?
- Which products are top sellers ?
- What are the peak sales periods ? 

Ex:
```SELECT
  id
  , name as first_name
  , surname
  , creation_date
  , number_of_orders
  , total_turnover
  , case 
    WHEN number_of_orders >0 THEN 1
      ELSE 0
    END AS is_customers
  , CASE 
    WHEN number_of_orders=0 THEN "New"
    WHEN number_of_orders >= 1 AND number_of_orders <= 2 THEN "New"
    ELSE "Frequent"
    END AS segment
  , CASE
    WHEN number_of_orders = 0 THEN 0
    ELSE (total_turnover / number_of_orders) 
  END AS average_basket 
FROM `crucial-binder-437910-a7.Course14.gwz_customers` 
WHERE name IN ("Paul","George")
ORDER BY id
```

### Findings

The analysis results are summarized as follows:
1. The company's sales have steadily increasing over the past year, with a noticeable peak during the holiday season.
2. Product Category A is the best performing category in terms of sales and revenue.
3. Customer segments with high lifetime value (LTV) should be targeted for marketing efforts. 

### Recommendations

Based on the analysis, we recommend the following actions: 
- Invest in marketing and promotions during peak sales seasons to maximize revenue.
- Focus on expanding and promoting products in catagory A.
- Implement a customer segmentation strategy to target high value customers effectively.

### Limitations 
Ex. 
I had to remove all zero values from budget and revenue columns otherwise they would have affected the accuracy of my conclusions from the analysis. There are still a few outliers even after the comissions but even then we can still see that there is a positive correlation between both budget and number of votes with revenue. 

### References 
EX: If needed...
1. SQL for Businesses by Werty
2. [Stack overflow](https:stack-overflow.com)

