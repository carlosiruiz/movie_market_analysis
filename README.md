# movie_market_analysis

#### Data Scientists:
- Ignacio Ruiz
- Alec McCabe

#### Sources:
- TMDB API (The Movie Database)


## Introduction

The goal of this project is to assist Microsoft Corp with its entrance into the international movie industry. With this goal in mind, our team set out to collect data related to the most popular movies released between the years 2000 and 2019. Utilizing The Movie Database's API we were able to retrieve information for over 9,000 movies, including relevant features such as release_date, genre, budget, revenue, and more. Following subsequent data cleaning, we utilized this dataset to answer the following questions:

```
1. Who are the top production companies
    * by movie count
    * by mean movie revenue
2. What are the trends of genre popularity over time?
3. Which genres have the greatest revenue potential?
4. What months do top production companies typically release movies?
5. What is the distribution of runtime for our desired genres?
```

In answering the above questions, we utilized the following libraries:

```
### Data Collection
pandas
requests
json

### Data Visualization
pandas
matplotplib.pyplot
seaborn
```


## Data Collection

We utilized the The Movie Database (TMDB) API for the construction of our master dataset. Our objective was to collect - at minimim - the following data:
- Movie Title
- Movie Genre
- Movie Runtime
- Movie Production Company
- Movie Budget
- Movie Revenue
- Movie Release Date

TMDB is a crowdsourced database for movies, and as such we knew that we would need to pull data strategically in order to maximize data accuracy for "budget" and "revenue" features. As such, we performed a GET request using the TMDB API "Discover" attribute to retrieve the top 9,000 movies based on TMDB "Popularity". Popularity in this sence indicates the overall frequency in which users of the TMDB website interact with and update the movie entry within the database. As this API call returns results in pages (with 20 movie details returned per page), we needed to run the request through a for loop with range(0,500).

Following this, we had a list of 9,000 movies... but we were missing some key features.

Using a for loop combined with a list of the Movie IDs returned from the first API request, we retrieved our desired missing data by performing a GET request with the TMDB API "Movie" attribute. Calling the "Movie" attribute returns all of our desired data for a single movie. We collected this information and stored each variable into a respective list. We then added each new list as a new column in our original dataframe.


## Conclusion + Recommendations

#### Results + Recommendations

##### Who are your top competitors by total movie output?

![Image](images/company_count.png?raw=true)

##### Who are your top competitors by mean movie revenue?

![Image](images/company_mean.png?raw=true)

##### What are the trends for movie popularity over time by genre?

![Image](images/genre_year.png?raw=true)

##### What are the most profitable genres?

![Image](images/boxplot_no_outliers.png?raw=true)

##### Which months do top production companies typically release new films?

![Image](images/genre_month_clean.png?raw=true)

##### For the three most profitable genres, what is the distribution of total runtime?

![Image](images/histogram.png?raw=true)


Recommendations:

Competition:
- Investigate the operations of production companies such as Universal Pictures and Warner Brothers to optimize your movie production output 
- Focus on developing large franchises like those owned by Marvel and Lucasfilms in order to maximize total revenue at the box office

Genres:
- Avoid genres like Drama, Comedy, and Thriller as these are highly saturated
- Focus on developing Fantasy, Adventure, and Animation movies as these return the highest profit

Release Month:
- Avoid releasing films in “Dump Months” such as September, as you will have increased competition.

Runtime:
- Based on our analysis, the typical Fantasy, Animation, and Adventure genres are typically 90-100 minutes in duration.



























