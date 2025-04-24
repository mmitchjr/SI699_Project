# Lingustic Patterns and Airbnb Neighborhood Analysis

## Overview

This project analyzes Airbnb reviews in Los Angeles, exploring the sentiment of user comments and their connection to socioeconomic indicators.

## Project Structure

### Data Sources

**Census 2020**: Demographic and socioeconomic indicators by GISJOIN.
- **ACS 2019-2023**: Additional socioeconomic data, like household income and education levels.
- **Airbnb Listings and Reviews (2020-24)**: Listing details and user feedback.

### Components
- **Data Cleaning and Preparation**: Merges and cleans data, addressing missing values, focusing on Los Angeles County.
- **Sentiment Analysis**: Uses VADER to derive sentiment scores from Airbnb reviews.
- **Mismatch Analysis**: Identifies discrepancies between ratings and sentiments.
- **Phrase Extraction**: Analyzes adjective-noun phrases to capture public sentiments.
- **Visualization**: Generates plots to visualize sentiment trends and correlations.

## Key Functions
- `clean_census_data`: Cleans Census/ACS data, imputing median values.
- `vader_clean_text`: Prepares text for sentiment analysis.
- `extract_adj_noun_phrases`: Identifies adjective-noun phrases using SpaCy.
- `display_topics`: Displays top words for topics identified by LDA.

## Usage

### 1. Dependencies
- Install necessary libraries:
  - pip install pandas numpy scipy scikit-learn nltk spacy matplotlib tqdm geopandas

### 2. Data Preparation
- Place data files in the data/directory or update file paths in the script.
- Execute the script to clean and prepare data.

### 3. Running the Analysis
- Perform EDA, sentiment analysis, and visualization.

### 4. Accessing CSV Files

The required CSV files can be found here: https://drive.google.com/drive/folders/1HgRNoompnG2fUqwg9wo_5lsfAo1ka5Qj?usp=drive_link

Census and ACS Data: 
- df_census_2020 = pd.read_csv("data/census/nhgis0002_csv/nhgis0002_ds258_2020_tract.csv")
- df_acs_2019_23 = pd.read_csv("data/census/nhgis0002_csv/nhgis0002_ds267_20235_tract.csv")
  
Airbnb Data:
- reviews_full_df = pd.read_csv("data/airbnb/reviews.csv.gz", compression="gzip")
- listings_full_df = pd.read_csv("data/airbnb/listings.csv.gz", compression="gzip")
- review_df = pd.read_csv("data/airbnb/reviews.csv")
- neighborhoods_df = pd.read_csv("data/airbnb/neighbourhoods.csv")
- listing_df = pd.read_csv("data/airbnb/listings.csv")
**Note**: Files are located in the provided Google Drive folder.

CSV Files and Visualizations: Used for exploratory analysis.

Interactive Dashboard: 
- Located in the Google Drive directory
- data > tableau_data > airbnb_census_dashboard.twb

Visualizations
- Graphs show relationships such as sentiment scores against demographic data.

Future Work
- Advanced Modeling: Explore sentiment influence beyond linear regression.
- Contextual Language Models: Use domain-specific models for refined text analysis.
- Interactive Dashboards: Deploy results with interactive tools for enhanced exploration.

External Libraries & Attribution
- This project uses VADER Sentiment Analysis by C.J. Hutto & E.E. Gilbert (2014), available under the MIT license.
- GitHub: vaderSentiment
- Paper: Hutto, C.J. & Gilbert, E.E. (2014). VADER: A Parsimonious Rule-based Model for Sentiment Analysis of Social Media Text. ICWSM-14.
