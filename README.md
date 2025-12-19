# Swiggy Sales Data Analysis Project (SQL)

## Overview

This is an **advanced data analysis project** focusing on a real-time dataset of Swiggy sales transactions spanning three quarters. The primary tool used is **SQL Server Management Studio (SSMS)**.
The project involved a complete data workflow, from raw data ingestion and rigorous cleaning to the creation of a performance-optimized **Star Schema**. The final objective was to write and execute multiple SQL queries, ranging from basic to advanced, to extract Key Performance Indicators (KPIs) and granular business insights. This project demonstrates proficiency in data preparation, dimensional modelling, and complex analytical querying using SQL.
 
## Dataset

The analysis uses a **real-time Swiggy sales dataset**.

•	**Size**: The raw file is a single, bulky table containing 197,430 rows and 10 columns.

•	**Content**: Each record represents a single order. Key fields include state, city, order date, restaurant name, dish name, price, rating, and rating count.

## Tools

•	**Database Management System:** **MSSQL Server** (using SSMS – SQL Server Management Studio).

•	**Core Technology:** **SQL** (The queries used are adaptable for other relational databases like MySQL or PostgreSQL with minor modifications).

## Steps

The project followed a structured data analytics methodology:

1.	**Data Loading and Setup:** The raw CSV file was imported into **SSMS** to create the initial raw table (swiggy_data).
   
2.	**Data Cleaning and Validation (EDA):** Comprehensive data quality checks were performed, including identifying and verifying the absence of null values and empty/blank strings across all dimensions.
   
3.	**Duplicate Detection and Removal:** Identified 29 duplicate rows by grouping all fields. These duplicates were efficiently deleted using a Common Table Expression (CTE) combined with the **ROW_NUMBER()** window function and partitioning.
   
4.	**Dimensional Modelling (Star Schema Creation):** The bulky single table was restructured into a **Star Schema** to reduce redundancy and improve query performance. This involved creating five dimension tables (dim_date, dim_location, dim_restaurant, dim_category, dim_dish) and a central fact table (fact_swiggy_orders).
   
5.	**Schema Population:** Data, including derived date components (year, month, quarter), location details, and restaurant names, was inserted into the dimension tables using distinct values from the raw data. The fact table was populated, resolving foreign keys by joining back to the dimension tables to establish relationships.
    
6.	**Advanced Analysis:** Utilized multi-table **JOIN operations** across the generated Star Schema to perform in-depth analysis and solve specific business requirements.

## Results

The analysis yielded crucial insights by applying complex SQL functions (date functions, aggregations, window functions):

### Key Performance Indicators (KPIs)

•	**Total Orders:** Calculated total transaction volume.

•	**Total Revenue:** Calculated and presented total revenue, formatted in **INR Million**.

•	**Average Dish Price:** Determined the average transaction value.

•	**Average Rating:** Calculated the average rating across all orders.

### Deep Dive Business Analysis

•	**Trend Analysis:** Identified **monthly and quarterly order trends**, showing maximum sales in specific periods (e.g., January, August) and analysed order patterns by day of the week.

•	**Location Performance:** Identified the **Top 10 performing** cities by order volume (using the TOP 10 clause) and assessed revenue contribution by state, highlighting Karnataka as the maximum contributor.

•	**Food Performance:** Analysed restaurant performance (Top 10 restaurants by orders, e.g., McDonald's, KFC) and **most ordered dishes** (e.g., green salad, butter naan).

•	**Customer Spending:** Segmented customer orders by price range to determine spending patterns (e.g., maximum orders placed in the 100-199 INR range).



