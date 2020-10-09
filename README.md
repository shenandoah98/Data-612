# Assignment #1 - Shenan Smith

First, I selected the State_Drug_Utilization_Data_2010 from the data_612 repository in frankData612

Next, I loaded the dataset using Jupyter notebook. To do this I imported pandas and asked it to read the csv file for the dataset. Then I explored the data by doing the following:

1)  I showed the first 10 rows of the dataset using .head(10)

2)  I showed the last 10 rows of the dataset using .tail(10)

3)  Then I printed to see what the type of the data set is by using print(type(df)). This shows that this particular dataset is a Data Frame

4)  I checked the number of rows and columns by using print (df.shape). This showed me that there are 156,220 rows and 21 columns.

5)  Finally, I used print(df.groupby('Quarter')['Total Amount Reimbursed'].mean()) to find the total amount reimbursed by quarter.

