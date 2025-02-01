
# Project Overview

This project focuses on sentiment analysis using data scraped from X app reviews and trending topic tweets. The goal of this project is to analyze user sentiment towards app X and understand public opinion on trending topics on social media (in the case of this project, DeepSeek).

With the ever-growing volume of text data in the digital age, sentiment analysis has become crucial to understand public opinion patterns, improve user experience, and aid data-driven decision-making. This project aims to develop an accurate sentiment analysis model to overcome the challenges of complex sentiment classification, including the analysis of opinions that are positive, neutral or negative.

# Business Understanding

### Problem Statements:
- How to implement sentimental analysis to provide relevant insights into X app reviews and trending topic tweets?
- How accurate is the sentiment analysis model built in classifying user opinions, so that it can help decision making in application development and business strategy? 
- How can optimal data processing and feature extraction improve the performance of sentimental analysis models, especially in dealing with texts with informal language, sarcasm, or ambiguous opinions?

### Goals:
- To develop sentimental analysis that can accurately classify user opinions based on data from X app reviews and trending topic tweets.
- To identify user sentiment towards app X, so as to provide insight for developers in improving features, user experience, and customer satisfaction.
- To analyze sentiment from trending topic tweets, so as to understand public opinion in real-time and provide insights for stakeholders in responding to emerging issues.

# Data Understanding

### Dataset:
 1. **Data of X application review**: 
     - `Description`: This dataset was scraped using a scrapping technique that contains content, score, app version, date the review was created, and more.
     - `Total data` : 27000 reviews
     - `Source` : Google play (taken with scrapping technique)
 2. **Tweet data trending topics (DeepSeek)**: 
     - `Description`: This dataset contains recent tweets collected using X's web scraping technique. These tweets relate to the topic of DeepSeek AI and their opinions
     - `Total data` : 3000++ tweets
     - `Source` : X applications (taken with scrapping technique)

# Method 

Here are some steps in building sentimental analysis with **`lexicon-based approach`** and **`NLP-based preprocessing`**:

## Text preprocessing

1. **Text Cleaning**:
   - Using **regular expressions (regex)** to remove URLs, numbers, special characters, mentions (@), hashtags (#), and unnecessary text.
   
2. **Case Folding and Tokenization**:
   - Using **lowercasing** to convert all text to lowercase and tokenization with word_tokenize() to split the text into individual words.

3. **Text Cleaning**:
   - Uses **regular expressions (regex)** to remove URLs, numbers, special characters, mentions (@), hashtags (#), and unnecessary text.
   
4. **Text Normalization**:
   - Uses idiom dictionary and abbreviation dictionary to replace nonstandard words with more common forms.

5. **Lemmatization**:
   - Using WordNet Lemmatizer to return words to their base form based on word category (POS tagging).

## Sentiment scoring 

1. **Sentiment Analysis with VADER**:
   - Uses NLTK's SentimentIntensityAnalyzer to calculate sentiment polarity scores based on the words used.
   
2. **Sentiment Analysis with AFINN**:
   - Uses the Afinn lexicon to provide a sentiment score based on words that have a certain weight in the AFINN list.

3. **Sentiment Analysis with SentiWordNet**:
   - Using SentiWordNet to score the polarity of words based on POS tagging.

# Modeling and Result

## X App Review Sentiment Analysis
| Model |	Accuracy of Training |	Accuracy of Training |
|---------------|--------------|--------------|
| SVM |	94.32% |	89.35% |	
|Random Forest |	97.03% |	92.59% |
|Decision Tree |	97.03% |	88.47% |


## Trending Topic Tweet Sentiment Analysis (DeepSeek) 
| Model |	Accuracy of Training |	Accuracy of Testing | Hyperparameter Tuning |
|---------------|--------------|--------------|--------------|
| SVM |	95.23% |	84.77% |	 -     |
|Random Forest |	97.47% |	88.71% | 89.10%   | 
|Decision Tree |	97.47% |	84.25% | -   |


# Conclusion
From the analysis conducted on app X reviews and trending topic tweets related to DeepSeek AI, the sentiment distribution was categorized into positive, neutral, and negative sentiments. The lexicon-based approach combined with NLP preprocessing provides significant insights into how users perceive some feature change policies on apps and trending topics on social media.

As a result, Random Forest performed best on both datasets, achieving the highest accuracy for both training and testing phases. SVM performed well but showed a larger drop in accuracy from training to testing, indicating possible overfitting. Decision Tree had a slightly lower testing accuracy, suggesting that this method cannot be generalized as well as Random Forest.

Lexicon-based sentiment analysis combined with preprocessing techniques effectively classifies sentiment from informal and unstructured text data. Random Forest outperformed the other models, which makes it the most reliable choice for sentiment classification in this case.

Tweet sentiment analysis had lower test accuracy compared to app reviews, likely due to the complexity of social media text, including sarcasm and ambiguous language. Sarcasm and ambiguous sentiment remain a challenge for lexicon-based approaches, indicating the potential benefits of integrating deep learning models for better accuracy.

This project successfully demonstrated the application of sentiment analysis in extracting insights from both app reviews and social media discussions. The results highlight that sentiment analysis can provide valuable insights for decision-making in app development, business strategy, and understanding public opinion. 
