# Earnings Prediction Using AlphaVantage

This project aims to predict whether a company will outperform or underperform its earnings report using Natural Language Processing (NLP) and machine learning techniques.

<h2>Project Overview</h2>
Using data pulled from the AlphaVantage API and webscraping techniques from the BeautifulSoup Library, this project collects earnings reports and news articles for the 10 days leading up to each earnings release. NLP techniques like CountVectorizer, TF-IDF, Naives Bayes, and VADER Sentiment Analysis are used to extract meaningful features from this data. These features are then used as input for machine learning models, specifically Random Forest and SVM, to classify earnings performance as "outperform" or "underperform."

<h2>2. Data </h2>
AlphaVantage is a leading provider of various stock market data and information.  They have multiple APIs that are kept up to date inclusive of earnings reports, and news articles that can be filtered by multiple criteria.  You will need to purchase an API key to access this data as the free version only allows 20 API calls a day.  The link is as follows: https://www.alphavantage.co/documentation/

<h2> 2. Data Cleaning & EDA </h2>
One of the main issues I faced with gathering data was that the API only gave me urls and brief descriptions of articles being pulled.  In order to get the actual article, I implemented webscraping techniques from the BeautifulSoup library.  This allowed me to pull over 9,000 articles from the top websites producing articles.  Once pulled, I filtered through for valid articles based on length and was able to confirm article completeness.  

With the articles pulled, I created both count and tfidf vectorizers.  Using the vectorizers and Vader Sentiment Analysis, I was able to create a list of predictive words using Naives Bayes algorithm.  These predictive words would serve as features for my final model of predicting Earnings

<h2> Models </h2>

Because I had both vectorizers created for TFIDF and Count, I essentially created two datasets to test on my modles.  Below are the models tested with associated score, and their respective features/hyperparameters.  Overall, using the TFIDF values proved to show more predictive power than the count vectorizer.

![Model Scores Matrix](/models_matrix.png)


<h2> Future Improvements </h2>

<ul>- Try finding an API that allows pulling of article bodies from further back </ul>
<ul>- Gather more companies to test and run through the model as 277 is a very small number</ul>
<ul>- Spend more time on the article analysis as many articles mentioned more than one company and could skew the sentiment</ul>
