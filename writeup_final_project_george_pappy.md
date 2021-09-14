# EDA PROJECT WRITE-UP

### Predicting Final Sales Price for Single Family Homes in the West San Fernando Valley

## Abstract

With the COVID-19 pandemic came an historic rise in home sales as people have spent more time social distancing and (to the extent possible) working from home. Demand far exceeds supply and realtors tell stories of literally dozens of bids on the same house and final sales prices far above the original listing price.

A small group of independent realtors in the West San Fernando Valley (a suburb of Los Angeles) has requested a model which can help them accurately forecast the sales price of homes which they may soon be involved with (representing either the seller or the buyer). They hope such a model can give them and their clients a noticeable advantage in this historically competitive market.

## Design

The clients primarily deal with single family home sales, which aligns well with the current belief that the market for such residential properties behaves uniquely relative to the market for condominiums and other multi-family dwellings. Therefore, the data to be considered will be all single family home sales over the past three months in the West San Fernando Valley, using the 405 Freeway as the East-West cutoff line (i.e., every home sale to the east of this line will be disregarded).

## Data

The data used for modeling in this project was scraped from a publicly-available real estate website and consists of a target variable (Home Sale Price) and ten predictors:

- Beds (integer) 			: number of bedrooms
- Baths (float)                : number of bathrooms (0.5 for toilet only, 0.75 add shower, 1.0 add tub and shower)
- Square_Feet (integer) : total interior square footage
- Lot_Size (integer)       : total exterior square footage
- Year_Built (integer)     : year when the house was built
- Zipcode (categorical) : USPS zip code associated with the home
- Pool (binary)               : 1 = has pool, 0 = no pool
- Garage (binary).         : 1 = has garage, 0 = no garage
- Stories (categorical)   : number of stories (floors) in the home
- Schools (float)            : average Great Schools score (0 - 10) for all schools serving the home's neighborhood

Additionally, supplemental data in CSV form was downloaded from the same website, providing an additional predictor:

- HOA/Month (integer)       : the Homeowner's Association monthly fee in dollars (if any)

The supplemental data also included a potential alternate target variable which could be used with the predictors above to develop related predictive models:

- Days on Market (integer) : the number of days between the home's listing date and the sale date

This Home Sale Price could be used as a hyperparameter in predicting this alternative target to give realtors a sense of how long the house will remain unsold at different price points. 

## Algorithms

The primary predictive models developed for this project were Linear Regressions, both with and without regularization (Lasso, Ridge, ElasticNet). Tree-based regressors (Random Forest, XGBoost) were also developed. Extensive feature engineering was performed to incrementally improve model performance before selecting the best models (one Linear Regressor and one Tree-Based model). The primary perfromance metric was Mean Absolute Error (MAE, in $) since this was deemed to be the most customer-friendly (and understandable) metric. R-squared and Root Mean Square Error (RMSE) were also considered during the modeling process.

## Tools 

The following tools were used in this project:

1. Requests and BeautifulSoup modules to facilitate webscraping
2. Pandas to clean, explore and generate the final modeling data
3. Statsmodels and SKLearn to implement various regression models as well as to perform cross validation, variable selection and regularization
4. Matplotlib and Seaborn to visualize the data and present final results
5. Python 3.8 (to be able to use Requests, BeautifulSoup, Pandas, Statsmodels, SKLearn, Matplotlib and Seaborn)

## Communication

In addtition to presenting final Project Slides to the stakeholders, all work (including the slides) will be available on GitHub: https://github.com/georgepappy/LinearRegression

