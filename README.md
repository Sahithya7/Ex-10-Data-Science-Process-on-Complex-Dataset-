# Ex-09-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.
# CODE
```
import seaborn as sns
import matplotlib.pyplot as plt

# Load the tips dataset
tips = sns.load_dataset('tips')

# Drop rows with all missing values
tips.dropna(how='all', inplace=True)
sns.barplot(x='day', y='total_bill', data=tips)
plt.show()

# a) Which day of the week has the highest total bill amount?

# Group by day and sum total_bill
total_bill_by_day = tips.groupby('day')['total_bill'].sum()

# Sort by descending order and select the first row
highest_total_bill_day = total_bill_by_day.sort_values(ascending=False).index[0]

print("The day with the highest total bill amount is:", highest_total_bill_day)

# b) What is the average tip amount given by smokers and non-smokers?

sns.barplot(x='smoker', y='tip', data=tips)
plt.show()

# Group by smoker and calculate mean of tip
tip_by_smoker = tips.groupby('smoker')['tip'].mean()

print("Average tip amount given by smokers:", tip_by_smoker['Yes'])
print("Average tip amount given by non-smokers:", tip_by_smoker['No'])

# c) How does the tip percentage vary based on the size of the dining party?

tips['tip_percentage'] = tips['tip'] / tips['total_bill'] * 100
sns.pointplot(x='size', y='tip_percentage', data=tips)
plt.show()

# Create a new column for tip percentage
tips['tip_percentage'] = tips['tip'] / tips['total_bill']

# Group by size and calculate mean of tip percentage
tip_percentage_by_size = tips.groupby('size')['tip_percentage'].mean()

print("Tip percentage by size of dining party:")
print(tip_percentage_by_size)

# d) Which gender tends to leave higher tips?

sns.boxplot(x='sex', y='tip', data=tips)
plt.show()

# Group by gender and calculate mean of tip
tip_by_gender = tips.groupby('sex')['tip'].mean()

print("Average tip amount by gender:")
print(tip_by_gender)

# e) Is there any relationship between the total bill amount and the day of the week?

sns.scatterplot(x='total_bill', y='day', data=tips)
plt.show()

# f) How does the distribution of total bill amounts vary across different time periods (lunch vs. dinner)?

sns.boxplot(x='time', y='total_bill', data=tips)
plt.show()

# g) Which dining party size group tends to have the highest average total bill amount?

sns.barplot(x='size', y='total_bill', data=tips)
plt.show()

# Group by size and calculate mean of total_bill
total_bill_by_size = tips.groupby('size')['total_bill'].mean()

print("Average total bill amount by size of dining party:")
print(total_bill_by_size)

# h) What is the distribution of tip amounts for each day of the week?

sns.boxplot(x='day', y='tip', data=tips)
plt.show()

# i) How does the tip amount vary based on the type of service (lunch vs. dinner)?

sns.boxplot(x='time', y='tip', data=tips)
plt.show()

# j) Is there any correlation between the total bill amount and the tip amount?
sns.scatterplot(x='total_bill', y='tip', data=tips)
plt.show()
correlation = tips['total_bill'].corr(tips['tip'])
print("Correlation coefficient between total_bill and tip:", correlation)
```
# OUPUT
![image](https://github.com/Sahithya7/Ex-08-Data-Visualization_1/assets/133002193/f0a7fbed-cd7e-4097-b635-d995cd995f51)

The day with the highest total bill amount is: Sat

![image](https://github.com/Sahithya7/Ex-08-Data-Visualization_1/assets/133002193/9f89e08e-a10d-46ef-9e53-52403022704b)

Average tip amount given by smokers: 3.008709677419355
Average tip amount given by non-smokers: 2.9918543046357615

![image](https://github.com/Sahithya7/Ex-08-Data-Visualization_1/assets/133002193/60ab6546-80a3-46f6-ab7b-f1540a8eb9ac)

Tip percentage by size of dining party:
size
1    0.217292
2    0.165719
3    0.152157
4    0.145949
5    0.141495
6    0.156229
Name: tip_percentage, dtype: float64

![image](https://github.com/Sahithya7/Ex-08-Data-Visualization_1/assets/133002193/c94e1982-4a0b-463a-9ecc-930ff57b20f4)

Average tip amount by gender:
sex
Male      3.089618
Female    2.833448
Name: tip, dtype: float64

![image](https://github.com/Sahithya7/Ex-08-Data-Visualization_1/assets/133002193/0f8299f5-8b6d-4639-9d8d-fa437df22a39)

![image](https://github.com/Sahithya7/Ex-08-Data-Visualization_1/assets/133002193/fd0488b4-1fe7-4776-9fd0-a354ca7822a1)

![image](https://github.com/Sahithya7/Ex-08-Data-Visualization_1/assets/133002193/6ea51b92-1c43-4aca-bd51-3a59de984441)

Average total bill amount by size of dining party:
size
1     7.242500
2    16.448013
3    23.277632
4    28.613514
5    30.068000
6    34.830000
Name: total_bill, dtype: float64

![image](https://github.com/Sahithya7/Ex-08-Data-Visualization_1/assets/133002193/19a0a3ef-2abe-487c-86f1-2784f3733851)

![image](https://github.com/Sahithya7/Ex-08-Data-Visualization_1/assets/133002193/7a2a1b73-760f-4495-b3dd-1ad34fb647b8)

![image](https://github.com/Sahithya7/Ex-08-Data-Visualization_1/assets/133002193/0eda11ef-c1a5-4e87-805d-e9190fde1dac)

Correlation coefficient between total_bill and tip: 0.6757341092113641
# RESULT
Thus, Data Visualization on a complex dataset and save the data to a file has been performed successfully.
