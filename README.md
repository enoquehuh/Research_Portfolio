# Enoque's UX Research Portfolio
## Topics Overview
* [Project 1.](#fortnite) Games Research — Sentiment Analysis and Web Scraping ([code](#code1))
* [Project 2.](#survey) Survey Research — How does sleep deprivation affect how we interact with others? ([code](#code2))
* [Project 3.](#wine) Regression — What Makes Wine Taste Good? ([code](#code3))

# Project 1: Analyzing Player Sentiment on Fortnite's Changes to the XP System <a name="fortnite"></a>
### Introduction
* Fortnite’s recent changes to how players can get XP (experience points) was received with mixed opinions. With the purchase of the Battle Pass (that costs 950 V-Bucks or around $8), players receive in-game rewards according to their levels. Players have a chance to win all of the Battle Pass rewards by reaching level 200 by the end of the season. One way to ensure you progress through all the levels and receive all of the rewards is by completing quests. Until recently, players were given quests that could be completed throughout the season, whenever they wanted. But with the changes to the Weekly Quests, players now have exactly one week to complete these quests before they expire forever. This has caused a lot of backlash in the community and has left casual players feeling like they're missing out on a lot of XP and potential rewards, and that there’s not enough time to complete their weekly quests.
![](/image/fortnite_cover.png)
### Web Scraping the Data from Reddit
* On the Fortnite subreddit r/FortNiteBR, there was an interesting discussion thread titled: “Can We All Agree That Having 1 Week To Do Quests is Stupid?”. This post garnered tremendous attention, being one of the most upvoted discussion posts this year, with almost 6,000 upvotes. To better understand player sentiment and what people are saying about these recent changes, I decided to web scrape this whole post from Reddit, import it into a DataFrame in Python, and analyze this discussion through data.
### Sorting the Data
* Two ways we can explore the data are by filtering comments by “Best” and filtering comments by “Top”. These are what these Reddit terms mean:
1. Best: the highest upvote to downvote ratio. Basically means a lot of people agree with the comment, and there are almost no “dislikes”.
2. Top: the highest number of upvotes regardless of downvotes. 

* Although they sound similar, having both of these metrics in hand will be useful, as they tell us different things about each comment’s popularity.
* The column "upvotes" is sorting the comments by "Top", while the column "upvote ratio rank" is sorting the comments by "Best".
### Sentiment Analysis
* To better understand each comment’s sentiment, I utilized a natural language processing (NLP) package called TextBlob, to add these 2 metrics as columns to the DataFrame:
1. Polarity score: a score that ranges from -1 (which indicates negative sentiment) to 1 (which indicates positive sentiment).
2. Subjectivity score: a score that ranges from 0 (factual) to 1 (subjective). Subjective sentences generally refer to personal opinion, emotion, or judgment.
* Since this is a Reddit discussion thread, it’s expected that most comments will have high subjectivity scores.
![](/image/fortnite_sent.png)
### Data Visualizations
![](/image/fortnite_words_enhanced.png)
![](/image/fortnite_image_sentiment_1.png)
![](/image/fortnite_sentiment_2.png)
### Player Insights
* Reading through the best comments and most upvoted comments, we see that there are a few recurring topics that had great discussion, and interesting insights from players of various backgrounds.
#### 1. Fortnite shouldn't feel like a full-time job
* A recurring topic that came up in discussion was that casual players don't have time to play Fortnite every single day. They want to enjoy the game and earn their Battle Pass rewards without having to commit multiple hours every day to the game. 
* Adults make up a considerable part of the player base. They play Fortnite to unwind after a long day of working, and feel like these changes to the XP system negatively affect them. Here's what they had to say about it:
![](/image/fortnite_image_fulltime.png)
#### 2. Fear of Missing Out (FOMO) Business Model
* The FOMO monetization model incentivizes habitual playing and purchasing. Epic Games utilizes this business model extensively in Fortnite, for example: with limited-time cosmetic items, challenges, events, etc. Although this model has been extremely effective for player retention and monetization, it seems like players are fed up with it this time around. Here's what some people had to say about it:
![](/image/fortnite_image_fomo.png)
### Limitations
* Reddit is a great place to engage in discussion and learn something new. I learned so much by browsing the thread and got to understand many different perspectives and how players feel about the recent changes in Fortnite. One amazing thing about Reddit is that there's a lot of information and a lot of unfiltered opinions from many users. People can be genuine and express their true opinions because of the anonymity that Reddit provides.

* But anonymity is a double-edged sword, as there's a noticeable drawback to this: we don't know the background and age of all the users. We know that different groups of people have different experiences and play the game differently. Older players might play the game more casually and less frequently, while younger players might have more time to complete all their quests. This is something we should keep in mind when finding insights from the discussion and the data.

### Closing Thoughts
* We were able to engage in deep discussion and took a step forward in understanding player sentiment.  This project was very interesting and gave me a lot of new insights in better understanding people's different experiences and how they play Fortnite. I hope to bring my knowledge and passion for gaming, user research, and data analysis to the next opportunity that arises. Thanks for reading!

<br>

<a href="#top">Back to top</a>

# Project 2: Survey Research -- The Effects of Sleep Deprivation on Behavior <a name="survey"></a>
### Introduction
* This project is a summary of my role in one of UC Berkeley's social psychology studies. The study was a diary study that spanned for more than a year. We explored the effects of sleep deprivation on prosocial behavior. Participants were randomly assigned to either sleep deprivation or their regular sleep schedule. Participants completed daily surveys for a week, and on the final day they participated in a synchronous moderated remote session.
![](/image/survey_pic.jpg)
### Survey Design and User Interviews
* I designed and launched survey questionnaires by using Qualtrics. Participants filled out these surveys throughout the week when they were participating in the study; which served to measure their daily sleep patterns, baseline emotional state, and post-condition emotional state. Before the study officially launched, I also conducted 1:1 interviews with pilot participants to iteratively improve the survey design.
![](/image/Page2_edited.jpg)
### Running Remote Testing
* On the last day of the experiment, participants participated on a synchronous online activity, where they engaged in discussion with a study confederate. I led 40+ user testings as both the moderator and confederate of the study. The moderator facilitated the remote sessions and engaged the participants in discussion. The confederate role pretended to be a participant and interacted with the real participant by following a predetermined script.
![](/image/Page1_edited.jpg)
### Statistical Analysis in Python
* The study aimed to compare the differences in prosocial behavior and emotional states of the control group (those who were told to not change their sleep schedules) and experimental group (those who were assigned to the sleep deprivation condition). I cleaned the data, graded the psychometric scales, and performed hypothesis testing of the data by using Python and its statistical packages.
* [Here](#code2) is the full code analysis with some redacted information.

<br>

<a href="#top">Back to top</a>

# Project 3: What Exactly Makes Wine Taste Good? <a name="wine"></a>
### Introduction
* Wine preferences are very subjective as people tend to like different things. But is there a way to create an objectively good tasting wine with the help of machine learning? In this project, I aimed to find out what exactly makes wine taste good by analyzing the similarities and differences of 1600 wines. Objective features of the wine included things like: fixed acidity, residual sugars, pH level, alcohol content, etc. Each wine was rated by three different wine experts and the median of the ratings was used as the wine score which ranged from 0 (very bad) to 10 (excellent).
![](/image/wine_image.jpeg)
### Methods
* Four different regression models were used to compare results: ordinary least squares, ridge regression, lasso regression, and elastic net.
* Cross-validation was used for choosing the tuning parameters of all models except ordinary least squares.
* All code was written in Python, and packages used were: numpy and pandas for data manipulation, seaborn for data visualization, and scikit-learn for model training and cross-validation.
### Creating the Regression Models
#### 1. Ordinary Least Squares
* We want to identify the coefficients of a linear model relating wine quality to different features of the wine. Our predictors are all of the features of the wine, and our response variable is the subjective rating that each wine was given by the wine experts. The complete list of 11 features includes: fixed acidity, volatile acidity, citric acid, residual sugar, chlorides, free sulfur dioxide, total sulfur dioxide, density, pH, sulfates, and alcohol. The model was split 70/30 as train/test data.
#### 2. Ridge Regression
* To optimize our ridge regression model, we utilized the default leave-one-out cross validation, and inputted a list of ![](https://latex.codecogs.com/gif.latex?%5Calpha) values [0.1, 0.11, 0.12, ..., 2] where higher values of ![](https://latex.codecogs.com/gif.latex?%5Calpha) correspond to stronger regularization. The final ![](https://latex.codecogs.com/gif.latex?%5Calpha) value was 0.21 as shown by the graph below. We see that when ![](https://latex.codecogs.com/gif.latex?%5Calpha%3D0.21), the mean squared error is the lowest, and as ![](https://latex.codecogs.com/gif.latex?%5Calpha) increases past 0.21, the mean squared error increases rapidly. This shows that some regularization can help model performance, while too much regularization can reduce model performance.
![](/image/ridge.png)
#### 3. Lasso Regression
* For the lasso model, 5-fold cross-validation was used. We inputted a list of ![](https://latex.codecogs.com/gif.latex?%5Calpha) values [0.001, 0.002, 0.003, ..., 1] and the amount of penalization chosen was [$\alpha=0.001$](https://latex.codecogs.com/gif.latex?%5Calpha%3D0.001). We observe that in contrast to ridge regression, lasso regression gets rid of some features completely, as residual sugar as well as density are now both 0. This is because lasso (L1 regularization) is considered a more strict shrinkage operation, and leads to sparser models.
![](/image/lasso.png)
#### 4. Elastic Net
* In an elastic net model, there are 2 tuning parameters we need to consider when using cross-validation: the L1 ratio and ![](https://latex.codecogs.com/gif.latex?%5Calpha). 
* L1 ratio = 0 is ridge regression
* L1 ratio = 1 is lasso regression.
* Our model's L1 ratio chosen by cross-validation was 1, so in this case our elastic net model is the same as a lasso regression model.
### Results
#### Features
![](/image/wine_1.jpg)
#### Comparing Models on Test Data
![](/image/all_models.png)

<a href="#top">Back to top</a>


# Full Code
## Project 1 Code  <a name="code1"></a>
![](/image/Fortnite%20Project-1.png)
![](/image/Fortnite%20Project-2.png)
![](/image/Fortnite%20Project-3.png)
![](/image/Fortnite%20Project-4.png)
![](/image/Fortnite%20Project-5.png)
![](/image/Fortnite%20Project-6.png)
![](/image/Fortnite%20Project-7.png)
![](/image/Fortnite%20Project-8.png)
<br>
<a href="#top">Back to top</a>

## Project 2 Code  <a name="code2"></a>
![](/image/qualtrics_code.png)
<br>
<a href="#top">Back to top</a>

## Project 3 Code  <a name="code3"></a>
![](/image/wine_proj_full.png)

<br>
<a href="#top">Back to top</a>

