# COVID-19 Vaccine Sentiment Analysis

A comprehensive data science project that analyzes sentiment in COVID-19 vaccination-related tweets using Natural Language Processing (NLP) techniques.

## Project Overview

This project performs sentiment analysis on a large corpus of tweets discussing COVID-19 vaccinations. Using VADER sentiment analysis and NLP preprocessing techniques, the analysis identifies positive, negative, and neutral sentiment patterns in public discourse around vaccination. The project includes exploratory data analysis, sentiment scoring, temporal feature engineering, and word frequency visualization.

## Dataset

**Source:** `data/vaccination_tweets.csv`

The dataset contains tweets with the following features:
- **Tweet metadata:** id, date, user information, engagement metrics
- **User information:** username, location, follower/friend counts, verification status
- **Tweet content:** raw text, hashtags, source platform
- **Engagement:** retweets, favorites, retweet status

### Data Characteristics
- Multiple tweet features including timestamps, user descriptions, and engagement metrics
- Tweet dates spanning across 2020
- Hashtags related to various vaccine manufacturers (Pfizer, BioNTech, Moderna, AstraZeneca, SputnikV)
- Real social media data with varying text quality and language patterns

## Project Structure

```
covid/
├── covid.ipynb                    # Main Jupyter notebook with full analysis
├── data/
│   └── vaccination_tweets.csv     # Tweet dataset
├── models/                         # Directory for trained models (future)
├── requirements.txt                # Python package dependencies
└── README.md                       # This file
```

## Methodology

### 1. **Data Preprocessing**
   - Convert text to lowercase
   - Remove Twitter handles (@mentions)
   - Remove hashtags
   - Remove URLs
   - Remove special characters
   - Remove single characters
   - Normalize whitespace

### 2. **Sentiment Analysis**
   - **Tool:** NLTK VADER (Valence Aware Dictionary and sEntiment Reasoner)
   - **Metrics:** Positive, Negative, and Neutral sentiment scores
   - **Range:** 0-1 for each sentiment component
   - Small epsilon value (10^-6) added to avoid log(0) issues

### 3. **Exploratory Data Analysis**
   - Distribution analysis of sentiment scores (PDF and CDF)
   - Sentiment cutoff identification:
     - **Positive threshold:** > 0.4
     - **Negative threshold:** > 0.25
   - Temporal feature engineering (year, month, day, quarter, season)

### 4. **Visualization & Insights**
   - Word clouds for most positive and negative tweets
   - Top 10 word frequency analysis
   - Removal of stopwords for meaningful insights
   - Word distribution comparisons between sentiment categories

## Key Features

- **VADER Sentiment Analysis:** Specialized for social media text
- **Text Preprocessing:** Comprehensive cleaning pipeline for tweet data
- **Temporal Analysis:** Feature extraction for time-based insights
- **Word Cloud Visualization:** Visual representation of dominant themes
- **Statistical Summaries:** Mean and median sentiment calculations

## Installation & Setup

### Prerequisites
- Python 3.7+
- pip or conda package manager

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Required Libraries
- `pandas` - Data manipulation and analysis
- `numpy` - Numerical computing
- `nltk` - Natural Language Processing
- `matplotlib` - Data visualization
- `seaborn` - Statistical data visualization
- `plotly` - Interactive visualizations
- `wordcloud` - Word cloud generation
- `statsmodels` - Time series analysis

## Usage

### Running the Analysis

1. Ensure all dependencies are installed:
   ```bash
   pip install -r requirements.txt
   ```

2. Open the Jupyter notebook:
   ```bash
   jupyter notebook covid.ipynb
   ```

3. Execute cells sequentially to:
   - Load and preprocess tweet data
   - Calculate sentiment scores
   - Generate visualizations
   - Analyze sentiment distributions and patterns

### Key Outputs
- Sentiment distribution plots (PDF and CDF)
- Annotated cutoff analysis for positive/negative sentiment
- Word clouds showing prominent terminology
- Top 10 most frequent words by sentiment

## Analysis Sections

### Sentiment Distribution Analysis
Explores the distribution of positive, negative, and neutral sentiment across all tweets using kernel density estimation and cumulative distribution functions.

### Sentiment Cutoff Analysis
Identifies optimal thresholds for classification:
- Visualizes distribution of most positive/negative tweets
- Shows mean and median sentiment values
- Provides context for interpreting sentiment strength

### Word Cloud Analysis
- Generates visual representations of frequently occurring terms
- Compares vocabulary between positive and negative sentiment groups
- Filters stopwords for relevance
- Top 10 word analysis with frequency counts

### Temporal Analysis
Extracts time-based features for potential trends:
- Year, month, day extraction
- Day of year and quarter calculations
- Seasonal categorization

## Results & Insights

The analysis reveals:
- **Sentiment Distribution:** Patterns in public opinion on COVID-19 vaccination
- **Common Themes:** Frequently discussed vaccine manufacturers and related topics
- **Sentiment Drivers:** Key words and phrases associated with positive/negative sentiment
- **Temporal Patterns:** Potential trends in vaccination sentiment over time

## Future Enhancements

- Build predictive models (classification, clustering)
- Train custom sentiment models beyond VADER
- Perform aspect-based sentiment analysis
- Implement real-time tweet monitoring
- Time series forecasting of sentiment trends
- User demographic analysis
- Engagement impact analysis

## Technologies Used

- **Python 3**
- **Jupyter Notebook**
- **NLTK (Natural Language Toolkit)**
- **VADER Sentiment Analysis**
- **Pandas & NumPy**
- **Matplotlib & Seaborn**
- **Plotly**
- **WordCloud**
- **Statsmodels**

## Notes

- The dataset contains real social media data with variable quality and language variations
- Sentiment analysis is probabilistic and subject to model limitations
- VADER is optimized for social media language including slang and emoticons
- Results should be interpreted with consideration for context and model accuracy

---

**Last Updated:** January 2026
