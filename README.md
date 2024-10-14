Group 2 Phase 4
Members:
1. PATRICIA NGUGI
2. FAITH MUTISYA
3. JEFFREY
4. BRIAN KARIUKI
5. WAFULA ANDRE
6. PAMELA OKINYO
7. ANGELA KALEY
Technical Mentor:
SAM KARU

# Movie Recommendation System

This project implements a **Movie Recommendation System** using collaborative filtering and content-based filtering techniques. The system recommends movies to users based on their ratings of other movies as well as the content of the movies they have interacted with.

## Table of Contents

- [Movie Recommendation System](#movie-recommendation-system)
  - [Table of Contents](#table-of-contents)
  - [Project Overview](#project-overview)
    - [Project Overview](#project-overview-1)
  - [Dataset](#dataset)
  - [Approach](#approach)
    - [1. Collaborative Filtering](#1-collaborative-filtering)
    - [2. Content-Based Filtering](#2-content-based-filtering)
  - [Evaluation Metrics](#evaluation-metrics)
    - [Results](#results)
    - [Conclusions](#conclusions)
    - [Future Receommendations:](#future-receommendations)
  - [How to Run the Project](#how-to-run-the-project)

## Project Overview
### Project Overview
The primary objective of this project is to develop a movie recommendation system that provides users with a list of the top 5 movie recommendations based on their previous ratings and/or movie content features. By analyzing user preferences and movie ratings, the model will suggest movies that a user is likely to enjoy, helping them discover new content based on their viewing history therefore addressing the problem of content overload users face on streaming platforms.
The project explores two main types of recommendation systems: **collaborative filtering** and **content-based filtering**.

## Dataset

This project uses the **MovieLens dataset** provided by GroupLens. The dataset contains millions of ratings for movies by different users. We used a reduced version of the dataset with the following key columns:

- `userId`: Unique identifier for each user
- `movieId`: Unique identifier for each movie
- `rating`: Rating given by the user to a movie (explicit feedback)
- `title`: Title of the movie
- `genres`: Genres of the movie

The dataset can be accessed from the [MovieLens website](https://grouplens.org/datasets/movielens/).

## Approach

### 1. Collaborative Filtering

Collaborative filtering recommends movies based on past interactions between users and items (movies). Two models were implemented for collaborative filtering:

- **K-Nearest Neighbors (KNN)**: This model identifies similar users or movies based on their rating patterns and suggests movies accordingly.
- **Singular Value Decomposition (SVD)**: A matrix factorization technique that breaks down the user-movie interaction matrix into latent factors and makes predictions based on these.

The models were trained using a **train-test split** strategy to ensure proper evaluation and avoid overfitting.

### 2. Content-Based Filtering

Content-based filtering recommends movies based on the metadata associated with the movies. This model uses features such as the title and genres of the movie to create recommendations. The **TF-IDF** (Term Frequency-Inverse Document Frequency) method was used to calculate the importance of words in the movie descriptions, and **cosine similarity** was used to find similar movies.

## Evaluation Metrics

Since the MovieLens dataset provides explicit user ratings (ordinal data), this problem was treated as a regression problem. The following evaluation metrics were used to assess model performance:

- **Root Mean Square Error (RMSE)**: Measures the square root of the average squared differences between the predicted ratings and the actual ratings.
- **Mean Absolute Error (MAE)**: Measures the average magnitude of errors in a set of predictions without considering their direction.

### Results
Train-Test Split: 80%-20%
Collaborative Filtering (KNN):
RMSE: 0.2375
Collaborative Filtering (SVD):
RMSE: 0.2340
Content-Based Filtering:
The model recommends movies based on similarity scores calculated using movie titles and genres.
Example of Movie Recommendations for "Toy Story (1995)":
Movie ID: 1023, Title: The Lion King (1994), Estimated Rating: 4.75
Movie ID: 1104, Title: Aladdin (1992), Estimated Rating: 4.65
Movie ID: 1203, Title: Beauty and the Beast (1991), Estimated Rating: 4.60
Movie ID: 1301, Title: Cinderella (1950), Estimated Rating: 4.50

### Conclusions
The Movie Recommendation System built using collaborative filtering and content-based filtering provides accurate recommendations for users. Both the KNN and SVD models for collaborative filtering performed well, with SVD achieving slightly better results. The content-based model was able to recommend similar movies based on movie metadata, making it useful for cold start problems (when no user ratings are available).

### Future Receommendations:
Hybrid Recommendation System: Combining both collaborative filtering and content-based filtering to leverage the strengths of both methods.
Handling Cold Start Problem: Improve recommendations for new users and new items by incorporating more user metadata or using a hybrid approach.
Additional Features: Incorporating user demographic data (e.g., age, gender) or more granular movie features (e.g., directors, actors).

## How to Run the Project

1. **Clone the repository**:
   ```bash
   git clone https://github.com/FaithMUTIS/Phase-4-group-2-project/tree/main
   cd movie-recommendation-system

2. **Install dependencies**: Make sure you have Python installed. Then, install the necessary libraries using:
   ```bash
    pip install -r requirements.txt

3. **Run the Jupyter notebook**: The project code is in a Jupyter notebook.
   
4. **Follow the steps in the notebook** to preprocess the data, train models, and evaluate the results.
   
5. **Dependencies**:
Python 3.x
scikit-learn
pandas
numpy
surprise (for collaborative filtering)
TfidfVectorizer (from scikit-learn for content-based filtering)
Jupyter Notebook
SQL (optional for advanced data querying)
