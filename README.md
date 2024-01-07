# Natural Language Processing - YELP Project
by Chris Adu

# Background
YELP is one of the leading sources of user generated reviews for businesses globally. The ratings are given between one and five stars and users also have the opportunity to write text review.Other users are rate the reviews  'cool' , 'useful' and 'funny'.
I am attempting to categories reviews from the website into one star or five star ratings based on the text reviews using natural language processing techniques. 

# Exploratory Data Analysis
I plotted a Facetgrid to visualise the star ratings and text length. It shows the distributions of text length is the same across all the star ratings , however there is a higher amount of text reviews skewed towards four and five star ratings.
<img width="1121" alt="Screenshot 2024-01-07 at 10 58 09" src="https://github.com/ceebeeaka89/NLP_YELP/assets/54710939/534c18ee-bc78-4a89-8017-e4a11de53c68">

I decided to plot a Boxplot of text length for each star category, from the results it showed that one and two star reviews has higher text lengths. However there are alot of outliners across categories , which could be down to a variety of factors such as the quality data or a high degree of variability we should take into consideration.

<img width="516" alt="Screenshot 2024-01-07 at 11 42 15" src="https://github.com/ceebeeaka89/NLP_YELP/assets/54710939/f5505d9e-f147-4ede-96d2-578357605cea">

To understand the number of occurrencts of each type of star I created a countplot. The results show that there are a higher amount of four and five star ratings gvien, which aligns with the histogram plotted above.
<img width="524" alt="Screenshot 2024-01-07 at 11 47 25" src="https://github.com/ceebeeaka89/NLP_YELP/assets/54710939/bc2053f4-0ddc-49a2-b828-ed97af03758c">

It would be interesting to see if there is a correlation between the reviews of the reviews and text length. The results show that 'Funny' is correlated with 'Useful', text length is psotively correlated with 'Useful'. Negative correlations between 'cool', 'text length', 'funny' and 'useful'. 

<img width="497" alt="Screenshot 2024-01-07 at 12 03 36" src="https://github.com/ceebeeaka89/NLP_YELP/assets/54710939/07c8a7e1-ec41-4975-9fbc-31219dc4555b">

# Natural Language Processing Classfication
I decided to focus on the one and five star review, when I reviw the new dataframe I have approximately half the entries.

<img width="684" alt="Screenshot 2024-01-07 at 12 28 44" src="https://github.com/ceebeeaka89/NLP_YELP/assets/54710939/6fc043eb-398e-4d27-92b6-a1afa4e0b18f">

With this data I transformed the text to vectors using vectorisation (CountVectorizer).

Train the model with Multinomial Naive Bayes Classifier

I used train test split methodology to split the data in test and train data. Then I trained the model using Multinomial as we are dealing with features represented in word counts and we are focused on classification.

# Predictions and Evaluations
To understand how well the model works , I need to predict ratings based of the text reviews to identify how closely they align to the actual ratings. I will be using confusion matrix and classification report.
The results show 93% accuracy on precision and recall for the one star and five star class. The model seems to perform well for Five star rating , where it has a high precision, recall and F1 score. One star ratings perform slightly lower, especially in terms of recall.

<img width="545" alt="Screenshot 2024-01-07 at 12 54 59" src="https://github.com/ceebeeaka89/NLP_YELP/assets/54710939/a1d22360-a9ed-41e8-a90e-3d54388adfbe">.

# Using Text Processsing (TF-IDF)
I wanted to understand if I would be able to improve the results of the model if I add TF-IDF methodology.

**Predictions and Evaluations**

I used confusion matrix and classification reports for my evaluations again. The results showed that TF-IDF made the results worse.

<img width="496" alt="Screenshot 2024-01-07 at 21 26 34" src="https://github.com/ceebeeaka89/NLP_YELP/assets/54710939/09886a64-df00-454d-8dc0-229fed6405c2">


**Drawbacks of the data**

Overall looking at the whole model the data is heavily skewed to four and five star ratings, this was likely to have a negative impact on the model as there is not a balance proportion of labels.

<img width="326" alt="Screenshot 2024-01-07 at 21 30 41" src="https://github.com/ceebeeaka89/NLP_YELP/assets/54710939/e1255171-7b63-4792-b1d2-4c8b9e49af86">







