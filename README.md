# Preparing the data for analysis
# 1 Examining the dataset
#Import the pandas library as pd
import pandas as pd

#Read 'police.csv' into a DataFrame named ri
ri = pd.read_csv('police.csv')

#Examine the head of the DataFrame
print(ri.head())

# 2 Dropping columns
#Count the number of missing values in each column
print(ri.isnull().sum())

#Count the number of missing values in each column
print(ri.isnull().sum())

#Examine the shape of the DataFrame
print(ri.shape)

#Drop the 'county_name' and 'state' columns
ri.drop(['county_name', 'state'], axis='columns', inplace=True)

#Examine the shape of the DataFrame (again)
print(ri.shape)

# 3 Dropping rows
#Count the number of missing values in each column
print(ri.isnull().sum())

#Drop all rows that are missing 'driver_gender'
ri.dropna(subset=['driver_gender'], inplace=True)

#Count the number of missing values in each column (again)
print(ri.isnull().sum())

#Examine the shape of the DataFrame
print(ri.shape)

# Fixing a data type
#Examine the head of the 'is_arrested' column
print(ri.is_arrested.head())

#Check the data type of 'is_arrested'
print(ri.is_arrested.dtype)

#Change the data type of 'is_arrested' to 'bool'
ri['is_arrested'] = ri.is_arrested.astype('bool')

#Check the data type of 'is_arrested' (again)
print(ri.is_arrested.dtype)
