# Movielens Dataset Recommender System

## Using Spark 2.0+

Recommender systems, or sometimes referred to as recommender engines, are a modeling algorithm that tries to predict the “rating” that a user would give to an item. In this case the items are movies from the Movielens dataset. This dataset is a list of movies, users and ratings with links to imdb and tmdb (theMovieDB) web id's so we can scrape or fetch information from API's regarding recommendations.

The main idea is to build a matrix of users X items with rating values filled in for existing data. This feature set in then decomposed into U, V matrices which correspond with a set of latent factors which can be used to describe user preferences.

ALS

Apache Spark ML implements alternating least squares (ALS) for collaborative filtering, a very popular algorithm for making recommendations.

ALS recommender is a matrix factorization algorithm that uses Alternating Least Squares with Weighted-Lamda-Regularization (ALS-WR). It makes the regularization parameter less dependent on the scale of the dataset. This way the best parameter learned from the sampled subset can be aplied to the full dataset and we will get similar performance. The latent factors should explain the observed user to item ratings and map new users to optimal movie recommendations.

## Jupyter Notebook

 [spark_recommender.ipynb](spark_recommender.ipynb)

## Considerations

The ALS model used assumes, by default, that the ratings are explicit. If the ratings matrix is described by other information or inferred from other signals then the parameter implicitPrefs can be set to True and yield better results.
