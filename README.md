# Ex-01_DS_Data_Cleansing
# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# ALGORITHM
## STEP 1
Read the given Data

## STEP 2
Get the information about the data

## STEP 3
Remove the null values from the data

## STEP 4
Save the Clean data to the file

# CODE
import pandas as pd
import numpy as np
import seaborn as sns

df1 = pd.read_csv("Data_set.csv")
df1

df1.head()

df1.describe()

df1.info()

df1.tail()

df1.shape

df1.columns

df1.isnull().sum()

df1.duplicated()

#Using mode method to fill the data in columns as Object(String)
#mode()[0] - Takes the most reccuring value and fills the empty cells
df1['show_name'] = df1['show_name'].fillna(df1['show_name'].mode()[0])
df1['aired_on'] = df1['aired_on'].fillna(df1['aired_on'].mode()[0])
df1['original_network'] = df1['original_network'].fillna(df1['original_network'].mode()[0])

sns.boxplot(x="rating",data=df1)

#Using mean method to fill the data
df1['rating'] = df1['rating'].fillna(df1['rating'].mean())
df1['current_overall_rank'] = df1['current_overall_rank'].fillna(df1['current_overall_rank'].mean())
df1['watchers'] = df1['watchers'].fillna(df1['watchers'].mean())

#Checking the total no.of null values again
df1.isnull().sum()

#Checking info of the dataset to check all the columns have entries
df1.info()
# OUPUT
## DATASET
![image](https://user-images.githubusercontent.com/94154683/189487926-b5ee42bf-7ebd-497e-a64d-664e4fce4306.png)

## HEAD
![image](https://user-images.githubusercontent.com/94154683/189487934-fd2d0be9-cd49-4334-8495-d5fdc3073140.png)

## DESCRIBE
![image](https://user-images.githubusercontent.com/94154683/189487945-df7314ce-7044-4640-a505-6f07e467e54a.png)

## INFO
![image](https://user-images.githubusercontent.com/94154683/189487953-23f6fed6-b651-4fb4-945c-4db122e5c7f9.png)

## TAIL
![image](https://user-images.githubusercontent.com/94154683/189487966-71e311cf-7b82-43b6-81ca-50328cd83d05.png)

## SHAPE
![image](https://user-images.githubusercontent.com/94154683/189487975-6eb0442d-5e2b-4a97-88d0-0f3b3bba0c89.png)

## isnull().sum() - Pre Cleaning
![image](https://user-images.githubusercontent.com/94154683/189487982-907ae087-5a16-4d1e-a61c-65dff99d8645.png)

## DUPLICATES
![image](https://user-images.githubusercontent.com/94154683/189488005-dbf5280d-b7ec-4548-bc44-823cd8b16b02.png)

## SNS PLOT-RATING
![image](https://user-images.githubusercontent.com/94154683/189488021-d9303349-d182-478f-a447-e844ebbba197.png)

## isnull().sum() - Post Cleaning
![image](https://user-images.githubusercontent.com/94154683/189488034-17912ca6-93cd-48ef-839b-d5855ce3dabd.png)

## Info - Post Cleaning
![image](https://user-images.githubusercontent.com/94154683/189488044-6d41a242-a3fc-4b93-af03-e296e8031262.png)


# Result:
The given data is read and data cleaning is performed and the cleaned data is saved to a file.
