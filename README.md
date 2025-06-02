# jupyter-0206
Task 1 (02-06-2025)
# Data Cleaning and Preprocessing
Now lets strat with the task of sales data cleaning and preprocessing since this is a data cleaning task. here we use to convert raw data to cleaned data set.now lets start by inmporting the necessary python libraries and dataset:
# import pandas libraries
import pandas as pd
# read file
df = pd.read_csv('sales.csv', encoding = "ISO-8859-1")
Moving further identify and handle missing values using .isnull()in python
# start with Count missing values per column wise using isnull : Identifies missing values (NaN) in the DataFrame and sum : Aggregates the count of True values (missing values) for each column.
Syntax : print(df.isnull().sum())
# Identify missing values using .isnull() in data frame its return true for missing values and False otherwise
syntax  print("Missing values in the dataset:")
        print(df.isnull())
# Filter rows with missing values is used to identify and filter out missing values (NaN) without directly removing them 
syntax : print("\nRows with missing values:")
         print(df[df.isnull().any(axis=1)])
# it removes duplicate rows based on all columns
syntax : df_cleaned = df.drop_duplicates()
         print(df_cleaned)
# Standardize to lowercase converts all uppercase characters in the string to their lowercase equivalents while leaving other characters unchanged.
syntax: df['CUSTOMERNAME'] = df['CUSTOMERNAME'].str.lower()
        print(df)
# Rename column headers clean and uniform 
syntax : df.columns = df.columns.str.lower().str.replace(" ", "_")
         print(df.columns)
# check and fix data types with integer and datatime format
syntax: df['ordernumber'] = df['ordernumber'].astype(int)  # Convert order number to integer
        df['orderdate'] = pd.to_datetime(df['orderdate'])  # Convert to datetime
        print(df)
# Conclusion
    Data cleaning and preprocessing are integral components of any data analysis Pandas, with its versatile functions, facilitates these processes efficiently.
# Refference 
https://www.geeksforgeeks.org/working-with-missing-data-in-pandas/
https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.drop_duplicates.html
https://stackoverflow.com/questions/57637450/is-there-a-way-to-handle-cast-type-varchar-and-int-in-age-range-sql-query
https://www.freecodecamp.org/news/data-cleaning-and-preprocessing-with-pandasbdvhj/
