FLICKFLARE MOVIE RECOMMENDATION SYSTEM


![FlickFlareLogo](https://github.com/user-attachments/assets/2439fab4-6a8e-4f0d-a7d2-1e9a6602a860)



 Kelvin Mwaura
 
 Abigael Nyabaga
 
Prossy Nansubuga


FlickFlare Movie Recommender System

Overview:

FlickFlare is a cutting-edge movie streaming platform designed to bring a diverse and expansive collection of films directly to your screen. Whether you're a fan of classic cinema, indie gems, or the latest blockbuster hits, FlickFlare has something for everyone.

To enhance user satisfaction and ensure that our movie recommendations align with user interests, we are introducing a sophisticated movie recommender system. This system will leverage user ratings and genre preferences to suggest the top 5 movies tailored to individual tastes

Business Understanding
 Problem Statement

FlickFlare, a movie streaming company, received feedback from users on the Google Play Store indicating that the movies recommended to them did not match their interests, leading to customer dissatisfaction.

To address this issue, FlickFlare has approached us, RODATA-a data analytics company, to build a movie recommender system. This system will aid in suggesting the top 5 movies to users based on their ratings and preferred genres.

 Objectives

 Main Objective

   To build a movie recommender system that suggests top movies to streaming users based on movie ratings

Specific Objectives

1. To Implement and compare SVD, NMF, and KNN collaborative filtering algorithms for movie recommendation, evaluating their performance using RMSE on a benchmark dataset of user-movie ratings

2. To use the model witn the lowest rmse  to generate personalized top-N movie recommendations for streaming users.


   Metric for Success


Goal: To Achieve at least 80% accuracy in recommending the top five movies.

Approach:

Model Implementation: To Utilize SVD, NMF, and KNN algorithms to predict user ratings and rank movies accordingly.

Evaluation: Measure the accuracy of predictions using RMSE. The goal is to achieve an RMSE that corresponds to at least 80% accuracy in the top five recommendations.

Optimization: Continuously tune and validate model parameters to improve accuracy. We will Use techniques like cross-validation to ensure the robustness of the models


### **Data Understanding**

The data used has been sourced from the MovieLens dataset from the GroupLens research lab at the University of Minnesota.

It contains 100,836 ratings and 3,683 tag applications across 9,742 movies. These data were created by 610 users.

The dataset is distributed among four CSV files:

    links.csv
    movies.csv
    ratings.csv
    tags.csv

1. **movies.csv**

Each line of this file after the header row represents one movie and has the following columns:

    movieId: Unique ID for each movie
    title: Name of the movie followed by its year of release
    genres: Categories that a movie might fall into, separated by |



2. **tags.csv**

Each line of this file after the header row represents one tag applied to one movie by one user and has the following columns:

    userId: Unique ID for each user
    movieId: Unique ID for each movie
    tag: User-generated metadata about the movie in the form of short, meaningful phrases
    timestamp: Time when the tag was provided by the user

3. **ratings.csv**

Each line of this file after the header row represents one rating and has the following columns:

    userId: Unique ID for each user
    movieId: Unique ID for each movie
    rating: Rating given by the user for the movie. Ratings are made on a 5-star scale with 0.5 increments
    timestamp: Time when the rating was given
    
EDA 
Exploratory Data Analysis: During the Exploratory Data Analysis (EDA) phase, we delve into the dataset to uncover its fundamental attributes and patterns. This process involves examining summary statistics, visualizing distributions, identifying correlations, and detecting outliers. EDA is a crucial preliminary step, offering insights that inform subsequent data preprocessing and modeling decisions.

This image shows the top 10 movies that received the highest number of 5-star ratings. Key observations:

"The Shawshank Redemption" (1994) leads with the most 5-star ratings.

Classic films from the 1990s dominate the list

This data suggests these movies are highly regarded by viewers and could be strong candidates for recommendations in a movie recommender system.



![EDA_JPEG-removebg-preview](https://github.com/user-attachments/assets/9fc1be82-405a-4d1e-9704-74a8e04a1804)





MODELLING
We used the SVD, KNN nearest neighbors, and the NMF model to build our collaborative filtering recommender system.
This is what we observed from the modeling bit :

![MODELLING_IMAGE-removebg-preview](https://github.com/user-attachments/assets/b38e65c1-a01e-43c8-801c-4c0b8a65139d)




-Baseline model: Had the highest RMSE of about 3.5, indicating poor performance.

-KNN (K-Nearest Neighbors): Shows significant improvement with an RMSE of about 0.95.

-NMF (Non-negative Matrix Factorization): Performs slightly better than KNN with an RMSE of about 0.9.
 
 -SVD (Singular Value Decomposition): The lowest RMSE of about 0.95, very close to NMF.


 Based on these results, we recommend using the SVD (Singular Value Decomposition) model for our recommendation system. Here's why:

 SVD has a lower overall RMSE (0.8828) compared to NMF (0.9231), indicating better average performance across the entire test set.

 While NMF performed better for the single example we looked at, the lower RMSE of SVD suggests it generalizes better across a wide range of user-movie pairs.


 RECOMMENDATIONS AND CONCLUSIONS 

To enhance the effectiveness of our movie recommendation system, we recommend implementing a feedback mechanism where users can rate the relevance of the recommendations they receive. This user feedback should be continuously utilized to refine and adjust the recommendation algorithms. Given its superior performance and accuracy, the SVD model should remain the primary recommendation engine to ensure users receive the most relevant suggestions. Additionally, it is crucial to ensure that the recommendation system is scalable to accommodate an increasing number of users and movie entries, potentially leveraging cloud-based solutions or distributed computing as necessary.

The project has successfully addressed the core challenge of user dissatisfaction with movie recommendations, as previously noted in Google Play Store feedback. By leveraging collaborative filtering through SVD, we've demonstrated the effectiveness of utilizing collective user behavior for personalized suggestions. This approach not only aligns with our initial objectives but also sets a strong foundation for improving user experience and engagement. The system's ability to provide accurate, personalized recommendations positions it well to meet user expectations and potentially increase user satisfaction and retention rates
