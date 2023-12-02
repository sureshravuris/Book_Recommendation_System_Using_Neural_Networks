# Book Recommendation System Using Neural Networks

Recommendation Systems are sophisticated algorithms designed to suggest items to users based on their interests. These systems play a crucial role in online shopping platforms to boost sales by personalizing user experiences.

There are primarily two categories of recommender systems:

#### Collaborative Filtering System:   
This type of system generates recommendations from users’ past behavior, preferences, and choices. It creates a user profile model and identifies items to recommend based on similarities between user profiles and their shared interactions with items.

#### Content-Based Filtering System:  
In contrast to collaborative filtering, content-based systems focus on the characteristics of the items themselves. They recommend items by analyzing the similarity of their attributes, suggesting items that share common features.

## Objective
Develop a neural network-based book recommendation system to deliver personalized book suggestions that resonate with individual user preferences and reading habits. Implement collaborative filtering approach by creating and learning from user and book embeddings, aiming to understand and utilize the intricate patterns of user-book interactions to enhance the quality of recommendations. Focus on minimizing the mean squared error during training to improve the accuracy of predictions, with the system's success measured by its performance on unseen data, user engagement, and satisfaction metrics.


## Overview of the Dataset
While there have been notable datasets for movie (such as Netflix and Movielens) and music (like the Million Songs dataset) recommendations, book recommendations have lagged behind until the introduction of this dataset. The dataset comprises ratings for ten thousand well-known books. These ratings were sourced from the internet. On average, each book has 100 reviews, though some have less. The ratings range from one to five.

The dataset features sequential IDs for both books and users. Book IDs run from 1 to 10,000, and user IDs from 1 to 53,424. Every user has contributed at least two ratings, with a median of 8 ratings per user. Additional data includes a list of books marked as 'to be read' by users, along with book metadata such as the author and publication year, as well as various tags associated with the books.

This dataset is available on Kaggle: [Click Here to view the Dataset](https://www.kaggle.com/datasets/zygmunt/goodbooks-10k)
## Project Architecture
### Exploratory Data Analysis (EDA):

The EDA phase involves graphical representations to identify trends and patterns, focusing on the most rated books, top authors, and distribution of user ratings.
This step is crucial for gaining insights into the dataset and guiding the preprocessing and model building stages.   
a) Loading the csv files

b) Checking the description of the daatsets like the data types, how many rows , columns, etc

c) Explored the following factors:

Top 20 highest rated books
![image](https://github.com/ruchithareddy269/256-Project-Book_Recommendation_System/assets/64256985/e95b09ed-86d6-441c-983b-a3455d01587b)


Top 20 most popular books
![image](https://github.com/ruchithareddy269/256-Project-Book_Recommendation_System/assets/64256985/e6274d9a-192c-4b4e-942f-c779faa591ea)


Most popular authors
![image](https://github.com/ruchithareddy269/256-Project-Book_Recommendation_System/assets/64256985/c6969f75-2e1f-4bf3-864c-57502b1c56e5)


Most number of ratings
![image](https://github.com/ruchithareddy269/256-Project-Book_Recommendation_System/assets/64256985/0f45eb75-664e-4c7e-92b7-54ddbafd6f90)


### Data Preprocessing:

Data cleansing involves removing duplicates, handling erroneous entries, and standardizing formats to ensure data quality.
Treatment of NaN values and extraction of relevant features set the stage for a robust dataset, ready for model consumption.

a) Selected essential columns for the recommendation process, which include 'id', 'book_id', 'isbn', 'authors', 'original_publication_year', 'title', 'average_rating', 'ratings_count', and 'small_image_url'.   
b) Addressed missing values by replacing them with 'NA' to preserve the integrity of the book records instead of deleting them.   
c) Preserved the processed dataset in its final form, ready to be used in the recommendation engine.
### Model Building:

The data is divided into training and testing sets to both develop the model and evaluate its performance on unseen data.
A neural network is constructed using TensorFlow's functional API, allowing for a flexible and complex architecture tailored to our recommendation system's needs.

### Neural Network Architecture:
![image](https://github.com/ruchithareddy269/256-Project-Book_Recommendation_System/assets/64256985/1ec6a0d7-d3d2-45dd-946d-7f5fb0c3efea)

The neural network model forms the backbone of the recommendation system and includes the following components:

#### User and Book Input Layers: 
Handle the input of user and book IDs.

#### Embedding Layers: 
Transform the user and book IDs into meaningful, dense vectors, capturing latent features and preferences.

#### Concatenate Layer:
Merges the user and book embeddings to create a unified feature set.

#### Dense Layers:
A series of fully connected layers with ReLU activation functions that learn the complex relationships between the combined features.

#### Output Layer:
A single neuron with a linear activation function that predicts the user's rating for a book.

### Result/Recommendation:

The trained model is loaded and utilized to predict user preferences, forming the basis of the book recommendation function.
This function takes user input and leverages the model to generate a personalized list of book recommendations.

a) Loaded the model and the books and ratings dataset. The recommendations are gonna be made from the books dataset.

b) Defined a function that is expecting a parameter input 'user_id' which is basically a unique id for each user. The function will return a dataset containg the top 5 recommended books for that particlular user.


## Conclusion:
The recommendation system function recommend(user_id) has been successfully implemented and tested. It effectively provides personalized book recommendations by leveraging a trained neural network model. When provided with a user ID, the system processes the entire catalog of books and predicts the top 5 books that the user is likely to enjoy, based on learned user preferences and book attributes. The system outputs a neatly formatted list of recommended books, including their IDs, authors, titles, and average ratings, demonstrating its potential to enhance user experience in a real-world book recommendation scenario. This represents a significant step towards creating an intelligent, data-driven approach to book discovery, tailored to individual user tastes.





