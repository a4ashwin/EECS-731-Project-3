# Assignment-Project-3-Weekend Movie Trip
 3rd assignment of EECS 731 Intro to Data Science - Weekend Movie Trip

 Prerequisites
Python 3.7.3, Jupyter Notebook, Pandas Library, Numpy Library & sklearn Library

 Introduction:
 In this project, we are going to transform the dataset of Weekend Movie Trip by using feature engineering. We are going to transform the dataset into a new dataset that has the meaningful data to cluster the dataset using KMeans model. The process includes dropping of features, changing the datatypes, concatenating features, training the models, testing the models, printing the overall accuracy and precision etc. We are going to use movies.csv, tags.csv and ratings.csv files to cluster the data which can give movie suggestion to user based on the previous watches of user.

 Idea:
 To cluster the data, we will be getting the average rating for a movie in the movies dataframe and then we will combine the tags for a movies in tags dataframe. Then, we will combine the movie, tags and ratings dataframe in the single dataframe on the basis of movieId. Then we will use KMeans clustering model on the basis of rating and genre to generate clusters of the dataframe. When a user watches a movie from a cluster then we can recommend movies from the same cluster which have nearly similar rating and genre as the movie user watched.


 Process:
 - Download the data from https://grouplens.org/datasets/
 - Load the dataset into Pandas dataframe from movies.csv, tags.csv and ratings.csv
 - Change the tag column's datatype into string as we will be combining all the tags for a movie in to single tag separated with ', ' so we can use it for clustering if we need.
 - Drop the userId and timestamp columns from tags dataframe because these columns are not significant in suggesting the movies to a user based on watched movies.
 - Grouping the tags for a movie from multiple users in a same row.
 - Drop the userId and tags from ratings_data as they are not significant to achieve our goal.
 - get the average rating for a movie by grouping movieId and calculating mean of ratings from various ratings given by different users to the same movie so we can use it later for clustering.
 - Merge movies_data, tags_data and ratings_data int0 a single dataframe on the basis of movieId which is common feature in all three tables to perform clustering.
 - Drop the title and tag as title is not necessary because we have movieId and using tag will make our clustering complicated because we will need to do sentimental analysis of the tags.Also, tags can have unlimited  possible words as they are provided by users.
 -  Encode the 'genres' feature as our model will only take numerical values and genres will have strings. We will be using LabelEncoder for the same.
 - Initialize the KMeans clustering model with k = 20 as there are 20 genres present and also it will give us a average rating interval of 0.25. (Tried different values of k but 20 gives the best plotting results per our analysis)
 - Fit the cluster on the basis of genre and rating.
 - Take the centers of the clusters and plot the data on the graph.


 Result:
 We have successfully used the exploratory data analysis technique to get the idea of the data and remove insignificant data from the original dataset. We have used feature engineering to transform and merge the data from different datasets and make a final meaningful dataset for our particular goal. We successfully used the KMeans clustering model to cluster the data and plotting the centers with clusters. These clusters can be used to suggest movies to the user if the user watches a movie from the cluster as one cluster will have movies with similar rating and same genres.


 Built With:
 Jupyter Notebook
 Python 3.7.3
 Pandas
 NumPy

 Authors:
 Ashwin Rathore

 License:
 This project is created for Course EECS 731 Assignment for University of Kansas.

 Acknowledgments
 https://grouplens.org/datasets/movielens/
