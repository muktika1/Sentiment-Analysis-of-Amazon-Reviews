# Analyzing-Amazon-Reviews-Sentiment-Analysis-for-Better-Consumer-Understanding

This project performs sentiment analysis on Amazon reviews using three deep learning models: VADER, RoBERTa, and the Transformer pipeline with BERT.

## Steps Involved

### Step 1: Data Upload and Library Import
We start by uploading the dataset, which originally consists of half a million records. For the analysis, we will use a subset of 10,000 rows. Next, we import the necessary libraries, including NLTK, Transformers, and Pandas.

### Step 2: Simple Preprocessing
In this step, we check for null values and duplicates in the dataset. We then add a new column called 'Sentiment', which categorizes the sentiment of users based on their ratings. The ratings range from 1 to 5, where 1 indicates the least satisfaction and 5 indicates the most. We define three sentiment labels:
- **Positive**: 4-5 star reviews
- **Neutral**: 3 star reviews
- **Negative**: 1-2 star reviews

### Step 3: Applying the VADER Model
Using the `SentimentIntensityAnalyzer`, we calculate the polarity scores for each review. These scores include negative, neutral, positive, and a compound score, which represents the overall sentiment on a scale from -1 (most negative) to +1 (most positive).

### Step 4: Function for Predicting Labels
We then create a function to predict sentiment labels based on the compound score of each review, generating a new column called `VADER_Sentiment` to display these values.

### Step 5: Applying the RoBERTa Model
After uploading the RoBERTa model, we create a function to predict sentiment labels based on the highest score among the three labels (positive, negative, neutral). We add a new column named `RoBERTa_Sentiment` to display these predictions.

### Step 6: Applying the Transformer Pipeline
The Transformer pipeline provides an intuitive interface for text classification and sentiment analysis using pre-trained models. We test the general sentiment model, but since it only outputs positive and negative labels, we switch to a specific pipeline that uses the BERT model. This model classifies reviews into five categories (1 star to 5 stars) along with confidence scores. We then convert these into three sentiment labels using a custom function.

### Step 7: Comparison of Models
We compare the predictions from the three models against the original sentiment values to evaluate their performance. The RoBERTa model achieves the highest accuracy at 0.84.

### Additional Analysis: Helpfulness Ratio
We investigate whether the helpfulness ratio correlates with user sentiment. Our findings indicate little to no correlation, suggesting that a review's helpfulness does not significantly influence its sentiment.


