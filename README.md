# Wrangle and Analyse Data (WeRateDogs)
## by (Ayodele Ayodeji Fortunate)

## Background Information on WeRateDogs Tweet Archive


The dataset that I will be wrangling (and analyzing and visualizing) is the tweet archive of Twitter user @dog_rates, also known as WeRateDogs. WeRateDogs is a Twitter account that rates people's dogs with a humorous comment about the dog. These ratings almost always have a denominator of 10. The numerators, though? Almost always greater than 10. 11/10, 12/10, 13/10, etc. Why? Because "they're good dogs Brent." WeRateDogs has over 4 million followers and has received international media coverage.

This dataset archive contains basic tweet data tweet ID, timestamp, text among others for all 5000+ of their tweets as they stood on August 1, 2017.

These are the 3 datasets that I will be working with througout this project:

#####  twitter_archive_enhanced.csv

- tweet_id - Identification number of Twitter account that rates people's dogs
- in_reply_to_status_id
- in_reply_to_user_id
- timestamp
- source
- text
- retweeted_status_id
- retweeted_status_user_id
- retweeted_status_timestamp
- expanded_urls
- rating_numerator - These ratings almost always have a denominator of 10
- rating_denominator- The numerators Almost always greater than 10. 11/10, 12/10, 13/10, etc.
- name - Name of dogs
- dog_stage - stages of dogs specifically doggo, floofer, pupper and puppo

#####  image_predictions.tsv
- tweet_id- Identification number of Twitter account that rates people's dogs
- jpg_url
- img_num
- p1- is the algorithm's #1 prediction for the image in the tweet → golden retriever
- p1_conf- is how confident the algorithm is in its #1 prediction → 95%
- p1_dog- is whether or not the #1 prediction is a breed of dog → TRUE
- p2- is the algorithm's second most likely prediction → Labrador retriever
- p2_conf- is how confident the algorithm is in its #2 prediction → 1%
- p2_dog- is whether or not the #2 prediction is a breed of dog → TRUE
- p3- is the algorithm's second most likely prediction
- p3_conf- is how confident the algorithm is in its #3 prediction
- p3_dog- is whether or not the #3 prediction is a breed of dog → TRUE

##### tweet_json.txt
- tweet_id- Identification number of Twitter account that rates people's dogs 
- created_at- 
- favorite_count- Count of likes
- retweet_count- Count of retweet


## Project Overview

In this project, I will wrangle WeRateDogs Twitter data to create interesting and trustworthy analyses and visualizations. Though the Twitter archive only contains very basic tweet information.

#### Question for analysis
1. Dogs with highest favourite count
2. Dog stage with highest favourite count and retweet count
4. Year with the highest favorite count and the Dog who has the win

#### Additional gathering
1. The tweet image predictions- This file (image_predictions.tsv) is present in each tweet according to a neural network. It is hosted on Udacity's servers and should be downloaded programmatically using the Requests library and the following URL: [here](https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv)

2. Additional data from the Twitter API- Gathered each tweet's retweet count and favorite ("like") count at the minimum and any additional data I found interesting. Using the tweet IDs in the WeRateDogs Twitter archive, query the Twitter API for each tweet's JSON data using Python's Tweepy library and stored each tweet's entire set of JSON data in a file called tweet_json.txt file.

Each tweet's JSON data is written to its own line. Then read the .txt file line by line into a pandas DataFrame with (at minimum) tweet ID, retweet count, and favorite count. Note: do not include your Twitter API keys, secrets, and tokens in your project submission.

### Tasks

- Gathering data

- Assessing data

- Cleaning data

- Storing data

- Analyzing and visualizing data

- Reporting

* The report section contains both my data wrangling efforts and my data analyses and visualizations.


## Software  ans Libraries needed for this project

- Anaconda (Jupiter notebook).
The following packages (libraries) need to be installed. You can install these packages via conda or pip.
- pandas
- NumPy
- requests
- tweepy
- json
- matplotlib

os, re, nltk and %matplotlib inline are optional(though used in this project based on the nature of my wrangling process).

- You need to be able to create written documents that contain images and you need to be able to export these documents as PDF files. This task can be done in a Jupyter Notebook, but you might prefer to use a word processor like Google Docs, which is free, or Microsoft Word.
- A text editor, like Sublime, which is free, will be useful but is not required.

## Summary of Findings

I analysed the first 10 top dogs with highest favorite_count along side with their names and tweet_id from which I was able to fetch out the Dog with top favourite count with the tweet_id. My analysis shows that 3 dog with name Duddles, Stephan and Jamesy with tweet_id 879415818425184262, 807106840509214720 and 866450705531457537 respectively has a really close favorite_count.

- Duddles has the highest favorite_count of 107956.0
- Stephan has favorite_count of 107015.0
- Jamesy has favorite_count of 106827.0
based on my analysis, Duddles with tweet_id 879415818425184262 has the highest favorite_count of 107956.0

Same approach of analyses was used to generate the first top 20 Dog stages with top favourite count and retweet_count from which I was able to fetch out the Dog stages with top favourite count and retweet_count.Analysis shows that dog stage with name doggo and puppo has a really close favorite_count but huge difference in retweet_count.

- doggo has the highest favorite_count of 131075.0 and retweet_count 79515.0
- puppo has favorite_count of 132810.0 and retweet_count 48265.0

At the end of the day, dog stage with name doggo and puppo has the highest favorite_count and retweet_count

-As for the year with highest favourite, the year 2017 has highest favorite_count of 107956.0 Dog with name Duddles

## Key Insights for Presentation

For the presentation, I focus on the three questions stated for my analysis in project review section. I start by displaying the top 10 Dogs with highest favourite count then follow by Dog_stage with highest favourite_count and retweet_count and finally, I will be displaying Year with the highest favorite count and the Dog who had the win.