# Kings_County_Housing_Project

## Overview
We have been approached by a real estate company about how to accurately appraise homes in King County so that they can give their customers accurate reccomendations when it comes to buying and selling homes. We've been given a data set that contains various information about the different homes within King County.
## Business Understanding
We'll be looking to answer the following questions to help us better understand the layout of the housing industry.

* How does number of bathrooms/bedrooms effect the price?
* How much does square footage matter?
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


## Model 3
then we'll check for collinearity between independent variabels

![image](https://user-images.githubusercontent.com/12703065/142474514-18d77e16-667e-424d-bac5-aeebdf13f0b0.png)

Looks like there's a good amount of collinearity in our data. In order to avoid this we have to drop one variable from each pair. If we dropped sqft_living and sqft_above, we'd be able to keep grade, bathrooms, sqft_living15. We also still have our bedrooms variable, as well as our sqft_basement.

![image](https://user-images.githubusercontent.com/12703065/142636540-f16e9740-507a-4daa-b20c-74b4d4312eaa.png)

Looking at the coefs from this model, we can see that the sqft of a home on average will increase the sale price by 114 per square foot, the sqft of the 15 surrounding homes will on average increase the sale price by 50, and improving the grade will increase the sale price by 90,000.

But we know that because grade is really a categorical number rather than a numerical number, all we can really infer from this is that the grade is strongly correlated, but we can't put a specific number on it.

Bathrooms, interestingly enough have a negative correlation. The explanation for this may be, that because the model takes in to acount the square footage, it wants to figure out how bathrooms impact the price given that it's a big home. In that case it's is possible that homes that are very big and therefore expensive don't have higher prices when there are more bathrooms.

Alternatively though the above model and collinearity check included outliers in the data set. After putting the columns we were planning to remove after the first
collinearity test back into the data and removing outliers we got different results. Now, the only colinear factors we found were sqft_living and sqft_above. This allows us to remove sqft_above and keep more columns in our data set than we would have been allowed to do before removing outliers.
## Final Model

![image](https://user-images.githubusercontent.com/12703065/142636864-07204801-6ee4-4c37-8235-fa0e8c983d30.png)



## Checking For Assumptions

Investigating Normality

![image](https://user-images.githubusercontent.com/12703065/142637054-cfc978b4-14a7-43ef-a81e-95c56aeb8b06.png)

Regression Plots

![image](https://user-images.githubusercontent.com/12703065/142637135-efd553be-3e35-4ec5-a783-51de38314657.png)

![image](https://user-images.githubusercontent.com/12703065/142637163-b7f745bc-f581-474b-9752-f2aa17db3872.png)

![image](https://user-images.githubusercontent.com/12703065/142637181-30470f14-00a7-4317-a2d6-483c1934601e.png)

This is how we'd expect our final model to perform. The RMSE matches the same RMSE as our fourth model HOWEVER we made these changes to the final model to satisfy the assumptions of linear regression. The four independent variables are homoscedastic by the graphs above meaning the variance doesn't increase as the independent variable gets bigger or smaller. We also know that these aren't collinear given the correlation graph we used above.

![image](https://user-images.githubusercontent.com/12703065/142637249-b15ed5db-18ce-4150-933e-08c9034fdd4d.png)

## Conclusion
