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

## Steps to perform:
1. Data cleaning:

The tweets, as given, are not in a form amenable to analysis – there is too much ‘noise’. Therefore, the first step is to “clean” the data. Design a procedure that prepares the Twitter data for analysis by satisfying the requirements below. Remember to use the same pipeline for both datasets.

    • All emojis are removed.
    
    • All URLs are removed.
    
    • All characters in the text are in lowercase.
    
    • All stop words are removed. Be clear in what you consider as a stop word.
    
    • All punctuations are removed.

2. Exploratory analysis:

    • Design a procedure that determines the political party (Liberal, Conservative, New Democratic Party (NDP), The People's Party of Canada (PPC)) of a given tweet and apply this procedure to all the tweets in the Canadian Elections dataset. A suggestion would be to look at and count relevant words and hashtags in the tweets that identify to certain political parties or candidates. What can you say about the distribution of the political affiliations of the tweets? 
    
   • Present a graphical figure (e.g. chart, graph, histogram, boxplot, word cloud, etc.) that visualizes some aspect of the generic tweets in sentiment_analysis.csv and another figure for the 2021 Canadian Elections tweets. All graphs and plots should be readable and have all axes that are appropriately labelled. Discuss the findings.

3. Sentiment Classification - Model implementation and tuning:

    a) Machine learning models:
    
      • Split the generic tweets randomly into training data (80%) and test data (20%).
      
      • Prepare the data using TF-IDF. You may set max_features = 5000 to keep the
computation time manageable. (hint: be careful regarding which dataset to fit the
TF-IDF model on.)

      • Train seven classification algorithms on the training data from generic tweets: logistic regression, k-NN, Naive Bayes, SVM, decision trees, Random Forest, and XGBoost, where each tweet is considered a single observation/example, and the target variable is the sentiment value, which is either positive or negative.
      
      • Evaluate each model on the test data in generic tweets dataset to obtain an accuracy value.

    b) Deep learning model:
    
      • Split the generic tweets into training data (60%), validation data (20%) and test
data (20%).

      • Prepare the data using Bag of Words (word frequency). You may set
max_features = 5000 to keep the computation time manageable.

      • Define and train a deep learning model to perform the sentiment classification task. There is no specific model architecture required.
      
      • Tune two hyperparameters of the deep learning model using grid search.
      
      • Evaluate the best model on the test data in generic tweets dataset to obtain an
accuracy value.

    c) Evaluate the trained model with the best performance (considering all models from
part a) and part b)) on the Canadian Elections data. How well do the predictions match the sentiment labelled in the Canadian elections data?

    d) Propose two other evaluation metrics you could use to evaluate the models. In one to two sentences, provide reasoning for each metric.

    e) Choose the model that has the best performance and visualize the sentiment prediction results and the true sentiment for each of the 4 parties. From this model, discuss your findings and whether NLP analytics based on tweets is useful for political parties during election campaigns. Explain how each party is viewed in the public eye based on the sentiment value. Suggest one way to improve the accuracy of this model.

4. Negative Reason Classification - Model implementation and tuning:

Split the negative Canadian elections tweets into training data (70%) and test data (30%). Use the true sentiment labels in the Canadian elections data instead of your predictions from the previous part. Choose one algorithms from classification algorithms (choose any model from logistic regression, k-NN, Naive Bayes, SVM, decision trees, RF, XGBoost, deep learning model), train multi-class classification models to predict the reason for the negative tweets. Tune the hyperparameters and chose the model with best score to test the prediction reason for negative sentiment tweets.

a) Provide a few reasons why your model may fail to predict the correct negative reasons. Back up the reasoning with examples from the test sets.

b) Suggest one way to improve the accuracy of the selected model.

c) Feel free to combine similar reasons into fewer categories as long as justified the reasoning. You are free to define input features of your model using word frequency analysis or other techniques.

Write a report and an ipynb file.
