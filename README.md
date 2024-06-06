# Suicidal_Risk_Detection_Using_Sentiment_Analysis
This project is aimed to develop an approach that analyzes and monitors social media activity, in this case the tweets a user uploads on his/her twitter account and classify sentiments into normal, stressed or suicidal using Naïve Bayes Classifier and SentiWordNet. The outcome of the project is a system that characterizes emotions based on social media records and detect stress or suicidal risks.

* The tweets are collected using Tweepy API for python.
* These tweets are divided into trainign and testing set.
* The training set is used to train Naïve Bayes Classifier for classification into positive and negative.
* For further classification of tweets into categories of suicidal, stressed and neutral it was required to analyze the polarity of the words for the tweets classified as "Negative". Each word will have a positive score and a negative score. 
* An average score of the negative scores of the words in a tweet is calculated based on its frequency of occurence. 

  For example - Not feeling well. Not going to school. Let's say "Not" has a negative score of 0.9. "well" has a negative score of "0.1" and rest all are neutral words hence both positive and     negative scores are 0. Hence the average would be calculated like:
  ((2 * 0.9) + (1 * 0.1) + 0 + 0 + 0 + 0) / (2 + 1 + 1 + 1 + 1 + 1)
  _The above calculation is just an example._
  
* If this value is above 0.7 then it has too many negative words and the tendency is suicidal. If the value is betwen 0.7 to 0.5 the tendency is stressed. Otherwise it is neutral. _These thresholds are defined manually. Can be changed according to requirements._
