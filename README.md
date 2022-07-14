# Sentiment Analysis for Twitter Data about Canadian Elections Using Python

## Background:
Sentiment Analysis is a branch of Natural Language Processing (NLP) that allows us to determine
algorithmically whether a statement or document is “positive” or “negative”.

Sentiment analysis is a technology of increasing importance in the modern society as it allows individuals and organizations to detect trends in public opinion by analyzing social media content. Keeping abreast of socio-political developments is especially important during periods of policy shifts such as election years, when both electoral candidates and companies can benefit from sentiment analysis by making appropriate changes to their campaigning and business strategies respectively.

The purpose of this project is to compute the sentiment of text information - in our case, tweets posted recently on Canadian Elections - and answer the research question: “What can public opinion on Twitter tell us about the Canadian political landscape in 2021?” The goal is to essentially use sentiment analysis on Twitter data to get insights into the Canadian Elections. For this project, we've pulled tweets regarding the Canadian elections from the announcement of the 2021 election to the day before the election for the analysis.

Central to sentiment analysis are techniques first developed in text mining. Some of those techniques require a large collection of classified text data often divided into two types of data, a training data set and a testing data set. The training data set is further divided into data used solely for the purpose of building the model and data used for validating the model. The process of building a model is iterative, with the model being successively refined until an acceptable performance is achieved. The model is then used on the testing data in order to calculate its performance characteristics.

Two sets of data are used for this project. The sentiment_analysis.csv file contains tweets that have had their sentiments already analyzed and recorded as binary values 0 (negative) and 1 (positive). Each line is a single tweet, which may contain multiple sentences despite their brevity. The comma-separated fields of each line are:

0  ID  Tweet ID

1  text  the text of the tweet

2  label  the polarity of each tweet (0 = negative sentiment, 1 = positive sentiment)

The second data set, Canadian_elections_2021.csv contains a list of tweets regarding the 2021 Canadian federal elections. The fields of each line are:

0  text  the text of the tweet

1  sentiment  can be “positive” or “negative”

2  negative_reason  reason for negative tweets. NaN for positive tweets


Both datasets have been collected directly from the web, so they may contain html tags, hashtags, and user tags.
