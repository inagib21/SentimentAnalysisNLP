# Overview:

In this project, we conducted a Twitter sentiment analysis for the SXSW (South by Southwest) Conference using natural language processing techniques. The goal was to determine the overall sentiment of the tweets related to Apple and Google, whether positive, negative, or neutral.

We first collected the tweets from  CrowdFlower via [Data.World](https://data.world/crowdflower/brands-and-product-emotions) and then preprocessed the data by cleaning and tokenizing the text data. We then performed exploratory data analysis to gain insights into the data and its distribution.

Next, we built several machine learning models using different the vectorization technique TfidfVectorizer, and also applied oversampling techniques to handle class imbalance. We also used a pretrained model and evaluated the models based on their accuracy and F1 scores and chose the best-performing model.

Finally, we applied the chosen model to the entire dataset and analyzed the results to determine the overall sentiment of the tweets related to the SXSW Conference. Overall, the sentiment was found to be mostly neutral, with a smaller proportion of positive and negative tweets. We also provided a classification report and confusion matrix to give more detailed insights into the model's performance.


# Business Understanding:
In this project, we will be conducting a sentiment analysis of tweets related to the South by Southwest (SXSW) conference. The SXSW conference is an annual event that showcases the latest trends in technology, music, and film. By analyzing tweets related to the conference, we aim to gain insights into how attendees and the wider public perceive the event and the brands and products showcased there. This information can be used by event organizers and exhibitors to improve the attendee experience and better understand the needs and preferences of their target audience.

# Stakeholder:
Our stakeholder is a marketing research firm that specializes in conducting market research for businesses. They are interested in understanding the sentiment around brands and products discussed at the SXSW Conference in order to provide insights to their clients. The stakeholder is particularly interested in identifying areas where their clients' brands and products can be improved or promoted based on the sentiment analysis. They would like to use machine learning techniques to automate the sentiment analysis process and make it more efficient.

# Data Understanding:
The data for this project was obtained from CrowdFlower via Data.World, and it consists of over 9,000 tweets related to the SXSW Conference. The tweets were collected during the 2013 SXSW Conference, and they contain mentions of various brands and products showcased at the event, including Apple and Google. The contributors evaluated tweets about multiple brands and products. The crowd was asked if the tweet expressed positive, negative, or no emotion towards a brand and/or product. If some emotion was expressed they were also asked to say which brand or product was the target of that emotion

The original columns in our dataset consist of:

 `tweet_text` This column contains the text of the tweet that was collected from Twitter during the SXSW conference.
`emotion_in_tweet_is_directed_at` This column contains the target of the emotion expressed in the tweet. It could be a brand, product, or service that was mentioned in the tweet
`is_there_an_emotion_directed_at_a_brand_or_product` This column contains the sentiment expressed in the tweet towards the target brand or product. The possible values are "Positive", "Negative", "Neutral".

# Methods:
### Exploratory Data Analysis
We performed exploratory data analysis to gain insights into the distribution of the data and the frequency of each sentiment label. We created histograms and bar charts to visualize the distribution of tweet lengths and sentiment labels.
### Data Preprocessing
Before building our machine learning models, we performed several preprocessing steps on the data to prepare it for analysis. We first cleaned the text data by removing URLs, special characters, and stopwords using the NLTK library in Python. We then tokenized the cleaned text into individual words and lemmatized the words using the WordNetLemmatizer.

### Modeling:
We built several machine learning models to classify the sentiment of the tweets(Naive Bayes, Random Forest, XGBoost). We used the TfidfVectorizer.to convert the text data into numerical features, and applied oversampling techniques (RandomOverSampler) to address class imbalance in the dataset. We als used a pre-trained language model, [Twitter-roBERTa-base](https://huggingface.co/cardiffnlp/twitter-roberta-base-sentiment), with the help of the Hugging Face library and PyTorch.

We evaluated the performance of each model using accuracy and F1 scores, and chose the best-performing model to apply to the entire dataset.

# Results: 
Our best performing model was the roBerta model which we trained our dataset on. the model achieved an overall accuracy of 0.80, with the Neutral class having the highest F1-score (0.87). The macro-average F1-score for all classes was 0.71, indicating that the model performed reasonably well in classifying the data.
![image](https://user-images.githubusercontent.com/45716414/235820311-c6eb413c-4d07-4513-8ba7-7564872359d0.png)


    precision    recall  f1-score   support

    Negative       0.64      0.46      0.53       126
    Neutral        0.86      0.87      0.87      1094
    Positive       0.71      0.74      0.73       568

    accuracy                           0.80      1788
    macro avg      0.74      0.69      0.71      1788
    weighted avg   0.80      0.80      0.80      1788


# Limitations and Further Analysis
- One limitation of this project is that the dataset is relatively small and may not be representative of the broader sentiment around the brands tha we analyzed.
- Another limitation is that the dataset only includes tweets from a limited time period and may not capture changes in sentiment over time.
- In future analysis, it would be interesting to explore the use of more advanced machine learning models such as GPT-3, which have shown promise in natural language processing tasks.
- Additionally, it would be valuable to conduct a more in-depth analysis of the tweets in the neutral class to determine whether they can be classified as positive or negative with greater accuracy.
- Another area for further analysis is to explore how sentiment varies across different brands and products showcased at the SXSW conference, particularly for major brands such as Google and Apple.
- Finally, it would be valuable to explore how sentiment around the SXSW conference has evolved over time and how it compares to other similar events in the industry.



