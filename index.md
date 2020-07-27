![Seattle](https://raw.githubusercontent.com/chrisestevez/chrisestevez.github.io/master/imgs/dataset-cover.jpg)


The cross-industry standard process for data mining (CRISP-DM) helps plan and organize a data project using a six-step process.

CRISP-DM STEPS
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

We will be focusing on a subset of the calendar and listing data. The first step will be to overview the dataset clean and later merge listing and calendar data.







