#              Retail Sales Predication using R program
In this article I’m going use an open source dataset which is available in this [link] (https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting/data) for download. This dataset contains sales information of 45 different Wal-Mart Retail Stores across US and using this dataset I’m to predict Wal-Mart weekly sales.
I have downloaded three different dataset names as Train.csv, Store.csv and Features.csv. After carefully validating the data, I have merged all the data into one single data.

###Process the data using R

Merged data are now processed into R program and exporting the variable on the dataset.

![output](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image18.JPG)

![output](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image19.JPG)

![output](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image20.JPG)

###Calculate R summary statistics

In the previous output I noticed “NA” values on the many variables, and also under the variable “IsHoliday” had a Boolean value of “TRUE” and “FALSE”. During the data cleansing process. Change Boolean values as TRUE = 0 and FALSE =1 and also for all the missing data for NA’s I have marked the value as “0” and also I have added one more Variable to the dataset called “Year” which represent the Sale year of the stores. I have also verified that there are no values with NA in the dataset.

![output](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image21.JPG)

![output](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image22.JPG)

###Perform test for Hypotheses for a two-sample t test

Null Hypotheses (H0):  There is no difference in Wal-Mart average sales in the year to 2011 and 2012.

Alternate Hypotheses (Ha):  There is a different is Wal-Mart average sales in the year 2011 and 2012.

![output](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image23.JPG)

![output](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image24.JPG)


Let’s assume that significance level a = 0.05. The p-value of the two-sided t-test is 0.002336 which less than the significance level a = 0.05. Lower p-value means sufficient evidence exists to reject the null hypothesis(H0), in favor of the alternative hypothesis (Ha).

###Determine how to interpret results and reach the right conclusions

I have used multiple linear regression model to predict sales. In this analysis, I will interpret the values and explain the relationship between independent and dependent variables

![output](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image25.JPG)

![output](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image26.JPG)

![output](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image27.JPG)

![output](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image28.JPG)

Predicted the Weekly sales to $23129.82 with the arbitary value for 
 - Temperature  = 65
 - Fule_Price = 2.87
 - MarkDown5 = 1001
 - CPI = 200

###Determine the question(s) you are addressing

Predeciting the sales for any organization is the key factor for the management decision. Analyzing mutiple variable and understaning the internal and external factor that contributes the sales are very importan in perdiction. This article we tried achieveing aproximate weekly sales of the retail store.
This a public dataset which are available in this [link] (https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting/data) for download.  

###Plan and build a system for storing, querying, or otherwise managing the data

The architrcture view given below is a secinore for intergating the data  flow from many IoT devices using Microsoft Azure Cloud Platform. Using managed Azure services such as IoT Hub and HDInsight will allow the customer to rapidly build and deploy a comprehensive solution with a lower operating cost.

![output](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image29.JPG)


![output](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image30.JPG)

###Produce some graphs to support your analysis

![output](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image31.JPG)

![output](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image32.JPG)

###Discover interesting relationships or phenomena from your data

Looking at the Analysis Of Variance Table (ANOVA) it was interesting that unemployment rating for the week in the region on the stores, Markdown 1:5  like what quantity was available in the store for that  week , CPI (Consumer Prince Index) for the week are signifiance to the Sale price of the Store for the week and while performing the data analysis I happen see negative values in the store Weekly sales after analyzing further, I was able to conclude those are Store return for pervious purchases.

![output](https://github.com/lokeshpy/Data_Science_and_Analytics/blob/master/images/image33.JPG)
