# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 3: Web Scraping & Classification

### Description

In week four we've learned about a few different classifiers. In week five we'll learn about webscraping and Natural Language Processing, and some additional classification methods. Now we're going to put those skills to the test.

### Scenario

You're fresh out of your Data Science bootcamp and looking to break through in the world of freelance data journalism. Nate Silver and co. at FiveThirtyEight have agreed to hear your pitch for a story in two weeks!

Your piece is going to be on how to create a Reddit post that will get the most engagement from Reddit users. Because this is FiveThirtyEight, you're going to have to get data and analyze it in order to make a compelling narrative.

#### Project Summary

In this project, we will practice two major skills. Collecting data by scraping a website and then building a binary predictor.

As we discussed in week 2, and earlier today, there are two components to starting a data science problem: the problem statement, and acquiring the data.

For this article, your problem statement will be: _What characteristics of a post on Reddit are most predictive of the overall interaction on a thread (as measured by number of comments)?_

Your method for acquiring the data will be scraping the 'hot' threads as listed on the [Reddit homepage](https://www.reddit.com/). You'll acquire _AT LEAST FOUR_ pieces of information about each thread:
1. The title of the thread
2. The subreddit that the thread corresponds to
3. The length of time it has been up on Reddit
4. The number of comments on the thread

Once you've got the data, you will build a classification model that, using Natural Language Processing and any other relevant features, predicts whether or not a given Reddit post will have above or below the _median_ number of comments.

**BONUS PROBLEMS**
1. If creating a logistic regression, GridSearch Ridge and Lasso for this model and report the best hyperparameter values.
1. Scrape the full text of the threads using Selenium (you'll learn about this in Webscraping II).
2. Write the actual article that you're pitching and turn it into a blog post that you host on your personal blog.

---

### Requirements

- Scrape and prepare your data using BeautifulSoup.
- **Create and compare two models**. One of these must be a random forest, however the other can be a classifier of your choosing: logistic regression, KNN, SVM, etc.
- A Jupyter Notebook with your analysis for a peer audience of data scientists.
- An executive summary of the results you found.
- A 10-12 minute presentation outlining your process and findings for a semi-technical audience. The reason we say 'semi-technical' is that FiveThirtyEight wants to see how you plan to explain your findings in your article, and their audience is likely readers who are familiar with and interested in data / statistics, but are not experts. This means that if you'd like to talk about your model works you can, but explain what exactly your model does at a high-level.

 **Pro Tip:** You can find a good example executive summary [here](https://www.proposify.biz/blog/executive-summary).

 **Pro Tip 2:** When building your webscraper, use the `sleep` function to make time in between your individual requests.

 **Pro Tip 3:** Build your scraper, and rigorously test it on a few pages to make sure it works before setting it loose on all of Reddit.

 **Pro tip 4:** Scrape early, scrape often. Unlike earlier projects, you're collecting your own data, and you won't be able to even start modeling until you've collected all of this.

**Pro tip 5:** Save your results to a .csv or .txt file whenever you scrape. If you just keep your results in memory, if you computer crashes or shuts off, or you accidentally close your Jupyter notebook, you'll lose your data.

---

### Necessary Deliverables / Submission

- Code and executive summary must be in a clearly commented Jupyter Notebook.
- You must submit your slide deck.
- You must, at minimum, have a link to your slides and a link to your Jupyter notebook on your personal static site.
- Materials must be submitted by 9 a.m. Friday, November 3rd EST. You will submit a link to your slides, your link to your Jupyter notebook, and your link to your static site via Google form. If your slides are not hosted online, you may Slack your slides to a DSIR.

---

### Dataset

1. We'll be utilizing a dataset derived from live web data: [Reddit.com](https://www.reddit.com/)

2. To get the data, we will use the requests library (or urllib) and BeautifulSoup to scrape the webpage.

---

### Suggested Ways to Get Started

- Read the docs for whatever technologies you use. Most of the time, there is a tutorial that you can follow, but not always, and learning to read documentation is crucial to your success!
- Document **everything**.
- Look up sample executive summaries online.

### Additional Resources
- [Advice on How to Write for a Non-Technical Audience](http://programmers.stackexchange.com/questions/11523/explaining-technical-things-to-non-technical-people)
- [Documentation for BeautifulSoup can be found here](http://www.crummy.com/software/BeautifulSoup/).

---

### Project Feedback + Evaluation

Data science is a field in which we apply data to solve real-world problems. Therefore, projects and presentations are means by which we can assess your ability to solve real-world problems in a data-driven manner.

Your final assessment ("grade," if you will) will be calculated based on a [topical rubric](https://docs.google.com/spreadsheets/d/19k8OZ42xzr7v9GDv2IUyD175yGjJlwTNokcufwX9Ago/edit?usp=sharing). For each category, you will receive a score of 0-3. From the rubric you can see descriptions of each score and what is needed to attain those scores. Make sure you look at the "Rubric P3" tab of the [spreadsheet](https://docs.google.com/spreadsheets/d/19k8OZ42xzr7v9GDv2IUyD175yGjJlwTNokcufwX9Ago/edit?usp=sharing).
