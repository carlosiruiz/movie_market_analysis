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


## Data Cleaning and Visualization

After organizing all of the pulled data into a single pandas dataframe, we began the process of data cleaning which included:

1. Removing unneccessary columns
2. Ensuring that all numeric values were stored as either "Int64" or "Float64"
3. Removing rows where Budget or Revenue equal 0
4. Removing rows where IMDB_ID is null
5. Removing rows where Production_Company and Production_Country = "[]" (empty)


## Conclusion

#### Results + Recommendations

##### Who are your top competitors by total movie output?

![Image](company_count.png?raw=true)

##### Who are your top competitors by mean movie revenue?

![Image](company_mean.png?raw=true)

##### What are the trends for movie popularity over time by genre?

![Image](genre_by_year.png?raw=true)

##### What are the most profitable genres?

![Image](histogram_no_outliers.png?raw=true)

##### Which months do top production companies typically release new films?

![Image](genre_by_month.png?raw=true)

##### For the three most profitable genres, what is the distribution of total runtime?

![Image](histogram.png?raw=true)



#### Further Analysis

In order to provide greater insights into Microsoft's entrance strategy, we would like to explore the following:

1. Optimize online marketing strategy by investigating language used 



























