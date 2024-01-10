# Predicting Fraud Users on Depop 

## Background and Motivation

As e-commerce grows as an industry, an ever present concern for platforms, buyers, and sellers, is the prevalence of fraud, or "scam," users. In our project, we define scam users as users that post fake listings, either of products that they never owned or never intended to sell. Scam users are a huge problem for all key stakeholders. For platforms such as Depop or Etsy, they drive away business, decrease revenue, and undermine the integrity of the platform. For buyers, they increase the potential of getting scammed and losing money and time. For sellers, scam listings can crowd out real listings and make it harder for real sellers to sell their products. 

Our goal is to build a model to detect fraud users so that they can be reviewed and removed by platforms as soon as possible. Our main research question is: What features and models can be used to accurately classify Depop listings as real or fraudulent?

## Data Overview

To obtain our data, we scraped data from 234 sellers and 171910 listings. We manually labelled and reviewed the data as real, new, or scam users using predetermined criteria. Our criteria for fake users included zero seller reviews, few or no sold products, different backgrounds, suspicious pricing, or unoriginal photos. Our criteria for real users included many seller reviews, many sold products, cohesive backgrounds, social media/different account, or photos are their own. Our criteria for new users included few buyer or seller reviews, few or no sold products, cohesive backgrounds, social media/different account, or photos are their own.

The decision to include a "new user" category arose during the initial labelling process. We decided to include this as a category because new users can often seem like scam users as they share a lot of the same characteristics, such as no reviews or few postings. 

After labelling the data, we did some feature engineering including dropping missing data, converting data types, and one-hot-encoding categorical features. We also added a bag of words feature of listing descriptions.

## Tree Based Models

We first performed a 70-30 test train split. We used three different types of tree based models: a Decision Tree, a Random Forest, and a Gradient Boosting/XG Boost.

All three models performed very well.
<img width="803" alt="Screen Shot 2024-01-10 at 12 07 54 PM" src="https://github.com/serenabai/NYC-Ubers/assets/78036684/9f7e8192-9b6c-4b0e-82e3-6cf912c0977c">

The two most important features were reviews_rating, and reviews_total for all three models.
<img width="704" alt="Screen Shot 2024-01-10 at 12 06 55 PM" src="https://github.com/serenabai/NYC-Ubers/assets/78036684/fec794f9-8de3-4e87-bacf-69cc1efee2e3">

Overall, the most suitable models were Decision Tree and Random Forest. While Gradient Boosting also had a high accuracy score, the model takes much too long to run as it cannot take advantage of parallelization.

## Neural Network

## Conclusion
