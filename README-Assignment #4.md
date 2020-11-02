# Assignment #4 - Shenan Smith

First, I loaded the State_Drug_Utilization_Data_2010 from the data_612 repository in frankData612 using Jupyter notebook. 
To do this I imported pandas and asked it to read the csv file for the dataset. 

Next, I downloaded the State Drug Utilizatin Data from Medicaid's website onto my computer. I uploaded the 2019 data into Jupyter notebook by calling the name of the file.

Then I explored the column names of the 2010 data and looked at the first 5 rows of the dataset. 
Next I explored the column names of the 2019 data and looked at the first 5 rows of this dataset.
By looking at both of these, I realized that in the 2010 data, there was a column named 'Unnamed: 0' that wasn't in the 2019 dataset.

To join the two datasets, I concatenated them and performed an inner join to keep the data from both datasets on only the columns that were in both datasets, using this code:
combined = pd.concat([data_2010,data_2019], join='inner', ignore_index=True)
I also chose to ignore the index so that the number of rows would be indexed from 0 to the total number in the dataset, rather than keeping the indexing of the two original datasets.

Next I looked at the total number of rows and columns in the combined dataset.
I also looked at the total number of rows and columns in the 2010 and 2019 dataset and counted the missing values on each as well.

Then I looked at the total number of missing values in each row on the combined dataset to make sure the numbers matched the individual datasets.
This also gave me a good idea of how many rows had missing values. On the 2019 dataset, there were approximately half of the rows that contained missing values. 

When I dug a little deeper to see which rows had missing values, it appeared that the majority of them were because the data was suppressed. 
I used this code to see the rows with only missing values:
data_2019_null_data = data_2019[data_2019.isnull().any(axis=1)]
data_2019_null_data
In my current position, we typically suppress data that can lead to identifying particular companies or individuals. 
 
If I were a little more familiar with the datasets and understood more aobut the variables, I would probably try to impute the missing data rather than delete it, 
especially since it accounted for so much of the data. 
Not being familiar with which fields to use to help impute the missing data, I chose to remove the rows that contained missing values using the following code:
combined_cleaned = combined.dropna()

Finally, I checked the new size of the cleaned combined dataset by using this code:
print(combined_cleaned.shape)
which showed me that the remaining dataset contains 2,198,250 rows and 20 columns.

I also checked to make sure the missing values were all removed from the cleaned by running this code:
combined_cleaned.isnull().sum()
