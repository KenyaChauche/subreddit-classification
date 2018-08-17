# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 3: Web APIs & Classification

### Description

In week four we've learned about a few different classifiers. In week five we'll learn about webscraping, APIs, Natural Language Processing, and some additional classification methods. Now we're going to put those skills to the test.

For project 3, your goal is two-fold:
1. Using Reddit's API, you'll collect posts from two subreddits of your choosing.
2. You'll then use NLP to train a classifier on a binary classification problem, where each post from one of your subreddits is class `0` and all the posts from the other subreddit are of class `1`.


#### Project Summary

In this project, we will practice two major skills. Collecting data by via an API and then building a binary predictor on text data.

As we discussed earlier in the course, there are two components to starting a data science problem: the problem statement, and acquiring the data.

For this article, your problem statement will be: _What characteristics of a post on Reddit are most predictive of which subreddit that post came from?_

Reddit's API is fairly straightforward. For example, if I want the posts from [`/r/boardgames`](https://www.reddit.com/r/boardgames), all I have to do is add `.json` to the end of the url: https://www.reddit.com/r/boardgames.json

To help you get started, we have a primer video on how to use Reddit's API: https://www.youtube.com/watch?v=5Y3ZE26Ciuk

---

### Requirements

- Scrape and prepare your data using the `requests` library.
- **Create and compare two models**. One of these must be a random forest, however the other can be a classifier of your choosing: logistic regression, KNN, SVM, etc.
- A Jupyter Notebook with your analysis for a peer audience of data scientists.
- An executive summary of the results you found.
- A short presentation outlining your process and findings for a semi-technical audience.

