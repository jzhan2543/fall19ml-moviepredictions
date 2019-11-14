# Predicting a Movie's Success Before Release 
### Team 17: Jefferson Zhan, Tony Zhang, Emily Wang, Jordan Leahey 

* * * 
### 1 Introduction and Motivation 

#### Preface:
Our team decided to change our dataset from the one in our proposal to a different Kaggle dataset on movie ratings. This was due to the realization that our last dataset was more suited to visualization projects and unsupervised learning.

#### Overview:
Movies are such an important aspect of modern culture. The movie industry brings in billions of dollars annually. Many people will spend their free time watching movies or plan a hangout at the movie theaters, but how many times have you finished watching a movie and realized what a waste of time and money it was, despite being very excited over the premise or actors?

What makes a movie truly successful then? There are movies with budgets in the hundreds of millions with big shot directors and actors but still flop in the box office. Is there a way to use the numbers and data behind each movie to predicts its success beforehand?

#### Goal:
Be able to predict whether a movie will be successful depending on its budget, runtime, and popularity *. This prediction would help both producers and the audience. Correlations will give directors and writers a rough guideline of past successes, and the audience can use this information to determine if a movie is worth their time and money to watch in theaters.

>*Popularity for each movie is determined by the number of votes, views, favorites, and watchlist adds per day compared the the previous days score as well as the release this. TMDB uses this metric to boost their search results as well as show users what is popular at the time of their visit to the website. Even before a movie is released popularity can be used to show growing interest in the movie as it gets closer to the release date and how the movie has been received after it has been released.

* * * 

### 2 Dataset and Methods 
#### TMDB 5000 Movie Dataset from Kaggle
- https://www.kaggle.com/tmdb/tmdb-movie-metadata 

This dataset contains two data sources: tmdb_5000_credits and tmdb_5000_movies. 

*tmdb_5000_credits features:*
- movie_id, title, cast, crew

*tmdb_5000_movies features:* 
- budget, genres, homepage, id, keywords, original_language, original_title, overview, popularity, production_companies, production_countries, release_date, revenue, runtime, spoken_languages, status, tagline, title, vote_average, vote_count 
