# Capstone Project - Olist Customer Recommendation

## Data Set
[Olist Public Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

## Reports

[Final Presentation with speaker notes](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

## Summary
Using a dataset of over 100k real world orders provided by Olist,
the largest department store in Brazilian market places, the code
provided in Jupyter Notebooks constructs a product recommendation
engine.  

This engine can take a user's unique id and a minimum similarity 
score and return product ids the user has not purchased yet, ranked
by similarity to the user.  Three groupings were used to categorize
the data:
1. Customer id  vs  Product Category Group
2. Seller id  vs  Product Category Group
3. Customer id  vs  Product Id

And the code generates a Category Group csv file (containing Group Ids
percentage of purchases across categories, and number of users in the 
Group) and a cosine similarity csv file (containing Group Ids and the 
similarity score between each group)

Using these files, product recommendations can be generated using the
following methods:
1. Using a customer's id and a Group id, return products of its group and similar groups using similarity table
2. Using customer's id and list of orders, determine similarity between the user and existing groups in Category table.  Return product ids of groups similar to this user
3. Using customer's id and list of orders, use Agglomerative clustering to cluster the categories and the user.  Return product ids of the user's cluster

Each method can also consider RFM scores of Buyers or Sellers when 
considering the quality of the recommendation.  Code has also been 
provided for updating the Category Group and Similarity Score tables 
based on new orders.

## Notebooks
_1 - Data Wrangling.ipynb_
- Investigation into several Data Sets, including Olist
- Data grouping of several Olist tables into a single orders DataFrame

_2 - EDA.ipynb_
- RFM Score Generation 
- Tableau Workbook Links
  - [RFM Score Investigation](https://public.tableau.com/authoring/OL_Data_Metric_EDA/SellerGeo#1)
  - [Mapping of Olist Orders](https://public.tableau.com/app/profile/karl.deakyne/viz/OL_Data_Orders_Mapped/OrdersMapped)

_3 - Similarity Score Generation.ipynb_
- Generation of Category Group and Similarity Score Tables
- Investigation into Similiarity Score's performance based on Silhouette Scores
  - Euclidean Distance
  - Modified Euclidean Distance
  - Cosine Similarity

_4 - Product Recommendation Engine.ipynb_
- Methods to generate ranked recommendations
- Method to update Category and Similarity tables based on new orders
