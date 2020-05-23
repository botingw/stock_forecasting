# Stock-Price-Indicator

This project uses machine learning / deep learning models to try to predict the prices of APPLE stocks. I will first use a very simple neural network and then use LSTM, tune the models and try to see whether the prediction performance can be increased.

## Project Overview

Investment firms, hedge funds and even individuals have been using financial models to better understand market behavior and make profitable investments and trades. Machine learning engineers and fund managers are therefore working together to find financials model that can properly describe the behaviors of the stock markets.

However, statistical analysts once argued and (some of the researchers) proved empirically that stock returns (especially in U.S. Equity markets) are weak-form efficient. Therefore, historical prices bear no information on future stock price movements. They argued that stock prices are unpredictable martingale processes. 

Recent rises in big data analysis, machine learning and deep learning have brought us to new horizons. With proper usage of these algorithms, we can probably be able to find reasonable models that can indicate the movement of stock prices.

I will not simply model the prices of the stocks because it has been observed that stock prices are empirically not stationary process and linear regression on the prices against explanatory variables are likely spurious. The machine learning models associated with these problems are likely to be spurious as well.

**A more reasonable approach is to predict the stock returns instead of the prices.** Stock returns are empirically proved to be stationary processes and therefore reasonable linear regression can be modeled. Complex machine learning and deep learning models can also be implemented. An extra benefit of stock return is stock returns are normalized to some number close to zero, while stock prices have different scales for each stock throughout the times. Throughout the analysis, I will use MSE as the loss function to train the returns of stock prices.

## Problem Statement

* Use machine learning / deep learning models to build the stock returns against a list of explanatory variables, each of them properly normalized.

* Analyze the stock price (return) predictability among the provided factors.

* Hyperparameter Tuning.

* Deploy the model, such that users can get the prediction of price movements tomorrow.

## Requirements

* pandas data-reader:

  `conda install -c anaconda pandas-datareader`
  
* Environment: SageMaker with PyTorch36

## Data

I use the following three datasets to retrieve data and perform analysis:

*	[Yahoo Finance](https://finance.yahoo.com/): Web API are used to get the stock prices.

*	[FRED](https://fred.stlouisfed.org/): Web API are used to get the economic data. For example, interest rates, dollar index, etc.

*	[Professor Kenneth R. French's Website](http://mba.tuck.dartmouth.edu/pages/faculty/ken.french/): Fama-French factor models used Fama-French factors. The up-to-date factors are freely available in the website.

