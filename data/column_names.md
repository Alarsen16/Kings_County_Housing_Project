# Column Names and Descriptions for King County Data Set
* `id` - Unique identifier for a house
* `date` - Date house was sold
* `price` - Sale price (prediction target)
* `bedrooms` - Number of bedrooms
* `bathrooms` - Number of bathrooms
* `sqft_living` - Square footage of living space in the home
* `sqft_lot` - Square footage of the lot
* `floors` - Number of floors (levels) in house
* `waterfront` - Whether the house is on a waterfront
  * Includes Duwamish, Elliott Bay, Puget Sound, Lake Union, Ship Canal, Lake Washington, Lake Sammamish, other lake, and river/slough waterfronts
* `view` - Quality of view from house
  * Includes views of Mt. Rainier, Olympics, Cascades, Territorial, Seattle Skyline, Puget Sound, Lake Washington, Lake Sammamish, small lake / river / creek, and other
* `condition` - How good the overall condition of the house is. Related to maintenance of house.
  * See the [King County Assessor Website](https://info.kingcounty.gov/assessor/esales/Glossary.aspx?type=r) for further explanation of each condition code
* `grade` - Overall grade of the house. Related to the construction and design of the house.
  * See the [King County Assessor Website](https://info.kingcounty.gov/assessor/esales/Glossary.aspx?type=r) for further explanation of each building grade code
* `sqft_above` - Square footage of house apart from basement
* `sqft_basement` - Square footage of the basement
* `yr_built` - Year when house was built
* `yr_renovated` - Year when house was renovated
* `zipcode` - ZIP Code used by the United States Postal Service
* `lat` - Latitude coordinate
* `long` - Longitude coordinate
* `sqft_living15` - The square footage of interior housing living space for the nearest 15 neighbors
* `sqft_lot15` - The square footage of the land lots of the nearest 15 neighbors







Adam Speech:

As you can see by the graph on screen, our RMSE values across the four different models have decreased. For starters, it's certainly important to understand RMSE, or root mean squared error, as the average amount we were WRONG by on each prediction versus the actual price.

Before we talk thru our models, we removed outliers to rid our models of skewness by the extreme values in sqft_living and bedrooms. While these aren't mutually exclusive, we believed that talking the inner 95% of these columns would give us a good data set to work with. 

To talk thru our models quickly: 
Our baseline model predicted the house value off of the average. Our simple model was improved by using the most correlated variable to price which was the size of the living space. We then ran a model where we included all variables to determine which values impacted price the most and then ran a final model with those statistically significant values trimmed down by which variables met all assumptions for linear regression. Next, Mendy will speak about those varibles!

