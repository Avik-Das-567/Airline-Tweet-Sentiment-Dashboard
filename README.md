# Sentiment Analysis of Tweets about US Airlines

### Live App: https://airline-tweet-sentiment-dashboard.streamlit.app

This project is an **interactive data visualization dashboard** built with **Python** and **Streamlit** to explore the sentiment of tweets related to major US airlines.

The application analyzes Twitter data and provides interactive visualizations to help users understand how people feel about different airlines. Users can explore tweet sentiments, visualize tweet distribution, view tweet locations on a map, and generate word clouds from tweet text.

The dashboard is deployed using **Streamlit Community Cloud**, allowing users to interact with the application directly from their browser.

## Project Overview
Social media platforms like Twitter provide valuable insights into customer opinions and experiences. This project analyzes tweets related to US airlines and classifies them into three sentiment categories:
- Positive
- Neutral
- Negative

Using **Streamlit**, the project converts a Python data analysis workflow into a **fully interactive web application**. Users can dynamically explore the dataset through different visualization components such as charts, maps, and word clouds.

The application loads tweet data, processes timestamps, and enables interactive filtering to provide a deeper understanding of customer sentiment toward different airlines.

## Dataset

This project uses the **Twitter US Airline Sentiment Dataset** available on Kaggle.

### Dataset Link: https://www.kaggle.com/datasets/crowdflower/twitter-airline-sentiment

The dataset contains tweets directed at major US airlines along with sentiment labels.

Key fields used in this project include:
- `airline` – Name of the airline mentioned in the tweet
- `airline_sentiment` – Sentiment classification (positive, neutral, negative)
- `text` – The tweet content
- `tweet_created` – Timestamp of when the tweet was posted
- `tweet coordinates` / location data – Used for mapping tweets geographically

## Features

The Streamlit dashboard provides multiple interactive components to analyze tweet sentiment.

### Random Tweet Viewer:

Users can select a sentiment type and view a **random tweet** from that category. 
This feature allows quick inspection of actual tweets classified as positive, neutral, or negative. 
The tweet is selected using a filtered query on the dataset and displayed in the sidebar. 

### Tweet Sentiment Distribution:

The dashboard shows how tweets are distributed across different sentiment categories. Users can choose between two visualization types:
- Histogram (Bar Chart)
- Pie Chart

These visualizations are created using **Plotly Express**, allowing interactive exploration of the sentiment distribution.

### Tweet Location Map:

Users can explore **where tweets were posted from** at different times of the day. 
Features include:
- Hour-of-day slider
- Map visualization of tweet locations
- Option to view raw filtered data

The application filters tweets based on the selected hour and plots them on an interactive map using Streamlit’s `st.map()` function.

This helps identify when and where users are tweeting about airlines.

### Airline-wise Sentiment Breakdown:

Users can select one or multiple airlines to compare how sentiments vary across airlines. Supported airlines include:
- US Airways
- United
- American
- Southwest
- Delta
- Virgin America

The dashboard generates a **faceted histogram** showing the number of tweets by sentiment for each selected airline.

The visualization helps answer questions like:
- Which airline receives the most negative tweets?
- Which airlines have the most positive feedback?

### Word Cloud Visualization:

The application can generate **word clouds** for tweets based on sentiment categories.

Users can select:
- Positive tweets
- Neutral tweets
- Negative tweets

The system processes tweet text and removes:
- URLs
- Mentions (`@username`)
- Retweet indicators (`RT`)

Then a word cloud is generated using the **WordCloud** library to visualize the most frequently used words. This helps identify common topics and issues discussed in tweets.

## Technologies Used

- Programming Language: Python
- Framework: Streamlit
- Data Processing: Pandas, NumPy
- Visualization: Plotly Express, Matplotlib
- Text Visualization: WordCloud

## Project Structure
```
Airline-Tweet-Sentiment-Dashboard
│
├── app.py
├── requirements.txt
├── dataset
│   └── Tweets.csv
└── README.md
```

### app.py
The main Streamlit application that handles:
- Data loading
- Interactive UI elements
- Visualizations
- Word cloud generation

### requirements.txt
Contains the list of Python dependencies required to run the project.

### dataset/Tweets.csv
The dataset containing tweets related to US airlines used for sentiment analysis.

## How the Application Works

### Data Loading
The dataset is loaded using a cached function to improve performance:
- Reads CSV file
- Converts `tweet_created` column to datetime format
- Caches the data using `st.cache_data()`

This ensures the dataset is not reloaded every time the user interacts with the dashboard.

### Interactive Sidebar Controls

The sidebar provides controls for interacting with the dashboard:
- Sentiment selector for random tweets
- Visualization type selection
- Hour-of-day slider
- Airline multi-selection
- Word cloud sentiment selector

These controls dynamically update the visualizations in real time.

## Running the App Locally

**1.** Clone the Repository
```
git clone https://github.com/Avik-Das-567/Airline-Tweet-Sentiment-Dashboard.git
```
**2.** Navigate to the Project Directory
```
cd Airline-Tweet-Sentiment-Dashboard
```
**3.** Install Dependencies

Install the required Python packages using:
```
pip install -r requirements.txt
```
**4.** Run the streamlit application:
```
streamlit run app.py
```
Streamlit will automatically launch the app at:
```
http://localhost:8501
```

## Key Highlights of the Project
- Converts a Python data analysis script into a **full web application**.
- Uses **interactive Streamlit widgets** for dynamic filtering.
- Provides **multiple visualization techniques** including charts and maps.
- Generates **word clouds** for text analysis.
- Demonstrates end-to-end **data exploration workflow**.

---
