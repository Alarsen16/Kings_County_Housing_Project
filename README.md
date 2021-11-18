# Kings_County_Housing_Project

## Overview
We have been approached by a real estate company about how to accurately appraise homes in Kings County so that they can give their customers accurate reccomendations when it comes to buying and selling homes. We've been given a data set that contains various information about the different homes within Kings County.
## Business Understanding
We'll be looking to answer the following questions to help us better understand the layout of the housing industry.

* How does number of bathrooms/bedrooms effect the price?
* How does square footage matter?
* Are there any other features that effect the price significantly?
## Data Understanding and Analysis

# Modeling

## Model 1
![image](https://user-images.githubusercontent.com/12703065/142472501-753b5bfe-6579-47a1-8831-30cab8a8227b.png)
From the heatmap you can see that sqft_living is the most correlated feature so we'll be using that as our baseline model
Train score: 0.48733518973535617
Validation score: 0.4945445156766466
We did linear regression on our baseline model and it showed that our r-squared value is .49.
We will try to make our model better

## Model 2
We will start by checking linearity between price and independent variables.
![image](https://user-images.githubusercontent.com/12703065/142473481-72aa7328-3d54-41ef-aadb-1c821b2b30d5.png)

From the above graphs, we can see that the following independent variables have a linear relationship to listing price:

* sqft_living15
* grade
* sqft_above
* sqft_living
* bathrooms

then we'll check for collinearity between independent variabels
![image](https://user-images.githubusercontent.com/12703065/142474514-18d77e16-667e-424d-bac5-aeebdf13f0b0.png)
Looks like there's a good amount of colinnearity (spelling?) in our data. In order to avoid this we have to drop one variable from each pair. If we dropped sqft_living and sqft_above, we'd be able to keep grade, bathrooms, sqft_living15. We also still have our bedrooms variable, as well as our sqft_basement.

## Regression Results

## Conclusion