**Pro Tip:** You can find a good example executive summary [here](https://www.proposify.biz/blog/executive-summary).

**Pro Tip 2:** Reddit will give you 25 posts **per request**. To get enough data, you'll need to hit Reddit's API **repeatedly** (most likely in a `for` loop). _Be sure to use the `time.sleep()` function at the end of your loop to allow for a break in between requests. **THIS IS CRUCIAL**_

**Pro tip 3:** At the end of each loop, be sure to save the results from your scrape as a `csv`: JSON from Reddit > Pandas DataFrame > CSV. That way, if something goes wrong in your loop, you won't lose all your data.

---

### Necessary Deliverables / Submission

- Code and executive summary must be in a clearly commented Jupyter Notebook.
- You must submit your slide deck.
- Materials must be submitted by **10:00 AM on Friday, September 7th**.

---

### Project Feedback + Evaluation

For all projects, students will be evaluated on a simple 4 point scale (0-3 inclusive). Instructors will use this rubric when scoring student performance on each of the core project requirements:

Score | Expectations
----- | ------------
**0** | _Does not meet expectations. Try again._
**1** | _Approaching expectations. Getting there..._
**2** | _Meets expecations. Great job._
**3** | _Surpasses expectations. Brilliant!_

### Rubric

Your final assessment ("grade" if you will) will be calculated based on a topical rubric (see below).  For each category, you will receive a score of 0-3.  From the rubric you can see descriptions of each score and what is needed to attain those scores.

For Project 3 the evaluation categories are as follows:
- [Organization](#organization)
- [Presentation](#presentation)
- [Data Structures](#data-structures)
- [Python Syntax and Control Flow](#python-syntax-and-control-flow)
- [Modeling](#modeling)
- [Data Collection](#data-collection)

#### Organization

Clearly commented, annotated and sectioned Jupyter notebook or Python script.  Comments and annotations add clarity, explanation and intent to the work.  Notebook is well-structured with title, author and sections. Assumptions are stated and justified.


| Score | Status                     | Examples                                                                                                                                                                                                                                         |
|-------|----------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 0     | Does not Meet Expectations | 1. Comments and annotations are **absent** <br> 2. There is no clear notebook structure <br> 3. Assumptions are not stated                                                                                                                                       |
| 1     | Approaching Expectations   | 1. Comments are present but generally unclear or uninformative (e.g., comments do not clarify, explain or interpret the code) <br> 2. There are some structural components like section/subsection headings <br> 3. Assumptions are stated but not justified |
| 2     | Meets Expectations         | 1. Comments and annotations are clear and informative <br> 2. There is a clear structure to the notebook with title and appropriate sectioning <br> 3. Assumptions are both stated and justified                                                             |
| 3     | Exceeds Expectations       | 1. Comments and annotations are clear, informative and insightful <br> 2. There is a helpful and cogent structure to the notebook that clarifies the analysis flow <br> 3. Assumptions are stated, justified and backed by evidence or insight               |

#### Presentation

The goal, methodology and results of your work are presented in a clear, concise and thorough manner.  The presentation is appropriate for the specified audience, and includes relevant and enlightening visual aides as appropriate.

| Score | Status | Examples |
|-------|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 0 | Does not Meet Expectations | 1. The problem was not well explained or ambiguous. <br> 2. The level of technicality was far above or below the target audience. <br> 3. The presentation went substantially over or under time. <br> 4. The speaker's voice was difficult to hear of unclear. <br> 5. The presentation visuals did not seem to support the talk. |
| 1 | Approaching Expectations | 1. The problem was stated but was not 100% clear. <br> 2. The level of technicality was was good at times, but too low or too high at other times given the target audience. <br> 3. The presentation was given went slightly over or under time. <br> 4. The speaker's voice was at times difficult to understand. <br> 5. The presentation visuals were generally helpful, but some of them were either too complex or disconnected from the narrative. |
| 2 | Meets Expectations | 1. The problem was framed appropriately for the audience. <br> 2. The level of technicality was appropriate to the target audience. <br> 3. The presentation was given within the allocated timeframe. <br> 4. The speaker's voice had volume and clarity. <br> 5. The presentation visuals were helpful and supportive. |
| 3 | Exceeds Expectations | 1. The problem was expertly stated and compelling. <br> 2. The level of technicality was perfect for the target audience. <br> 3. The presentation was given within the allocated timeframe and paced evenly throughout. <br> 4. The speaker's voice was clear, understandable and consistent. <br> 5. The presentation visuals provided distinct insight, supported the speaker from the background, and were not distracting. |

#### Data Structures

Python data structures including lists, dictionaries and imported structures (e.g. DataFrames), are created and used correctly.  The appropriate data structures are used in context.  Data structures are created and accessed using appropriate mechanisms such as comprehensions, slices, filters and copies.

| Score | Status | Examples |
|-------|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 0 | Does not Meet Expectations | 1. Appropriate data structures are not identified or implemented <br> 2. Data structures are not created appropriately <br> 3. Data structures are not accessed or used effectively |
| 1 | Approaching Expectations | 1. Contextually appropriate data structures are identified in some but not all instances <br> 2. Data structures are created successfully but lacked efficiency or generality (e.g., structures were hard-coded with values that limits generalization; brute-force vs automatic creation/population of data) <br> 3. Data structures are accessed or used but best practices are not adopted |
| 2 | Meets Expectations | 1. Contextually appropriate data structures are identified and implemented given the context of the problem <br> 2. Data structures are created in an effective manner <br> 3. Data structures are accessed and used following general programming and Pythonic best practices |
| 3 | Exceeds Expectations | 1. Use or creation of data structures is clever and insightful <br> 2. Data structures are created in a way that reveals significant Pythonic understanding <br> 3. Data structures are used or applied in clever or insightful ways |

#### Python Syntax and Control Flow

Python code is written correctly and follows standard style guidelines and best practices.  There are no runtime errors.  The code is expressive while being reasonably concise.

| Score | Status | Examples |
|-------|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 0 | Does not Meet Expectations | 1. Code has systemic syntactical issues <br> 2. Code generates incorrect results <br> 3. Code is disorganized and needlessly difficult |
| 1 | Approaching Expectations | 1. Code is generally correct with some runtime errors <br> 2. Code logic is generally correct but does not produce the desired outcome <br> 3. Code is somewhat organized and follows some stylistic conventions |
| 2 | Meets Expectations | 1. Code is syntactically correct (no runtime errors) <br> 2. Code generates desired results (logically correct) <br> 3. Code follows general best practices and style guidelines |
| 3 | Exceeds Expectations | 1. Code adopts clever or advanced syntax <br> 2. Code generates desired results in an easily consumable manner (e.g., results are written to screen, file, pipeline, etc, as appropriate within the flow of the analysis) <br> 3. Code is exceptionally expressive, well formed and organized |

#### Modeling

Data is appropriately prepared for modeling.  Model choice matches the context of the data and the analysis.  Model hyperparameters are optimized.  Model evaluation is robust.  Model results are extracted and explained either visually, numerically or narratively.

| Score | Status | Examples |
|-------|----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 0 | Does not Meet Expectations | 1. Data is not prepared for modeling.<br>2. Models are not implemented or not implemented fully.<br>3. Model hyperparameters are not considered.<br>4. Model evaluation is not performed.<br>5. Model results are unavailable or not extracted. |
| 1 | Approaching Expectations | 1. Data has some null values, inappropriate types and/or improper handling of categorical labels.<br>2. Model choice is questionable given the objective of the analysis.<br>3. Model hyperparameters are insufficiently or not optimized.<br>4. Model evaluation is performed but the evaluation is not generalizable.<br>5. Model results are extracted but not explained or interpreted. |
| 2 | Meets Expectations | 1. Data is free from nulls and correctly typed for the given model.<br>2. Model choice is appropriate to the analysis.<br>3. Model hyperparameters are optimally selected.<br>4. Model evaluation reflects generalizeable performance.<br>5. Model results are extracted and explained either visually, numerically or naratively. |
| 3 | Exceeds Expectations | 1. Data is pristinely prepared with creative or useful feature engineering.<br>2. Model selection is justified and demonstrates an awareness of tradeoffs.<br>3. Model hyperparameters are optimized and the optimization is demonstrated/justified.<br>4. Model evaluation reflects generalizable performance and is interpreted in the context of the analysis.<br>5. Model results are explained, interpreted and related to the overarching analysis goals. |

#### Data Collection

Data is collected from external sources through API's or scraping where applicable.  Data is collected and parsed using appropriate Python modules and effective Python code.

| Score | Status | Examples |
|-------|----------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 0 | Does not Meet Expectations | 1. Appropriate Python packages are not identified.<br>2. Data collection is unsuccessful. |
| 1 | Approaching Expectations | 1. Data collection and/or parsing is successful but unnecessarily complex because appropriate Python modules are not used of under-utilized.<br>2. Data collection is not easily repeatable. |
| 2 | Meets Expectations | 1. Data is collected and parsed using appropriate Python modules.<br>2. Data collection process is efficient and repeatable. |
| 3 | Exceeds Expectations | 1. Data collection and parsing reveals expert knowledge of the relevant Python tools.<br>2. Data collection process is efficient, repeatable and well-documented. |

---

### Why we choose this project for you?
This project covers three of the biggest concepts we cover in the class: Classification Modeling, Natural Language Processing and Data Wrangling/Acquisition.

Part 1 of the project focuses on **Data wrangling/gathering/acquisition**. This is a very important skill as not all the data you will need will be in clean CSVs or a single table in SQL.  There is a good chance that wherever you land you will have to gather some data from some unstructured/semi-structured sources; when possible, requesting information from an API, but often scraping it because they don't have an API (or it's terribly documented).

Part 2 of the project focuses on **Natural Language Processing** and converting standard text data (like Titles and Comments) into a format that allows us to analyze it and use it in modeling.

Part 3 of the project focuses on **Classification Modeling**.  Given that project 2 was a regression focused problem, we needed to give you a classification focused problem to practice the various models, means of assessment and preprocessing associated with classification.   
