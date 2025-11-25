Project Title

Tweet Sentiment Analysis Using VADER

Short Description

This project analyzes the sentiment of tweets using the VADER (Valence Aware Dictionary and sEntiment Reasoner) sentiment analysis tool. It accepts tweet text from a CSV file (or scraped tweets if enabled) and classifies each tweet as positive, negative, or neutral based on sentiment scores. The output is saved as a CSV file.

How to Run

1. Install Dependencies

Make sure Python 3 is installed, then install the required libraries:
pip install -r requirements.txt
2. Run Sentiment Analysis on a CSV File

Your CSV must contain a column named text.
python source_code/sentiment_analysis.py --mode file --input sample_input.csv --output sample_output.csv
3. (Optional) Scrape Tweets and Analyze

If snscrape is installed, you can scrape tweets without API keys:
python source_code/sentiment_analysis.py --mode scrape --query "#python" --limit 50 --output 

sample_output.csv

Sample Input (sample_input.csv)
text
I love Python! It's so powerful and fun. #programming
This new update ruined everything. Very disappointed.
It's okay — not great, not awful.
What a beautiful day! Feeling grateful.
Worst experience ever. I hate it.

Expected Output (sample_output.csv)

id,text,compound,neg,neu,pos,label
1,"I love Python! It's so powerful and fun. #programming",0.7096,0.0,0.548,0.452,positive
2,"This new update ruined everything. Very disappointed.",-0.5994,0.468,0.532,0.0,negative
3,"It's okay — not great, not awful.",0.0,0.0,1.0,0.0,neutral
4,"What a beautiful day! Feeling grateful.",0.6249,0.0,0.634,0.366,positive
5,"Worst experience ever. I hate it.",-0.8268,0.542,0.458,0.0,negative

Libraries Used

vaderSentiment
snscrape (optional, for scraping tweets)
csv (Python built‑in)
argparse (Python built‑in)