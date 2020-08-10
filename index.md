![Seattle](https://raw.githubusercontent.com/chrisestevez/chrisestevez.github.io/master/imgs/dataset-cover.jpg)


The cross-industry standard process for data mining (CRISP-DM) helps plan and organize a data project using a six-step process.

**CRISP-DM STEPS**
* Business Understanding
* Data Understanding
* Data Preparation
* Modeling
* Evaluation
* Deployment

In this post, we will apply the CRISP-DM methodology to the Seattle Airbnb open data set. We will use the following tools for the analysis and visualization python, pandas, sklearn, and seaborn.

# Business Understanding

Airbnb is one of the world's largest market place for accommodations. Having around 7 million accommodation all over the world and hosted by local people. Airbnb encourages tourism in individual communities and fosters a  people-to-people connection.

Airbnb was founded in August 2008, San Francisco, CA, by Brian Chesky, Joe Gebbia, Nathan Blecharczyk. The company has more than 7M listings worldwide, with more than 100K cities, and listings in more than 220 countries and regions.
#### [source](http://airbnb.com)



## Questions to be answered are the following:

1. Are there any changes in price listings from month to month in the Airbnb Seattle prices?

2. Are there price differences in the types of properties?

3. What neighborhood accounts for the most listings?

4. Does the price vary by neighborhood?

5. What features help predict listing price?




# Data Understanding

Kaggle provided the dataset and consist of three files calendar, listings, and reviews from the Seattle Airbnb Open Data. The range of the data is from 2016-2017. The calendar dataset has the availability of a particular property on a given date with pricing. The listings provide information regarding the location, host details, and metadata. Finally, the reviews fie contains reviews by visitors.

We will be focusing on a subset of the calendar and listing data. The first step will be to overview the dataset, clean, and later merge listing and calendar data. After cleaning the data, we will answer the following questions:

1. Are there any changes in price listings from month to month in the Airbnb Seattle prices?

2. Are there price differences in the types of properties?

3. What neighborhood accounts for the most listings?

4. Does the price vary by neighborhood?

5. What features help predict listing price?


# Data Preparation
To accurately answer the questions, the calendar and listing data needed to be clean. The steps were the following:

## Calendar
* Format date column
* Cleaned the price column and transformed to numeric
* Extracted the month name from the date and converted the month to an ordered category

## Listings
* Selected id, neighbourhood_group_cleansed, property_type, room_type, and accommodates columns
* Merged listings to calendar data where available is equal to true

## Answer Questions 1-4
### 1. Are there any changes in price listings from month to month in the Airbnb Seattle prices?

Given the calendar listings, there appears to be price variation within the months. Prices in January are the lowest, and July is when the listing price is at the highest.

![price trends](https://raw.githubusercontent.com/chrisestevez/chrisestevez.github.io/master/imgs/price_trends.png)

### 2. Are there price differences in the types of properties?

Property prices range from $10 to $1,650, with the median at $109. Properties categorized as shared room private rooms have the lowest prices. The most popular rental is the entire home/apt.

![prices by property types](https://raw.githubusercontent.com/chrisestevez/chrisestevez.github.io/master/imgs/price_by_prop_type.png)

![price by room type](https://raw.githubusercontent.com/chrisestevez/chrisestevez.github.io/master/imgs/price_by_room_type.png)

### 3. What neighborhood accounts for the most listings?

The neighbourhood_group_cleansed least popular property had 3,394 listings, an average of 54,973, and a median of 33,148. Other neighborhoods account for the most listings in the dataset with 194,661 listings. The category is composed of many communities. The least popular is Interbay and Seward Park.
 
![neighborhood listings](https://raw.githubusercontent.com/chrisestevez/chrisestevez.github.io/master/imgs/neighborhood_listings.png) 

### 4. Does the price vary by neighborhood?

The average neighborhood price ranged from $90 to $198. The most expensive neighborhood was Magnolia, which was the third least popular in terms of listings.

![neighborhood price.png](https://raw.githubusercontent.com/chrisestevez/chrisestevez.github.io/master/imgs/neighborhood_price.png)

### Feature engineering
To answer the last question, we will fit a random forest model. The model will be an exploratory model to identify essential features. A total of 62 columns were created, and the steps taken to manipulate the data are the following:

* One hot encode month_name, property_type, neighbourhood_group_cleansed, room_type, and accommodates
* Dropping of columns used to hot encode
* Cleaning column names
* Dropped Property type other, and other neighborhoods 

# Modeling
A random forest model is used to explore the final dataset. The model will use month, neighborhood, property type, room type, and accommodates. The model use 70/30 data split and yielded an R^2 of 0.67. The model did not use cross-validation and was not optimized. 

### 5. What features help predict listing price?
The model identifies the entire home apartment, as the main feature driving the model. The accommodation was also a  driver. Additionally, having the listing in Queen Anne or Downtown is a driver of price listing.

![model features](https://raw.githubusercontent.com/chrisestevez/chrisestevez.github.io/master/imgs/features.png)

# Evaluation & Deployment
Given the nature of the analysis, we will not be evaluating the model for performance and deployment. Ideally, one could build multiple models using different algorithms or optimize the existing model. The user will then compare the results provided and select the final model. The final model could be composed of one model or a combination of models. Additionally, the deployment phase would consist of integrating the model into an existing process or used to learn complex relations that exist within a dataset as per our example.

# Conclusion
In this post, we applied the CRISP-DM methodology to the Seattle Airbnb Open Data. We explored a subset of the data using exploratory data analytics in addition to machine learning. The supporting code can access via the [link](https://github.com/chrisestevez/Data-Scientist/blob/master/CRISP_DM/Project1/Write_A_Data_Science_Blog_Post.ipynb).






