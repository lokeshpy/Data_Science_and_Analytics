# Python Statistical Data Visualization - Plotting data
In this poject i'm going to create a sample data and plot the data 
### Tools
PyCharm IDE
### Software
Python Version: 3.7
### Package
1. Matplotlib
2. Pandas
3. Seaborn
### Creating dataframe
"""Pandas use for data structures and data analysis
Import the necessary libraries
""""
``` sas
import matplotlib.pyplot as plt
import pandas as pd
import seaborn as sns

#Create Data_Frame from Array.

df = pd.DataFrame({
    'name':['john','mary','peter','jeff','bill','lisa','jose'],
    'age':[23,78,22,19,45,33,20],
    'gender':['M','F','M','F','M','F','M'],
    'state':['CA','DC','CA','DC','VA','NY','NY'],
    'num_children':[2,0,0,3,2,1,4],
    'num_pets':[5,1,0,5,2,2,3]
})
print(df)
```
![output](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image9.JPG)

### scatter plot between two variables
``` sas
df.plot(kind='scatter',x='num_children',y='num_pets',color='red')
plt.show()
```
![Scatter plot graph](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image1.JPG)

### Simple Line Plot
``` sas
df.plot(kind='bar',x='name',y='age')
plt.show()
```
![Simple Line Plot](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image2.JPG)

### Line plot with multiple columns
``` sas
ax = plt.gca()
df.plot(kind='line',x='name',y='num_children', ax=ax)
df.plot(kind='line',x='name',y='num_pets', color='red', ax=ax)
plt.show()
```
![Line Plot](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image3.JPG)

### Stacked bar plot with two-level group by
``` sas
df.groupby(['state','gender'])['name'].size().unstack().plot(kind='bar',stacked=True)
df.sample(n=3)
plt.show()
```
![Stacked Bar Plot](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image4.JPG)

### Plot with count of people by gender, spliting by state:
``` sas
df.groupby(['gender','state'])['age'].size().unstack().plot(kind='bar',stacked=True)
plt.show()
```
![Groupby plot](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image5.JPG)

### Violinplot
```sas
fig, ax = plt.subplots()
ax.violinplot(df["age"], vert=False)
plt.show()
```
![violinplot](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image6.JPG)

### Plot of the distribution of faculty children
```sas
num_bins = 10
plt.hist(df['num_children'], num_bins, density=1, facecolor='blue', alpha=0.5)
plt.show()
```
![distribution](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image7.JPG)

### Plot using Seaborn libaray
```sas
sns.set()
# Set context to `"paper"`
sns.set_context("paper")
# Construct pets plot
sns.swarmplot(x="num_pets", y="age", data=df)
# Show plot
plt.show()
```
![seaborn plot](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image8.JPG)
