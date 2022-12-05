## RECOMMENDER SYSTEM

### 1) Team members
- Alessia Bresolin (275601)
- Raffaele Girardi (265131)
- Alessandro Ivashkevich (276871)

### 2) Introduction
What does our project consists in? We have identified ourselves into members of the data science team of a prestigious fashion firm. Our primary aim is to boost the revenues of the company using any possible legal mean. 
Our online platform does not suffer any particular issue. However, we want to improve our recommender system. In this project, we will test different systems and select the most efficient one.

### 3) Methods
We have been proposed 3 datasets containing information for: customers, transactions and articles. We have analyzed all of them through a deep explanatory data analysis. 

#### a) Data Understanding
- 'recsys_customers.csv': customer id associated to age and optional participation to fashion news and club member.
- 'recsys_articles.csv': article id associated to the name of the product, colour of the product (from very detailed to very general), department, group of membership, section or type of garment.
- 'recsys_transactions.csv': purchase done by a customer on a certain date

#### b) Data Preparation 
The output of this first step is a clean and more comprehensible dataset. This stage helps us to have a better insight of our data, especially about the relationship between customers and transactions. We have identified all the missing values and highlighted some important features of each dataset.
- Replace Null values in the column 'age' in 'recsys_customer' with the mode of the values;
- Create additional dataframes;

#### c) EDA
Explanatory Data Analysis is a fundamental process in Machine Learning for data preparation. It is key to understand the intrinsic features of our datasets by applying different Python packages:
- Pandas;
- Numpy;
- Sklearn;
- Matplotlib.pyplot;
- Seaborn.

**Customers**
We have data for more then 40 thousands customers. For each of them, we have records of their identifier, if they are subscribed to fashion news, if they are part of the club member and their age. Through EDA we have noticed that there weas a small percentage of Null values (0.32%) in the age column. We decided to replace them by the average of the age of all the customers. 

We have grouped them in age categories, calculated how many people belong to each of them and the proportion of people who is subscribed to either the club membership or to fashion news.

![Club Membership!](images/club_membership.png 'Club Membership')

![Fashion News!](images/fashion_news.jpg 'Fashion News')

**Transactions**
For transactions, we have a file that stores all the purchases made by each customers and the date in which they made it. We calculated the number of transactions per customer and the maximum value is 104 transactions made by a single customer. To get a better insight of the dataset, we have grouped all the transactions in classes. Only a small proportion of customers has done more than 30 transactions. We finally calculated also the number of customers that has bought each product.

![Transaction Groups!](images/transactions_group.png 'Transaction Groups')

**Articles**
6536 articles are stored in our dataset, with all their characteristics. Each product belongs to many categories: they have a garment group, a section, a deparment, an index group and a type. We use the Explanatory Data Analysis to look for the best identifier for all the products. We have decided to discard the more precise classes to avoid overfitting and also too general ones, because they may lead to an inaccurate recommender system. We finally decided to take into consideration only the article type and section. Furthermore, we have noticed the presence of 'Unknown' items.
Another attribute of the articles is the colour. Again, we have taken into consideration only the 'perceived_colour_master' which was, for us, the best middle way between dealing with overfitting and having a precise model.

#### d) Data Analysis

## 4) Recommender System
Our recommender system generates a list of articles that a customer might be interested in, basing on its actual purchases and on the similarities with other users. 

##### Content filtering 
The first type of recommendation system we have applied is: content filtering recommender system. 
The final suggestions are shaped on the basis of features of the products, such as their color, their department and so on with all the pther properties of the articles.

##### Collaborative filtering
The second type of recommendation system we have applied is: collaborative filtering recommender system.
This kind of system is based on the idea of considering customers' opinions on the different products and suggest an article based on other purchases of the user and purchases and opinions of customers that are similar to him. Basically, in this case, we use information collected by different customers to recommend products to the actual customer.

## Final output
Our recommender engine has been implemented to boost the revenues of our company by predicting user preferences and recommending the right products to each user. We have applied different kinds of recommendations using content-based and collaborative filtering systems. 

