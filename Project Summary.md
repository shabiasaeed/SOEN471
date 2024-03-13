# SOEN 471-Project Summary

## Introduction
This project aims to develop a tool that enhances user experience by offering tailored and personalized beauty product recommendations. It uses the Sephora dataset and applies various recommender systems class models and algorithms. 

## Dataset Description

The “[Sephora Products and Skincare Reviews](https://www.kaggle.com/datasets/nadyinky/sephora-products-and-skincare-reviews)” dataset, sourced from Kaggle, is composed of over 8,000 product and review data content about beauty products. The product data content consists of 27 different product-specific features such as id, name, brand, number of reviews, number of loves, ingredients, and more. The review data content consists of 15 features and is divided into 2 parts; 

- review content features:  author id, review text, rating, would the user recommend it..

- user information features: skin color, skin type, eye color, hair color…

## Research Questions
The questions we would like to address using this data set are the following:

&nbsp; **1.** How can we utilize user's physical characteristics and preferences to recommend customers the most suitable products?

&nbsp; **2.** Among the different models, which one will yield the most promising results?

## Model Design

### Class of Models:

The aim is to use recommender system models to suggest beauty products to various user profiles based on the Sephora dataset. The two models we have decided upon are:

- Content-based Filtering Model: This model recommends an item based on the attributes of items a user has shown interest in before. Attributes can include product type, ingredients, brand, and skin benefits for beauty products.

- Collaborative-based Filtering Model: This model recommends items based on the interactions between users and items and identifies similarities between different users or items. This technique allows for analyzing data from users with similar beauty product preferences and recommending products with the highest correlation.

### Algorithms:

The two approaches we will take to build our recommender system are going to be content-based filtering and collaborative-based filtering. Collaborative-based filtering is available with PySpark and implemented using the Alternating-Least Square (ALS) algorithm. Given two matrices P and U representing products and users respectively, the ALS algorithm finds the optimal U’ and P’ matrices that can represent our dataset by first fixing U to find P’, then fixing P to find U’ [1].  Now, Content-Based filtering is not available out of the box with PySpark but can be implemented by leveraging TF-IDF [2]. We will vectorize the information for each product, mainly highlights, primary, secondary, and tertiary categories, and ingredients, to build an item profile. After which, we will build user profiles and thus be able to recommend items to users. 

As our dataset is imbalanced, with few products having many reviews and others very few, we will evaluate and compare the model’s performance by using the F1 measure.

## Conclusion
In conclusion, this project aims to build a model that matches users with Sephora products that align with their preferences and physical characteristics, utilizing content-based and collaborative filtering models.
 
## References
[1] Watson, Sophie“A gentle introduction to alternating least squares,” Sophie Learns Things., https://sophwats.github.io/2018-04-05-gentle-als.html#:~:text=The%20goal%20of%20Alternating%20Least,with%20row%20j%20of%20P. (accessed Mar. 12, 2024). 

[2] Sophie, “A gentle introduction to alternating least squares,” Sophie Learns Things., https://sophwats.github.io/2018-04-05-gentle-als.html#:~:text=The%20goal%20of%20Alternating%20Least,with%20row%20j%20of%20P. (accessed Mar. 13, 2024). 

