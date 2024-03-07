# Yelp-Star-Rating-Prediction
Optimizing Business Success on Yelp: Analyzing Factors for Star Ratings

**Problem Statement**  

Yelp's challenge is to refine business onboarding to better reflect the impact of customer interactions and preferences on star ratings.


**Purpose and Objectives**
1. Predict star ratings and understand driving factors
2. Equip businesses with actionable strategy to elevate their ratings
3. Boost user engagement through data models for Yelp


**Solution Value**

Analyze the Yelp dataset to predict star ratings, provide businesses with strategic insights to enhance user experience and foster a robust Yelp community.


**Definition & Scope of Features**

Overview
- 73 Features Considered
- 5 Dataset for Analysis

Main Categories for Features:

1. Business:
   
- Service options (Takeout, caters)
- Dining experience (ambience, outdoor seating)
- Presence of amenities (e.g., TV, Wi-Fi, parking)

2. Review:
- Sentiment scores
- Frequency of positive/negative words
- Length of review


3. User Engagement:
- Number of reviews received
- Average stars given by user
- Number of friends
- Elite status duration


4. Temporal Data:
- Check-in times
- Frequency of reviews over time
- Temporal patterns in user activity
- Tips information

**Data Exploration**

Datasets Overview

- 5 Data Sets: Business, User, Review, Check-in, Tips
- 150,346 businesses - Location, ratings, attributes
- 1,987,897 users
- 6,990,280 reviews - Reviews with rating and text
- 908,915 tips - User tips with text and compliment
- 131,930 check-ins - User check-ins at business


Data Description

Primary Unit

- Businesses: Evaluated through ratings, categories, and attributes.
- Users: Analyzed via reviews, tips, and engagement metrics.
  
Secondary Unit

- Reviews: Insights on customer satisfaction and feedback.
  
Limitation & Delimitation

- Subjectivity: Check-in and tips, being subjective, might introduce bias in understanding business quality so we didn’t incorporate in feature engineering.
- Focus Area: Analysis centers on user interactions, review and business-related metrics.

**Modeling Framework**

Feature Engineering

- Text Features: Identify significant words or phrases (TF-IDF).
- Truncated SVD: Avoid sparse matrix issue since user compliment/feedback/fans have a lot zeros.
- One-Hot Encoding: Each category value is converted into a new column and assigned a 1 or 0 (notation for true/false) value to the column.

Validation

- Cross Validation: Employ cross-validation techniques to ensure model reliability across different subsets of data.


**Methodology**

Model Descriptions

- Baseline: Linear Regression
- Non-Linear:
  - SVM (linear & non-linear)
  - Decision Tree
  - Random Forest
  - AdaBoost
  - XGBoost

- Customized Ensemble Model: Stacking the base models above using Bayesian Ridge Regression

- Result: Bayesian Ridge Regression model, combining based model of Decision Tree and XGBoost

- Training RMSE: 0.022; Test RMSE: 0.035


**Model Selection and Validation**

Model Performance Evaluation:

- CV error > training set error: overfitting
- CV error ≈ training set error >> test set error: underfitting

Randomized Search Cross-validation (5-fold) was employed to assess model generalizability, with RMSE (Root Mean Squared Error) as the performance metric to compare different models' predictive accuracy.

