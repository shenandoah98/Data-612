# Assignment #3 - Shenan Smith

First, I loaded the State_Drug_Utilization_Data_2010 from the data_612 repository in frankData612 using Jupyter notebook. 
To do this I imported pandas and asked it to read the csv file for the dataset. 
Then I explored the data by showing the first 5 rows of the dataset using .head(5)
Next, I imported the matplotlib and seaborn packages using the following code:
import matplotlib.pyplot as plt
import seaborn as sns

## Chart #1 - 
For this chart, I created a count plot, or bar chart, that shows how many times each State had a drug utilization for a covered outpatient drug.

I changed the dimensions of the graph to 18x12, so that data for all 50 states would be legible, using this code:
count_dims = (18,12)
count, ax = plt.subplots(figsize=count_dims)
ax = sns.countplot('State', ax=ax,data=df)

Then I added a title to the graph using this code:
ax.set_title('Count of State')

Next I asked the graph to use the State variable for the x-axis, using this code: 
ax.set_xlabel('State')

Then I asked for the frequency to be plotted using this code:
ax.set_ylabel('Frequency')

Finally, I plotted the graph:
plt.show()

A count plot, or bar plot, is best used when you want to count discrete variables.  

## Chart #2 - 
For this chart, I created a bar chart, that shows how many units were reimbured for each State.

I changed the dimensions of the graph to 18x12, so that data for all 50 states would be legible, using this code:
bar_dims = (18,12)
bar, ax = plt.subplots(figsize=bar_dims)
sns.barplot(x=df['State'],y=df['Units Reimbursed'],ax=ax,data=df)

Then I added a title to the graph using this code:
ax.set_title('Total Units Reimbursed per State')

Finally, I plotted the graph:
plt.show()

Box plots are useful to show multiple variables.

## Chart #3 - 
For this chart, I created a scatterplot comparing how many prescriptions there were to the total number of reimbursements, using this code:
scatter, ax = plt.subplots()
ax = sns.regplot (x='Total Amount Reimbursed', y='Number of Prescriptions', data=df)

I set the title to show Total Amount Reimbursed versus Number of Prescriptions using this code:
ax.set_title('Total Amount Reimbursed versus Number of Prescriptions')

Then I asked for the Total Amount Reimbursed to be displayed on the x-axis:
ax.set_xlabel('Total Amount Reimbursed')
And I asked for the Number of Prescriptions to be shown on the y-axis:
ax.set_ylabel('Number of Prescriptions')

Finally, I plotted the graph:
plt.show()

Scatterplots are useful when you want to show a regression line, or see if there is a correlation between two variables. 


## Note: 
I also attempted to create a boxplot, but colab seemed to be running super slow and I couldn't get the last code to run.
I was also going to see if I could do some graphing after I group information together, but I haven't had time yet to figure this out. 

