# Predicting a Movie's Success Before Release 
### Team 17: Jefferson Zhan, Tony Zhang, Emily Wang, Jordan Leahey 

* * *

<p align="center">
  <img src="https://github.com/jzhan2543/fall19ml-moviepredictions/blob/master/images/cinema-clipart-food-17.png" width="150" height="150"> 
</p>

### 1) Introduction and Motivation 

#### Preface:
Our team decided to change our dataset from the one in our proposal to a different Kaggle dataset on movie ratings. This was due to the realization that our last dataset was more suited to visualization projects and unsupervised learning.

#### Overview:
Movies are such an important aspect of modern culture. The movie industry brings in billions of dollars annually. Many people will spend their free time watching movies or plan a hangout at the movie theaters, but how many times have you finished watching a movie and realized what a waste of time and money it was, despite being very excited over the premise or actors?

What makes a movie truly successful then? There are movies with budgets in the hundreds of millions but still flop in the box office. Is there a way to use the numbers and data behind each movie to predicts its success beforehand?

#### Goal:
Be able to predict whether a movie will be successful depending on its budget, runtime, and popularity *. This prediction would help both producers and the audience. Correlations will give directors and writers a rough guideline of past successes, and the audience can use this information to determine if a movie is worth their time and money to watch in theaters.

>*Popularity for each movie is determined by the number of votes, views, favorites, and watchlist adds per day compared the the previous days score as well as the release this. TMDB uses this metric to boost their search results as well as show users what is popular at the time of their visit to the website. Even before a movie is released popularity can be used to show growing interest in the movie as it gets closer to the release date and how the movie has been received after it has been released.

* * * 

### 2) Dataset and Methods 
#### TMDB 5000 Movie Dataset from Kaggle
- https://www.kaggle.com/tmdb/tmdb-movie-metadata 

The Kaggle dataset uses information from TMDB due to copyright concerns from the IMDB website.

This dataset contains two data sources: tmdb_5000_credits and tmdb_5000_movies. 

*tmdb_5000_credits features:*
- movie_id, title, cast, crew

*tmdb_5000_movies features:* 
- budget, genres, homepage, id, keywords, original_language, original_title, overview, popularity, production_companies, production_countries, release_date, revenue, runtime, spoken_languages, status, tagline, title, vote_average, vote_count   

Our team decided to combine these two data sources, so we would have access to all these features. 

<p align="left">
  <img src="https://github.com/jzhan2543/fall19ml-moviepredictions/blob/master/images/dataHead.PNG"> 
</p>


#### Preprocessing: 

We chose to drop 'homepage' and 'vote_count' from the features as those would not be part of our definition of a "successful" movie. Data values such as duration which were equal to zero were also cleaned up.

#### Pairwise Plot 

<p align="center">
  <img src="https://github.com/jzhan2543/fall19ml-moviepredictions/blob/master/images/pairwise.PNG" width="900"> 
</p>

WHAT CONCLUSION FROM PAIRWISE PLOT?

* * * 

### 3) Feature Selection and Data Manipulation 

To prepare our data, our team decided to use a binary classification system, where we chose threshold values for certain columns of the data, and for each movie, we set that column to either a 1 or a 0. This allowed use to certain algorithms to determine whether or not a movie would be successful. 

For example, for the budget, we added seven new columns as classifiers to cover the possible range. So if a movie's budget is less than $5,000,000, then it is considered 'extremelylow' budget and would have a 1 in the column. If a movie's budget is great than $150,000,000, then it is considered as 'blockbusterhigh'. 

A similar process was followed for converting the 'title_month' and 'duration' of each movie. 

WHATS HAPPENING WITH GENRE? getting flattened out? 

Our team decided to deem a movie as "successful" using three metrics: 'Popularity Success', 'Vote Success', and 'Commercial Success'.
1. 'Popularity Success':  if a movie's popularity feature is greater than the mean of all popularity scores, __do we know the mean___. 
2. 'Vote Success': likewise if the voting_average of a movie is higher than the mean. 
3. 'Commercial Success': if a movie's gross profit exceeds its budget. 

A movie will be considered *truly successful* if it fits all three of these criterion. The 3 pie graphs below shows a breakdown of the percentage of movies in the dataset that fulfill each success factor. 

Popularity Sucess          |  Vote Success             | Commercial Success
:-------------------------:|:-------------------------:|:------------------:
<img src="https://github.com/jzhan2543/fall19ml-moviepredictions/blob/master/images/popularitySuccess.PNG" width="250" /> | <img src="https://github.com/jzhan2543/fall19ml-moviepredictions/blob/master/images/voteSuccess.PNG" width="300" />  | <img src="https://github.com/jzhan2543/fall19ml-moviepredictions/blob/master/images/commercialSuccess.PNG" width="350" />


conditionals for SVM???? 

So out of all the movies in our dataset, only 21.3% are truly successful using our team's definition.

<p align="left">
  <img src="https://github.com/jzhan2543/fall19ml-moviepredictions/blob/master/images/success.PNG" width="200"> 
</p>

In order to further determine what features play an important role in determing a movie's success, we graphed a few visualizations (THIS COULD BE BETTER WORDED) and decided to drop title_year and duration. (BUT WHY?) 

Popularity Sucess          |  Vote Success             | Commercial Success
:-------------------------:|:-------------------------:|:------------------:
<img src="https://github.com/jzhan2543/fall19ml-moviepredictions/blob/master/images/budgetxSuccess.PNG" width="300" /> | <img src="https://github.com/jzhan2543/fall19ml-moviepredictions/blob/master/images/monthxSuccess.PNG" width="300" />  | <img src="https://github.com/jzhan2543/fall19ml-moviepredictions/blob/master/images/durationxSuccess.PNG" width="300" />

* * * 

### 4) 

### 5) Supervised Learning Models 

#### Decision Tree - Cross Validation Score  

Accuracy: 74%

#### Random Forest Tree Model

Accuracy: 76% 

#### K-nearest neighbors

Accuracy: 81%

#### SVM 

Accuracy: 81% 

* * * 

### 6) Conclusion 


`````````````````Where to move this????``````````````````````

First we took a look at the correlation matrix to see if any of the features had an impact on popularity. 
<p align="center">
  <img src="https://github.com/jzhan2543/fall19ml-moviepredictions/blob/master/images/correlationMap.PNG" width="500"> 
</p>

```````````````gotta move````````````````
