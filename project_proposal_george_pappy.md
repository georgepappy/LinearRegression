# PROJECT PROPOSAL

##### IN THE CURRENT RESIDENTIAL REAL ESTATE MARKET, CAN A REASONABLE PREDICTION OF THE FINAL SALES PRICE OF A HOME BE PREDICTED BY USING RECENT SALES DATA?

With the COVID-19 pandemic has come a historic rise in home sales as people have spent more time social distancing and (to the extent possible) working from home. Demand far exceeds supply and realtors tell stories of literally dozens of bids on the same house and final sales prices far above the original listing price.

A small group of independent realtors in the West San Fernando Valley (a suburb of Los Angeles) has requested that I build them a model which can help them accurately forecast the sales price of homes which they may soon be involved with (representing either the seller or the buyer). They hope such models can give them and their clients a noticeable advantage in this historically competitive market.

Fortunately, the clients primarily deal with single family home sales, which aligns nicely with the current belief that the market for such residential properties behaves distinctly relative to the market for condominiums and other multi-family dwellings. Therefore, the data to be considered will be all single family home sales over the past three months in the West San Fernando Valley, using the 405 Freeway as the East-West cutoff line (i.e. every home sale to the east of this line will be disregarded).

The home sales data will be scraped from one of the major real estate websites. The target variable will be final home Sale Price, and each scraped sample will consist of the following ten predictors: 

- Beds (integer) 			: the number of bedrooms
- Baths (float)                : number of bathrooms (0.5 implies toilet only, 0.75 add shower only, 1.0 add tub and shower)
- Square_Feet (integer) : total interior square footage
- Lot_Size (integer)       : total exterior square footage
- Year_Built (integer)     : year when the house was built
- Zipcode (integer)        : USPS zip code containing the home
- Pool (boolean)            : 1 = has pool, 0 = no pool
- Garage (boolean)       : 1 = has garage, 0 = no garage
- Stories (integer)         : number of stories (floors) in the home
- Schools (float)            : average Great Schools score (from 0 - 10) for all schools serving the home's neighborhood

Additionally, general data for these home sales is available via direct csv file download from the scraped website, and it provides several more potentially useful predictors:

- Days on Market (integer) : the number of days between the home's listing date and the sale date
- HOA/Month (integer)       : the Homeowner's Association monthly fee in dollars (if any)

As previously indicated, this project will predict Home Sale Price based on some combination of the predictors above (and any additional features engineered from them). The baseline model will be an Ordinary Least Squares Linear Regression using features deemed to be most correlated to Home Sale Price. From there, variable selection and regularization will be applied to attemp to find a model that performs better. If time permits, attempts will also be made to employ other regression techniques (e.g. Random Forrest, XGBoost).

The tools required for this project are: 

1. Requests and BeautifulSoup to facilitate webscraping
3. Pandas to clean, explore  and generate the final modeling data
3. SKLearn to implement various linear regression models as well as to perform cross validation, variable selection and regularization
4. Matplotlib and Seaborn to visualize the data and present final results
5. Python 3.8 (to be able to use Requests, BeautifulSoup, Pandas, SKLearn, Matplotlib and Seaborn)

The Minimum Viable Product for this project will be a report (and slides) presenting a working model which can be shown to be optimally tuned to predict Home Sale Price based on the best subset of preditors and engineered features. Model quality will be demonstrated with graphs (Actual Sale Price vs. Predicted Value, Residuals vs. Predicted Value) and by citing figures of merit such as R-Squared and an appropriate measure of error (such as MAE, RMSE).

