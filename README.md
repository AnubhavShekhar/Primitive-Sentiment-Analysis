# Sentiment Analysis of Twitter Data 

This Python script analyzes Twitter data to calculate positive, negative, and net scores based on the presence of positive and negative words in the tweets.

## Description

The script reads Twitter data from a CSV file (`project_twitter_data.csv`), calculates scores for each tweet, and writes the results to another CSV file (`resulting_data.csv`). It uses lists of positive and negative words from external text files (`positive_words.txt` and `negative_words.txt`).

## Installation

1. Clone the repository to your local machine:

    ```
    git clone https://github.com/AnubhavShekhar/Primitive-Sentiment-Analysis.git
    ```

2. Navigate to the project directory:

    ```
    cd twitter-data-analysis
    ```

3. Ensure Python 3.x is installed on your system.


## Usage

1. Place the Twitter data CSV file (`project_twitter_data.csv`) in the project directory.
2. Ensure the `positive_words.txt` and `negative_words.txt` files containing positive and negative words are in the project directory.
3. Run the script:

    ```
    python twitter_analysis.py
    ```

4. The resulting data will be written to `resulting_data.csv`.

## File Structure

twitter-data-analysis/  
│  
├── positive_words.txt  
├── negative_words.txt  
├── project_twitter_data.csv  
├── resulting_data.csv  
├── twitter_analysis.py  
└── README.md  

