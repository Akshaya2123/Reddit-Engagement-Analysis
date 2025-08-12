# Reddit Engagement Analytics  

## Overview  
This project analyzes Reddit post engagement patterns, predicts **virality** and **controversy**, identifies trending topics, and provides interactive **EDA visualizations**.  
It combines data preprocessing, NLP techniques, machine learning models, and a Streamlit dashboard for end-to-end Reddit post analysis.  

## Features  
### 1. **Data Processing & Cleaning**  
- Removes URLs, HTML tags, punctuation, and numbers from post titles.  
- Normalizes text for consistent analysis.  
- Extracts sentiment scores using **VADER Sentiment Analysis**.  
- Generates features like:
  - Sentiment compound score & label (`positive`, `neutral`, `negative`)  
  - Day/month/year of posting  
  - Controversy ratio (comments-to-score ratio)  
  - Topic assignments from **Latent Dirichlet Allocation (LDA)**  

### 2. **Exploratory Data Analysis (EDA)**  
- Distribution of posts by subreddit, year, month, day, sentiment.  
- Sentiment trends over time.  
- Boxplots of score vs sentiment.  
- Word clouds for each topic discovered via LDA.  

### 3. **Machine Learning Models**  
#### **Virality Predictor (Logistic Regression)**  
Predicts the probability of a Reddit post going viral based on:
- TF-IDF features from post titles  
- Sentiment score  
- Number of comments  
- Subreddit subscriber count  

#### **Controversy Predictor (RandomForest Classifier)**  
Predicts likelihood of a post being controversial using:
- TF-IDF title features  
- Sentiment  
- Topic category (OneHot encoded)  
- Subreddit subscriber count  

#### **Topic Modeling (LDA)**  
- Groups posts into thematic topics  
- Identifies dominant topic for a given post  
- Detects **emerging topics** via **Holt-Winters forecasting**  

#### **Similarity Search**  
- Finds posts similar to a given title using TF-IDF + cosine similarity  

### 4. **Streamlit Dashboard**  
Interactive dashboard with four main sections:  
1. **📈 Virality & Controversy Predictor**  
   - Enter a post title → Get virality & controversy probabilities (with gauge & progress indicators).  
2. **Similar Posts**  
   - Find textually similar posts in the dataset.  
3. **Topic Trend Predictor**  
   - Identify dominant topic, detect emerging trends, and suggest best posting days.  
4. **Key Stats & EDA**  
   - Visualizations for subreddit activity, posting patterns, sentiment, and topic distributions.  

---

## Tech Stack  
- **Python**: Data processing, NLP, ML  
- **Streamlit**: Interactive web dashboard  
- **Pandas / NumPy**: Data manipulation  
- **Matplotlib / Seaborn**: Data visualization  
- **Scikit-learn**: ML models & preprocessing  
- **NLTK (VADER)**: Sentiment analysis  
- **WordCloud**: Topic visualization  
- **Statsmodels**: Time series forecasting (Holt-Winters)  
