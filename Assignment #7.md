# Assignment #7 - Shenan Smith

First, I loaded the State_Drug_Utilization_Data_2010 from the data_612 repository in frankData612 using Jupyter notebook. 
To do this I imported pandas and asked it to read the csv file for the dataset. 

Then I examined the dataset by looking at the first 10 rows of the 2010 dataset.
Next, I subsetted the original data_2010 dataset into a smaller set of 10 rows and named it subset_data_2010.

Next, I looked at the dtypes to see what format each row was in using this code:
print(subset_data_2010.dtypes)

Next, I created a simple function that would concatenate one column with a hypen and then a second column, using this code:
def start_small(df, x, y):
        df['z']= (df[x])+'-'+(df[y])
        return df['z']

I then called the function I created in the previous step, start_small, using this code:
start_small(subset_data_2010, 'Utilization Type', 'State')
This concatenates the Utilization Type with a hyphen and the State column.

Next, I created a custom function called Average_Reimbursed to find an average amount, using this code:
def Average_Reimbursed(df, x, y):
        df['Avg_Amt_Reimbursed']= (df[x])/(df[y])
        return df['Avg_Amt_Reimbursed']

Using the custom function I created in the last step, I calculated the average of the Total Amount Reimbursed by the Number of Prescriptions, using this code:
Average_Reimbursed(subset_data_2010, 'Total Amount Reimbursed', 'Number of Prescriptions')

Then I looked at the subsetted df again to make sure this calcuated result was added into a new column called Avg_Amt_Reimbursed by using this code:
subset_data_2010.head(10)

Next, I created a custom function called my_mean to find an average amount:
def my_mean(values):
    n = len(values)
    sum = 0
    for value in values:
        sum += value
    return(sum / n)
    
I then used this custom function to find the average Total Amount Reimbursed by State:
agg_my_mean = data_2010.groupby('State').Total_Amount_Reimbursed.agg(my_mean)
print(agg_my_mean)

*Note: I had to rename the column Total Amount Reimbursed to Total_Amount_Reimbursed before I could use the custom function on this column. 
When I tried using it on a column name that included spaces I got errors.

Next, using numpy, I calculated the number of rows that were not zero, the sum, the mean, and the standard deviation of the Total Amount Reimbursed and grouped it by State:
import numpy as np
gdf = data_2010.groupby('State').Total_Amount_Reimbursed.agg([np.count_nonzero,np.sum,np.mean,np.std])
print (gdf)

Finally, I created a custom function to sum the results of all the columns and group the results by quarter and then separate them by the two chosen states, Michigan and Ohio:
def my_func(df, x, y):
    category1 = 'Quarter'
    category2 = "State"
    category_values2 = ["OH" , "MI"]
    df2 = df[df[category2].isin(category_values2)].groupby([category1,category2]).sum().unstack()
    return df2
    
To use the custom function I created in the step above, I ran this code:
my_func(data_2010, 'State', 'Quarter')



