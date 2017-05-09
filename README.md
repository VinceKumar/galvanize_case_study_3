# Galvanize Case Study #3 : Zhifan, Vineet, Chris VD, Stefan Decker

## Introduction



## Initial impressions of the data/initial issues

After doing some exploratory analysis on the user-joke rating dataset, we made some initial observations of our data:


- __There are way more users than jokes in the dataset__: There are ~1.2M ratings, ~50K users, and only 150 jokes int total. Initially this seems great as overfitting (probably) won't be a big issue.
- __Obfuscated scoring metrics__: Because our final test scoring metric only values the ranking of the recommended jokes, and not the absolute accuracy of the predicted values, we chose to use a model that is optimized to be accurate only on the top rated jokes for each user. This means RMSE as a metric is not very meaningful to us, and we need to use a different metric for our training test. The GraphLab recommender has recall score attributes which are supposed to be the recall on the top rank jokes, but we do not know how it is calculated, so there is a bit of black box going on here. 
- __Validation and the cold start problem__: Cross validation is one of the only ways to test our model's performance. Unfortunately, when you split the data into a test and train set every time you test the model it is working on a cold start problem.
- __Humor is Subjective__: It’s very hard to quantify the nature of humor, people can have subjective opinions on whether or not a specific joke is good and even experts and professionals cannot explain why a joke is funny.

