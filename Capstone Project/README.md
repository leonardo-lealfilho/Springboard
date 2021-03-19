# Investment Decision with Annual Financial Statements


## The Stock Market

The stock market is where a person or entity can buy and sell publicly held companies' stocks.  The stock market is very volatile and many factors, such as interest rate, unemploymet, inflation, etc.  Though investing in the stock market has become more accessible with apps such as Robinhood, figuring out a good stock to buy and sell for profit is not an easy task.  With this project I seek to build a machine learning model that will use information found in companies annual financial statement to predict whether the company's stock will be a good one year investment.

## 1. Data

The dataset used in this project was found in the [Kaggle](https://www.kaggle.com/cnic92/200-financial-indicators-of-us-stocks-20142018) website.  There are 5 different datasets that represents 5 different years worth of data ranging from 2014 to 2018.  The 2 main columns in the datasets are the price variance percentage, which indicates the percentage gain or loss through out that year, and the class column that indicates invest or decline (1 or 0) which is dictated by a positive or negative price variance percentage.


## 2. Method

As I have previously mentioned, the dataset consists mostly of information taken from publicly held companies' annual fanancial statement.  So before beginning the project, I had to take some things into consideration:

1. The model will only be able to predict whether a stock is worth buying at the beginning of the fiscal year, hold, and sell at the end of the fiscal year.

2. The class column indicates whether or not a stock is worth the investment, a 1 value means that it is and a 0 value indicates to decline that option.  

3. The features in the financial information may vary from company to company.  For example, a bigger company will have higher profits and may be able to acquire more debt.  Because of that, I felt more prudent to utilize features that takes some ratios from the financial statements to try and identify strengths and weaknesses between the companies.

## 3. Data Wrangling

