# Grocery Analytics API

## Project Description

This MuleSoft API provides the back-end for an analytics dashboard. It leverages data from three sources: a relational database, an existing API, and a set of CSV files – which detail orders, transactions, products, and customers. This project consumes, processes, and organizes this data to deliver a single RESTful API which the consumer can use to see different trends related to income, sales, and customers.

## Technologies Used

* Mulesoft - version 4.4.0
* Anypoint Studio - version 7.12.1
* JavaSE  1.8
* PostgreSQL
* Git
* AWS
* Spring Framework - version 2.6.7

## Features

- [x] Generate data results for total income per previous month, organized by Store ID, Product ID, and by day of the week.
- [x] Generate data results for total quantity of sales per previous month by Store ID, Product ID, and by day of the week.
- [x] Analyzes the successful vs unsuccessful transactions by payment type.
- [x] Generates Average Sale Price data by Store ID and Day of Week
- [x] Generates Average Sale Quantity data by Store ID and Day of Week
- [x] Generate a trendline of historic sales by Store ID and Product ID
- [x] Generate a trendline of historic income per Store by Store ID
- [x] Generate representational data of new and returning customers

To-do list:
- [ ] More Error Handling for bad URI requests
- [ ] More MUnit testing to ensure proper application build

## Getting Started
- Install Anypoint Studio (https://www.mulesoft.com/lp/dl/studio)
- Navigate to target directory in git bash then enter: `git clone https://github.com/Ben-Ortiz/Mulesoft_Cohort_p3.git`
- Open Anypoint Studio then select the workspace as previously targeted directory.  

What it should look like after cloning and opening in Anypoint Studio:  
![image](https://user-images.githubusercontent.com/40044460/172427928-feb73c86-e780-4ebe-816b-badb77fc371a.png)  

- Install postman or ARC as a client for testing API endpoints.  

>Postman: https://www.postman.com/downloads/  
>Advanced Rest Client: https://install.advancedrestclient.com/install
## Usage

Guide to the available endpoints:

### Average Sale Quantity
**GET** http://localhost:8081/api/average-sales-quantity  
**Returns:** average "quantity of product" per sale, for all data

**GET** http://localhost:8081/api/average-sales-quantity/store?id=4  
**Returns:** average "quantity of product" per sale, for specified store

**GET** http://localhost:8081/api/average-sales-quantity/dow?dow=Tuesday (day spelled out)  
**Returns:** average "quantity of product" per sale, for specified day of the week

### New vs Returning
**GET** http://localhost:8081/api/new-vs-returning/store?id=4  
**Returns:** percentage of total customers that are new at the given store

### Total Income for Previous Month
**GET** http://localhost:8081/api/totalIncomePrevMonth  
**Returns:** total income made in the previous month

**GET** http://localhost:8081/api/totalIncomePrevMonth/storeId?storeId=2  
**Returns:** total income made in the previous month, for specified store

**GET** http://localhost:8081/api/totalIncomePrevMonth/productId?productId=e0f021c9-f530-493a-a002-d7c39d47bf78  
**Returns:** total income made in the previous month, for specified product

### Total Quantity of Sales for Previous Month
**GET** http://localhost:8081/api/totalQuantitySalesPrevMonth  
**Returns:** total number of sales made in previous month

**GET** http://localhost:8081/api/totalQuantitySalesPrevMonth/store?id=3  
**Returns:** total number of sales made in previous month, for specified store

**GET** http://localhost:8081/api/totalQuantitySalesPrevMonth/product?id=475ee4e3-95ae-44ac-9ae3-21080e710a1c  
**Returns:** total number of sales made in previous month, for specified product

**GET** http://localhost:8081/api/totalQuantitySalesPrevMonth/dotw?dotw=3 (1 is Monday, 7 is Sunday)  
**Returns:** total number of sales made in previous month, for specified day of the week

### Average Sale Price
**GET** http://localhost:8081/api/averagesale  
**Returns:** average sale price, for all data

**GET** http://localhost:8081/api/averagesale/?store_id=2  
**Returns:** average sale price for specified store

**GET** http://localhost:8081/api/averagesale/?day=Mon (three-letter-abbreviated days)  
**Returns:** average sale price for specified day

**GET** http://localhost:8081/api/averagesale/?day=Thu&?store_id=1  
**Returns:** average sale price for specified day and store

### Transaction Success
**GET** http://localhost:8081/api/transactionsuccess  
**Returns:** transaction success by payment type as a percent

### Historic Sales
**GET** http://localhost:8081/api/api/historicSalesByStore?id=4  
**Returns:** individual sales in ascending order by StoreID parameter as JSON array.

**GET** http://localhost:8081/api/api/historicSalesByProduct?id=a6693ab3-e4c1-4335-999b-a02349c8b8c9  
**Returns:** individual sales in ascending order by ProductID parameter as JSON array.

### Historic Income
**GET** http://localhost:8081/api/api/historicIncomeByStore?id=4  
**Returns:** total income of individual dates in ascending order by StoreID parameter as JSON array.

## Contributors
Here are the people who have contributed to this project.

- Ben Ortiz
- Abby Sowalla
- Brian Lee
- Brandon Learned
- Jake Varney
- Holly Anderson
- Anthony Baraja
- Ethan Shura
- Laura Messinger
- Sylvan C
- Erick Cilia
- Eric Schmidt
- Justin Cruz
- Greg Ramirez
- Jaeden Garcia
- Renato de Oyague
- Win Thurein Myint
