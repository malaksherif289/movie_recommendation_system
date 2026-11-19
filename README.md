# Movie Recommendation System

A user-based collaborative filtering recommender built on the MovieLens 100K dataset.

## Dataset
[MovieLens 100K Dataset](https://grouplens.org/datasets/movielens/100k/) (Kaggle): 100,000 ratings from 943 users on 1,682 movies.

## Approach
1. Loaded the ratings and movie titles
2. Split the ratings into 80% training and 20% testing
3. Built a user-item matrix from the training ratings
4. Computed user-to-user similarity with cosine similarity
5. For a given user, found the 30 most similar users and averaged their ratings (weighted by similarity) to score unseen movies
6. Recommended the top 10 movies the user has not seen yet
7. Evaluated with Precision@10 on held-out ratings of 4 stars or higher

## Example
Top recommendations for user 1 include Titanic (1997), Secrets & Lies (1996), Waiting for Guffman (1996) and The Shawshank Redemption (1994).

## Results
Precision@10: **0.083**

## Key Findings
- Recommendations come from users with similar taste, so no movie metadata is needed.
- Precision@10 is low in absolute terms, which is common for recommenders on sparse data: each user rated only a small fraction of the 1,682 movies.
- Possible improvements: item-based collaborative filtering and matrix factorization (SVD).

## Tech Stack
Python, Pandas, NumPy, Scikit-learn

## How to Run
1. Clone the repo
2. Install dependencies: `pip install pandas numpy scikit-learn`
3. Open `movie_recommendation_system.ipynb` in Jupyter or Google Colab and run all cells
