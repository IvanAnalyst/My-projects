# My portfolio projects
## Project 1: [ML stock price prediction](https://github.com/IvanAnalyst/My-projects/blob/main/ML%20stock%20price%20prediction/ML%20stock%20price%20prediction.ipynb)
&nbsp;&nbsp;&nbsp;&nbsp;In this project I have created a flexible predictive neural network model with LSTM (Long Short Term Memory) layers using python (Jupyter notebook) to predict stock prices. \
&nbsp;&nbsp;&nbsp;&nbsp;Firstly, I get a list of all NASDAQ exchange traded ticker symbols using [yahoo_fin](https://github.com/atreadw1492/yahoo_fin), because of the difficulties with retrieving this info with [yfinance](https://github.com/ranaroussi/yfinance). Then I drop the symbols that will not contain enough data for comparative analysis. I sample 10 random ticker symbols from the filtered list (I use a random seed so that all results can be reproduced) and using the [Yahoo!Finance's API](https://github.com/ranaroussi/yfinance) gather daily Adjusted Close prices for each of the tickers from 2018-01-02 to 2023-06-30. I split the sample into training (80% of the total data) and testing (20% of the total data) subsamples. Training data is used to tune model parameters while the testing subsample is left for performance valuation. I am using supervised learning: the model is trained using labeled data. This model predicts the Adjusted Close price one day into the future based on 60 previous days (both values can be changed). The performance is evaluated using RMSE (Root Mean Squared Error) and MAPE (Mean Absolute Percentage Error). If we consider a 5% upper bound on MAPE as a critical point of model rejection, then all 10 stock forecasts are of desirable accuracy, since their MAPE's are below 5% on test data, while many are even below 2%. The accuracy results can be seen below:

<img src="ML stock price prediction/Accuracy.png" class="img-responsive" alt="">

&nbsp;&nbsp;&nbsp;&nbsp;The model is flexible and can be used to predict multiple stocks for multiple periods (not just days) into the future. You can see the full code [here](https://github.com/IvanAnalyst/My-projects/blob/main/ML%20stock%20price%20prediction/ML%20stock%20price%20prediction.ipynb).

## Project 2: [Financial Statements KPI Analysis](https://github.com/IvanAnalyst/My-projects/blob/main/Financial%20Statements%20KPI%20Analysis/Web%20Link.md)
&nbsp;&nbsp;&nbsp;&nbsp;In this project I have created a dynamic dashboard of the S&P500 companies' annual Balance sheets and Income statements for the years 2017-2022 using python and Power BI. Below you can see the HTML version of the dashboard (for a web version you can click [here](https://app.powerbi.com/view?r=eyJrIjoiMDcyNWM2NTQtZDMwMi00YjdiLTllMDgtYzg3ZmZkYWRmNzhlIiwidCI6ImM4YzY5YWFlLTMyYmEtNDNkMS05ZjU5LWY5OGM5NWZiMjI3YiIsImMiOjl9)):

<iframe title="Statements" width="100%" height="800" src="https://app.powerbi.com/view?r=eyJrIjoiMDcyNWM2NTQtZDMwMi00YjdiLTllMDgtYzg3ZmZkYWRmNzhlIiwidCI6ImM4YzY5YWFlLTMyYmEtNDNkMS05ZjU5LWY5OGM5NWZiMjI3YiIsImMiOjl9" frameborder="0" allowFullScreen="true"></iframe>

&nbsp;&nbsp;&nbsp;&nbsp;The dashboard contains 2 filters: by ticker symbol (company) and report year. The data dynamically updates, provides information on the idustry and sector of the company and computes financial KPI's:
* **Profitability ratios:** Gross Margin (%), Net Profit Margin (%), Operating Margin, Return On Assets, Return On Equity
* **Liquidity ratios:** Current Ratio, Quick Ratio, Cash Ratio
* **Solvency ratios:** Debt-to-Assets Ratio, Interest Coverage Ratio, Debt-to-Equity Ratio  

&nbsp;&nbsp;&nbsp;&nbsp;Firstly, Using [yfinance](https://github.com/ranaroussi/yfinance) and [yahoo_fin](https://github.com/atreadw1492/yahoo_fin) I gather ticker symbols in the S&P500 index as well as their full company names, industry and sector. The reasoning is simple: S&P500 contains companies with the highest market cap and these big companies are likely to have financial statements data. I loaded the income statements and balance sheets of  using [SimFin API](https://github.com/SimFin/simfin). In order to do so you need an API key, which can be obtained for free [here](https://www.simfin.com/en/). I do not have any affiliation with SimFin and just thought that their product and python support are great. You can view full code [here](https://github.com/IvanAnalyst/My-projects/blob/main/Financial%20Statements%20KPI%20Analysis/Files/SimFin%20API%20data%20collection%2C%20reshaping%20and%20more.ipynb). \
&nbsp;&nbsp;&nbsp;&nbsp;However, the default shape was not fit for how I want to visualize the statements in Power BI, so I create a function to reshape the data accordingly. Then I compile the dataframes to Excel files and load them into Power BI. I make necessary relationships and create all the measures with DAX, including all line items you see in the statements as well as the KPI's. I designed the layout and theme of the dashboard myself. You can find all the Excel files used in this project [here](https://github.com/IvanAnalyst/My-projects/tree/main/Financial%20Statements%20KPI%20Analysis/Files). To download the project as a pbix click [here](https://github.com/IvanAnalyst/My-projects/raw/main/Financial%20Statements%20KPI%20Analysis/Files/Statements.pbix).

## Project 3: []()
