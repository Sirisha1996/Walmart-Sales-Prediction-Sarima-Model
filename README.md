# Walmart-Sales-Prediction-Sarima-Model

1.Problem Statement:
We are provided with historical sales data for 45 Walmart stores located in different regions. Each store contains several departments, and we are tasked with predicting the department-wide sales for each store.

2.Dataset Overview:
The dataset we selected contains collected information concerning 45 Walmart stores located in different regions. The data covers from 2010-02-05 to 2012-11-01, with a total of 421570 values to test the efficacy and efficiency of the models. Our dataset included features such as the store number, the date the data was collected, the temperature that day, the Consumer Price Index (CPI) and whether that day was a Holiday or not. We are tasked to predict the sales for each of these stores.

3.Preprocessing: 
First, we imported any of the necessary libraries into the notebook, then the dataset from Kaggle. We then checked for and filled or removed any null values that presented themselves in the data. Lastly, we merged the features with the training data based on Store Number, and by the Date in the data.

4.Exploratory Data Analysis and Visualization:
Performed exploratory data analysis on Walmart sales dataset, initially identified the sales in holidays and non-holidays using sns-barplot and concluded that sales are high on holidays.

Then we counted the total number of stores, and it is 45. Among them, there are three different types of stores, Store A, Store B and Store C. Found the number of Store A, B and C as 22, 17 and 6 respectively, using this we plotted a pie-chart and a boxplot which represents the percentage of three different types of stores. Here Store A is higher in number while comparing with B and C

Next, we tried to find the relationship between Customer Price Index (CPI) and Weekly Sales using a scatter plot. Three clear clusters are formed but there is no relationship between CPI and Weekly Sales.

Following this, compared Weekly Sales and Temperature to find whether the temperature of the region has any impact on sales. Plotted a scatter plot, and found there is no relationship between the temperature of the region and sales

Lastly, plotted weekly sales and found that sales peak is inflated in a periodic interval, and we can assume that it will during the month of November and December as it is the month of Thanksgiving and Christmas.

5.SARIMA Without Additional Variables:
We implemented the SARIMA model without additional variables. Trained the dataset using the train data set. Developed the model to forecast the sales for unseen data which is the test data set. We considered the features - Date, Weekly sales and if the day is a holiday. Calculating the weekly sales and for the training set, using these columns only. 

Before building the models, we checked the ACF and PACF plots to determine the value of p,d,q to be used for the model. These plots show the order of AR and MA and seasonality order to fit the best SARIMA model 

To find the best model, observing the diagnostics of the models, we can say that the data doesn’t follow any trend and the histogram can be interpreted as normal distribution. In the Normal Q-Q plot, all points lie on straight line. And in the correlogram, no values are significant except lag3. 

From the plot, the forecasts from the SARIMA model are without using any additional variables. The time series plot with green line represents the forecasted sales. The grey shade around the line indicates the confidence intervals. The orange line represents the actual sales data.

The MSPE score for this model obtained is 342.121

6.SARIMA With Additional Variables
Like the previous model, we implemented the SARIMA model by adding additional variables now. Adding the seasonal index as the new column, we create the training data set. Trained the model with the given dataset and built the model to fit the data. 

Finding the best model by observing the diagnostics of the models, we can say that the data doesn’t follow any trend and the histogram can be interpreted as normal distribution. In the Normal Q-Q plot, all points lie on straight line. And in the correlogram, we can observe that lag values are not falling in 95% confidence interval. 

From the plot, the forecasts from the SARIMA model using additional variables. The time series plot with green line represents the forecasted sales. The red line represents the actual sales data.

The MSPE score for this model obtained is 104.62. 



