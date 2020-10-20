# Assignment #2 - Shenan Smith

First, I loaded the State_Drug_Utilization_Data_2010 from the data_612 repository in frankData612 using Jupyter notebook. 
To do this I imported pandas and asked it to read the csv file for the dataset. 
Then I explored the data by showing the first 5 rows of the dataset using .head(5)

Next, I changed the 'Quarter Begin Date' column to the correct date format using 
df['Quarter Begin Date'] = pd.to_datetime(df['Quarter Begin Date'])

1) I found the maximum date of the 'Quarter Begin Date' field and created a name for the max date using this code: 
maxdate=df['Quarter Begin Date'].max()
maxdate

2) Next, I subtracted all the dates in the dataset from the maximum date using this code: 
for i in df['Quarter Begin Date']:
    print(maxdate-i)
    
3) I converted the number of days into number of months and named this field 'numberofmonths'. Here's the code I used:
numberofmonths= df['Quarter Begin Date'].dt.strftime('%b')
numberofmonths

4) Then I created a new column named 'Month' and saved the numberofmonths data into the data set:
df['Month'] = numberofmonths
df

5) Finally, I saved the dataset with the newly created 'Month' field to my desktop by using this code:
df.to_csv (r'C:\Users\g\Desktop\Data 612\drug.csv')
I also read the csv file I just created and saved to my desktop by using this code:
df1 = pd.read_csv(r'C:\Users\g\Desktop\Data 612\drug.csv')
df1

