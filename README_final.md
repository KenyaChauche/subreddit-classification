# Distinguishing Abuse
## Natural Language Processing and Classification Modeling

### Problem Statement 
Relationship abuse is frighteningly common, with 1 in 4 women and 1 in 9 men experiencing physical violence, sexual violence, and/or stalking in the US. Abuse can often go unreported by the survivor or unrecognized by those on the outside, making it difficult to get resources to those who need them. Even after escape from an abuser, a survivor is likely to carry trauma with them, which will often manifest as depression, anxiety, or suicidal thoughts. Abuse is a sensitive topic, and is difficult for a survivor to bring up, even when talking with a mental health professional. This project aims to identify language patterns survivors use that could distinguish them from those without abusive experiences. This could be of use to mental health professionals, especially those who communicate with their clients through text (text hotline, text-based therapy, etc). Detecting these language patterns could be valuable in granting further context into how a mental health professional can interact with their client in an aware and thoughtful way without forcing the client to revisit tramatic experiences. 


### Data Gathering
Two subreddits were used as data sources for this project: r/Relationships and r/AbusiveRelationships. Reddit is a gathering of online forums, with communities organized into subreddits. Subreddits are places for people with common interests, backgrounds, or needs gather to interact, share stories, memes, advice, or resources, and are referred to as "r/" followed by their subreddit name. 

r/Relationships is a community for people seeking assistance with interpersonal relationship challenges. Redditors will post about a challenge they are facing, and other redditors will respond in comment threads with empathy, advice, or resources. Challenges posted about in this subreddit can range from communication issues, infidelity, challenges with a partner with disabilities, even to advice on how to help a partner handle recently diagnosed lactose intolerance. This is a highly trafficked and popular subreddit, with top posts from the month garnering 200 - 350 comments each. 

r/AbusiveRelationships is a community for people who have experienced or are currently experiencing abuse in a relationship. This community is also geared towards empathy, advice, and resources, though what is offered in this community is much more specific and sensitive. Discussions here can range from a redditor searching for support before facing their abuser in court, someone needing advice on how to escape from an abusive relationship, to someone sharing resources such as legal or mental health support.


Samples of posts from each subreddit were collected using the [Pushshift API](https://github.com/pushshift/api). Three rounds of posts were collected from each: one round from the most recent month, one round from the previous month, and one round from any time preceding the most recent two months (starting with more recent posts and working backwards). In an effort to gather posts that had resonated with the community, post participation was taken into account by setting comment thresholds. For r/Relationships, posts that were within the timeframe and had over 100 comments were sampled, while sampled posts from r/AbusiveRelationships needed to have a minimum of 3 comments. These numbers were arrived at after reviewing the number of comments that are typical for top posts for the day and week in both subreddits. r/Relationships is a popular and highly trafficked subreddit, with 2.8 million members, while r/AbusiveRelationships has 20.3 thousand. 

Data sampled was organized in the following manner: 
| Name | Description | 
| :---: | :--- | 
| selftext | Text from the body of the post | 
| title | Title of post | 
| subreddit | Subreddit of origin | 
| text | (made as part of project) a combination of the selftext and title of the post, to have all post text in one field | 

Data cleaning involved removing puncuation, lemmatizing, and making all words lowercase. Links were also removed from the posts, but the rest of the text was left intact. 

### Modeling
Four different models were tested for this project: two models with the CountVectorizer transformer, and two with the TFIDFVectorizer transformer. These were combined with two different classifying estimators (resulting in four total model tests): Logistic Regression and Multinomial Naive Bayes. Sklearn's GridSearchCV was used to tune hyperparameters for each model configuration. With the inital set of hyperparameter values, the program took a substantial amount of time to run, so the hyperparameter values were broken up into subsets instead. While this probably resulted in a similar overall runtime to the original configuration, this allowed for updates on the results of each hyperparameter list to be printed along the way. 

In the end, the model built with TFIDFVectorizer and Logistic Regression was the best model, with `ngram_range` of (1, 2), sklearn's preset list of English stopwords removed, and `max_features` of 300. This had a training accuracy score of 93.9% and a test accuracy score of 91.6%. While other model configurations and hyperparamter values produced models with better accuracy scores, the discrepancy between the training and test scores was greater. This model was chosen for having relatively high scores along with better consistency between training and test sets. 


### Observations
When looking at the most frequently used words for both groups, the top 30 words do not seem distinctive. For both groups words like "relationship," "kind," "know," and "just" were common. When looking at the top 300 words for each group and filtering for those that did not overlap, words and phrases that were associated with abuse were much more intuitive and less revolutionary. These are words such as "abusive," "abusive relationship," "scared," and "control." 


### Conclusion
There is a distinct and discernable difference between posts made to r/Relationships and r/AbusiveRelationships, denoting that there is a distinct use of language between those are experiencing challenges in a relationship as opposed to those who experience abuse in a relationship. The overarching pattern of this distinguishing language, however, is a distinct presence of the word "abuse" and other forms in posts from r/AbusiveRelationships. 

The best model to use for distinguishing between these two groups as handled in this project is a TFIDFVectorizer in concert with Logistic Regression classification. In addition to producing some of the highest accuracy scores, the Logistic Regression estimator grants the benefit of a customizable classification threshold. In future renditions of this project, adjustment of this hyperparamter would be an interesting aspect to explore. 

Another suggestion for future renditions of this project is to add the word "abuse" and other forms of that word to the list of stopwords that are scrubbed from the dataset when modeling. This would make the distingushing language between the groups less intuitive and more nuanced, thereby providing more valuable context for mental health professionals. Identifying the language patterns beyond the word "abused" would be much more valuable for mental health professionals interacting with clients who are not forthcoming about the presence of abuse in their backgrounds. 


### Sources 
https://ncadv.org/statistics
https://assets.speakcdn.com/assets/2497/domestic_violence_and_economic_abuse_ncadv.pdf
https://assets.speakcdn.com/assets/2497/domestic_violence_and_psychological_abuse_ncadv.pdf
https://www.verywellmind.com/signs-someone-is-being-abused-66535