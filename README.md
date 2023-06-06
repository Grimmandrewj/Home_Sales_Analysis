## Goal
- In this assignment, I was tasked with utilizing SparkSQL to determine key metrics about home sales today
- I was to use Spark to create temporary views, partition the data, cache and uncache a temporary table, and verify that the table was uncached
- The data consisted of ID number of the purchase, date of purchase, date the home was built, price, number of bedrooms, bathrooms, and floors, square footage, view rating, etc. 

## Method
- Initially I imported findspark and pyspark and assigned a variable to the provided url: https://2u-data-curriculum-team.s3.amazonaws.com/dataviz-classroom/v1.2/22-big-data/home_sales_revised.csv
- I then read in the AWS S3 bucket into a DataFrame and displayed the result: 

![image](https://github.com/Grimmandrewj/Home_Sales/assets/120341249/678cb718-8bca-4bf0-8b49-cb2ae560cdd0)

- I created a temporary view of the DataFrame and displayed the following queries: 

  - Average price for four bedroom house sold each year
  
    ![image](https://github.com/Grimmandrewj/Home_Sales/assets/120341249/db69350b-6273-4d4a-8830-1392db05ac83)
  
  - Average price for three bedroom, three bath home sold each year

    ![image](https://github.com/Grimmandrewj/Home_Sales/assets/120341249/d3bf10e7-2b20-41c7-ba46-a22a8bcf3d6f)

  - Average price for three bedroom, three bath, two floor home with 2,000 or more square feet of living space sold each year

    ![image](https://github.com/Grimmandrewj/Home_Sales/assets/120341249/f109168d-60e0-4eda-bbdb-b1fba4876259)

  - View rating for average price of a home where the price is equal to or greater than $350,000

    ![image](https://github.com/Grimmandrewj/Home_Sales/assets/120341249/66f7f062-b27c-4938-b700-a39f4554e296)

- I then cached the temporary table and used the cached data to run the same query (view rating for average price where purchase price is greater than $350,000).  
- The data was then partitioned by the "date_built" field on the formatted parquet home sales data
- The formatted data was read, a temporary table created, and a query run.  The query took longer to run with the parquet data (1.7 seconds) vs. the cached data (.03 seconds).  

## Summary and results
- The data was pulled from the AWS S3 bucket and formatted into a DataFrame successfully
- The signified queries were run and the appropriate data displayed
- The uncached, cached, and parquet-formatted data was displayed and the run time calculated for the queries
- The query ran the fastest using the cached data
- The data was partitioned properly by the "date_built" field
