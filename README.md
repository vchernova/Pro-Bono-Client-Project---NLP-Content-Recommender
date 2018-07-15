# Pro-Bono-Client-Project---NLP-Content-Recommender

As my capstone project during my GA Data Science Immersive I worked with a small startup on an NLP/recommender assignment. The project was pro bono and was a great opportunity to work with a real-life data.

The data itself is proprietary but we agreed that I can share most of the code in my github portfolio. The cells won't run without the code but would give an idea of the steps and code used.

### The Problem
1. Find a way to search through a dataset of clients, based on text search term.
2. Access whether the client information in the dataset is still accurate or needs to be updated.

### Executive Summary 

The startup had different datasets with sparse information about their clients. We outer joined the datasets based on the company_id and all the data in this repo is based on that joined dataset. Additionally we looked at the crunchbase.com data, as it provided an opportunity to test our recommender on a larger dataset (crunchbase data comes with a paid membership, so I cannot share it publically here).

Thr first step was to do some EDA on the dataset. Some features were only available for less than 5% of the records. Other features were available for all. 
To fill in some of the missing values I used webscraping (selenium and beatiful soup), using the urls from the database. Urls were self-reported, so I did some cleaning. About half the urls in the database turned out to be actual company urls (I filtered out email addresses, google searches, things like www.nowebsite.com etc.). Webscraping was done on AWS ec2.
Once I scraped the text on the homepages of the urls provided and looked at the tweets (twitter account info pulled from the homepage), we used that text, combined with the company descriptions available for some of the clients in the database, to do a recommendation engine.


