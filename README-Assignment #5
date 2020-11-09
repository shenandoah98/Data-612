# Assignment #5 - Shenan Smith

First, I loaded the State_Drug_Utilization_Data_2010 from the data_612 repository in frankData612 using Jupyter notebook. 
To do this I imported pandas and asked it to read the csv file for the dataset. 

Then I examined the dataset by doing the following:
  * I looked at the first 5 rows of the 2010 dataset.
  * I viewed all the column names of the dataset.
  * I looked at the dtypes attribute to see what format each column was in.
  
1)
To convert a column of non-categorical type into a categorical type,
I converted the State column from a non-categorical type into a categorical type using this code:
  data_2010['State'] = data_2010['State'].astype('category')
  
  Then I double checked the dtypes of the dataset to ensure the State column was changed to a categorical type using this code:
    print(data_2010.dtypes)
    
I also converted the Product Name column from a non-categorical type into a categorical type using this code:
  data_2010['Product Name'] = data_2010['Product Name'].astype('category')
  
   Then I double checked the dtypes of the dataset to ensure the Product Name column was changed to a categorical type using this code:
    print(data_2010.dtypes)
    
2)
To Convert another column into a string type,
I converted the Quarter column from an integer to a string using this code: 
  data_2010['Quarter'] = data_2010['Quarter'].astype(str)
  And I checked to make sure the Quarter column was indeed changed to a string using this code:
  print(data_2010.dtypes)
  
I also found a neat way to explore the unique counts in each column using this code:
unique_counts = pd.DataFrame.from_records([(col, data_2010[col].nunique()) for col in data_2010.columns],columns=['Column_Name', 'Num_Unique']).sort_values(by=['Num_Unique'])
unique_counts
