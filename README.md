# WSB Sentiment Analysis 

## Motivation 

Wallstreetbets is an internet forum on reddit known for its cynical nihilist humour and also for encouraging high risk investments. Yet despite the risky approach, the page managed to surge in popularity in 2021, when its members succeeded in moving the market. WSB, in a move against conventional investing advice, caused the stock of a dying franchise Gamestop to surge to 1700% of its price. Therefore, we know that underneath all its crass and sometimes non-politically correct jokes, the forum has some major insights into the shiftings of stock market. In this work, we take a deep dive into the content in the forum to shed light on the retail investment interest as well as its interaction with the dynamics of the U.S. stock market using a text-based approach.

## Tools used 

* [pandas](https://pandas.pydata.org)
* [sklearn](https://scikit-learn.org/stable/)
* [matplotlib](https://matplotlib.org)
* [statsmodels](https://www.statsmodels.org/stable/index.html)

## Findings 

From topic analysis, we identified the 6 most popular stock tickers on the forum: Gamestop (GME), AMC, AMD, AMZN (Amazon), Palantir (PLTR), and Nvidia (NVDA). Ideally, we want to check if this feature can be used to develop a model that helps predict the stock price in the future. However, given that our dataset only contains 30 days worth of data, we have very limited daily information to work with. So instead, we can then use linear regression to investigate the relationship between the number of times the stock is mentioned every time compared to the stock price, returns and log returns. To answer this question, we use coefficient of determination (COD) to evaluate the quality of each model. 

For the most popular stock, GME, there is moderate correlation between the price and the number of posts. However, for the other stocks, this is not obviously the case. The count correlates with the price of AMD, but not for its returns. On the other hand, Palantir’s return and log returns correlate with the post count. Next, we wanted to investigate whether the number of posts mentioning each stock can be used to predict the direction of the stock. For this problem, we used the label 1 if a stock price increases and 0 otherwise. We fit a logistic regression model for each stock. However, the results for each stock is similar: the final accuracy is approximately 0.5-0.6 with auc of around 0.5-0.7. this means that the post count alone does not account for most of the variation in the stock price. Therefore overall, the number of posts correlates with the price/performance of GME, but the results are mixed for the remaining stocks.

## Conclusion 

We also investigated the relationship between the forum content and stock prices. Overall, the number of posts correlates with the price/performance of GME, but the results are mixed for the remaining stocks. Furthermore, the correlation between the sentiment of the posts with the stock prices is still unclear and we will probably need more data to more accurately investigate the relationship. 

## Acknowledgements 

* [Hugging-face-dataset](https://huggingface.co/datasets/SocialGrep/reddit-wallstreetbets-aug-2021) 
* [Yahoo-Finance](https://finance.yahoo.com)

