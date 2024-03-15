# Data Mining Principles - Project Design
## Team: Toby Chiu, Jacky Lin, Joon Park, Christina Song
### Case Description:
Yelp is the premier place to find user reviews and recommendations on restaurants and business. The data that we plan to analyze is from the Yelp Dataset Challenge webpage, which contains a total of 77,000 businesses, 2.2 million reviews, 552,000 user information, and 566,000 business attributes coming from 5 different datasets: business, review, user, checkin, and tip. The ‘business’ dataset contains attributes relating to a business: location (provided by longitude and latitude), type of business, name of business, and business category. The dataset also contains the ratings and the stars left by the customers. The ‘review’ dataset contains information about the reviews that a user leaves for a business and other metrics such as the number of likes the comments received from other users. The user dataset consists of information about the Yelp user such as the number of reviews left by the said user. The full length of features and tables are included at the end of this project design.

#### Audience:
We intend to provide our analysis to restaurant owners who plan on expanding their stores in the near future. Through our analysis, we hope that we will be able to improve the store ratings, number of reviews and impressions, and revenue.

#### Problem:
By utilizing these datasets, we plan to accomplish several tasks:
- Predict the success of a business in its industry based on the first 5-10 reviews.
- Predict the success of store expansions based on reviews, should they expand to different locations.

#### Approach/Methodology:

**Cleaning Data**
We aim to achieve two initial objectives: transforming our data into useful features, and understanding our data and generating hypotheses for future testing.
1. Data Wrangling
- Impute missing data (use tools like autoimpute)
- Standardization/Normalization
2. Exploratory Data Analysis (EDA)
- We can create basic profiles and use visualizations to help describe feature characteristics. Clustering groups, particularly with textual data, can help in understanding trends within our features.
3. Feature Selection/Engineering
4. Language Embedding
- A large proportion of our data is text-based in nature. We plan to turn text-based reviews into features through language embedding techniques, such as creating a bag-of-words through a tf-idf/count vectorizer or word2vec. We can then find descriptive trends through clustering methods or soft cosine similarity.
5. Feature selection
- Given the large amount of features, particularly from language embedding, we would ideally use dimensionality reduction to shrink our feature set, such as through PCA, T-SNE.
- Existing categorical variables (e.g. cities) should be shifted to numerical values.
- We should also use manual judgment to retain only features that can help solve our hypotheses, and create new features that can help increase capacity of our predictors, and help us augment our analysis.
- We can also use correlation analysis to remove/reduce multicollinearity between features, such as through a correlation matrix or VIF.

**Rating Prediction**

Yelp currently contains a 5-star rating feature that can be used to judge restaurant quality. Our first step in predictive analytics is to build a model that can predict how well any hypothetical restaurant should perform, given a certain set of Yelp data. We can use this model to abstract restaurant ratings, and allow us to predict ratings for hypothetical restaurants. 

We can test a variety of regression models that range in accuracy and interpretability, such as GLMs, Regression Decision Trees, and SVMs. We aim to prioritize interpretability as understanding the factors that affect ratings is one of our main goals. 

We don’t expect class imbalances in our dataset, and we plan to test our data through cross-validation with metrics such as RMSE/MAE.

**Predicting Expansion Success**

We can expand the use case for our previous model through predicting how well existing restaurants expanding to new markets will perform. To do this, we can grab basic demographic data (e.g. from the US Government’s SMART Location Database) and incorporate it as features for each city. We can use census predictors to grasp how different demographics affect the restaurant market for each sector.

Dataset:
https://www.yelp.com/dataset/download
Dataset documentation: https://www.yelp.com/dataset/documentation/main
