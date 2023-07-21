# Project 3 - Movies
 
 * Erica Kitano
 
## Business Problem:

To produce a MySQL database on Movies from a subset of IMDB's publicly available dataset, to analyze what makes a movie successful and provide recommendations to the stakeholder on how to make a successful movie.

## Data:

The original source of the data used are the following files from [IMDb](https://developer.imdb.com/non-commercial-datasets/).

- title.basics.tsv.gz
- title.ratings.tsv.gz
- title.akas.tsv.gz


## Additional Data:

Used an API to extract box office revenue and budget data from TMDB to add to the IMDB data and perform exploratory data analysis.

![Logo](https://www.themoviedb.org/assets/2/v4/logos/v2/blue_square_2-d537fb228cf3ded904ef09b136fe3fec72548ebc1fea3fbbd1ad9e36364db38b.svg)

### EDA:

 * Average revenue per certification category: 

|certification | mean revenue | 
| - | - |
| G | 1.173648e+08 |
| PG | 1.106791e+08 |
| PG-13 |  9.928786e+07 |
| R | 3.266001e+07 |
| NR | 9.588674e+06 |

 * Average budget per certification category
 
 | certification | mean budget |
 | - | - |
 | PG     |  4.482849e+07 |
 | PG-13  |  4.299357e+07 |
 | G      |  3.813333e+07 |
 | R      |  1.945174e+07 |
 | NR     |  6.302358e+06 |
 
## MySQL Database and Tables
 
|Tables_in_movies|
| - |
| 0  genres|
| 1  title_basics| 
| 2  title_genres|
| 3  title_ratings|
| 4  tmdb_data|

## Hypothesis Testing

### Q1. Does the MPAA rating of a movie (G/PG/PG-13/R) affect how much revenue the movie generates?

![PNG](/Images/Q1_plot.png)


**Conclusion: Yes, we support that there is a significant difference in the average revenue between the 4 groups.**

### Q2. Do movies that are over 2.5 hours long earn more revenue than movies that are less than 2.5 hours long?

![PNG](/Images/Q2_plot.png)

**Conclusion: Yes, movies that are over 2.5 hours long earn more revenue than movies that are less than 2.5 hours long.**

### Q3. Do movies released in 2020 earn less revenue than movies released in 2019 ?

![PNG](/Images/Q3_plot.png)

**Conclusion: Yes, movies released in 2020 earned less revenue compared to movies released in 2019.**

## Linear Regression Model

### Coefficient of Final Model

![PNG](/Images/Coefficient.png)

## Final Recommendation

The features (columns) that show highest coefficient (highest correlation with the target ('revenue')) are:

- year
- popularity
- runtime
- vote_count