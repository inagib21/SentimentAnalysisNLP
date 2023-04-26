Overview

In this project, we conducted a Twitter sentiment analysis for the SXSW (South by Southwest) Conference using natural language processing techniques. The goal was to determine the overall sentiment of the tweets related to the conference, whether positive, negative, or neutral.

We first collected the tweets from  CrowdFlower via [data.world]https://data.world/crowdflower/brands-and-product-emotions[data.world] and then preprocessed the data by cleaning and tokenizing the text data. We then performed exploratory data analysis to gain insights into the data and its distribution.

Next, we built several machine learning models using different vectorization techniques such as CountVectorizer, TfidfVectorizer, and Word2Vec, and also applied oversampling techniques to handle class imbalance. We evaluated the models based on their accuracy and F1 scores and chose the best-performing model.

Finally, we applied the chosen model to the entire dataset and analyzed the results to determine the overall sentiment of the tweets related to the SXSW Conference. Overall, the sentiment was found to be mostly positive, with a smaller proportion of negative tweets. We also provided a classification report and confusion matrix to give more detailed insights into the model's performance.
