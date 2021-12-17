# Sentiment-Analysis-Telegram-Crypto
Sentiment Analysis of the Text Messages from the Crypto.com Telegram Group (https://t.me/CryptoComOfficial) from May 1st to May 15th 2021.

I have used Vader Sentiment Analysis Framework for performing the semantic Analysis. Vader stands for (**V**alence **A**ware **D**ictionary and s**E**ntiment **R**easoning) and is popular rule-based sentiment analyzer. Vader is optimized of Social Media and yields good results when used with data from Twitter, Facebook, etc. 

It provides sentiment of the given input message by providing four attributes:
1. neg -> Probability of the given input sentence to be negative.
2. neu -> Probability of the given input sentence to be neutral.
3. pos -> Probability of the given input sentence to be positive.
4. compound -> Normalized sum of positive, negative & neutral scores between -1(most extreme negative) and +1 (most extreme positive). 

The sum of neg, neu and pos will always add up to 100%. The more Compound score closer to +1, the higher the positivity of the text.

After calculating the sentiment for every English text message containing either SHIB or DOGE, the average sentiment is calculated for every single day and grouped into two categories: 
1. Positive Sentiment: The average Compound Score for that day is > 0.
2. Negative Sentiment: The average Compound Score for that day is < 0.

The results obatine are plotted in a histogram and the following inferences can be made:
1. The Majority of the days between May 1 to May 15 2021 have positive sentiment towards DOGE / SHIB.
2. Only on May 6th (total of 45 messages), there was a negative sentiment towards DOGE / SHIB.
3. The majoriy of English messages regarding DOGE / SHIB was between May 8 to May 10 (corresponding to a total of ~60% of the messages). All corresponding to positive sentiment.

![Sentiment Analysis Results](https://github.com/ssurananitish/Sentiment-Analysis-Telegram-Crypto/blob/main/Sentiment_Analysis_Plot.png)

Steps to reproduce the results:
1. Create the environment using the requirments.txt file 
```
pip install requirements.txt
or
conda install requirements.text
```
2. Run the Jupyter Notebook [Sentiment_Analysis_Crypto](https://github.com/ssurananitish/Sentiment-Analysis-Telegram-Crypto/blob/main/Sentiment_Analysis_Crypto.ipynb)

Possible Sources of Disprencies:
1. Stochastic nature of the SpaCy Language Model. (Can provide two different results for the same Input Message)
2. Stochastic nature of the VADER Sentiment Analysis Model. (Can provide slightly different polarity values for the same Input message)
