# Predicting Housing Prices in King County, WA, Using Multiple Linear Regression

**Author**: [Matt Schwartz](mailto:mtschwart@gmail.com)

## Overview 

The following report provides data and analysis on housing prices in King County, Washington State, and details a number of multiple regression models used to predict these prices. 

## Business Problem

Buying a home can be a frustrating process. Everyone has some idea of their dream home, but when it comes down to actually buying one, chances are there are blockers to getting the exact one you want. Maybe the square footage isn't right, or you wish it had another bedroom, or you simply don't have enough cash on hand to cover the down payment. Whatever it is, the process is long and arduous and requires lots of research.

As a prospective home buyer, one of the last things you'd want to do is overpay for that home. It's hard to know when you're getting fleeced, especially when you're really desparate to buy. This project is meant to help buyers not overpay for their home. By building a reliable prediction engine, we can help new home buyers know if they're getting a good price. We'd also be able to tell them what factors influence prices, and by how much. In theory, waterfront property will be cost more, but by how much? Does a house that's been renovated have much higher prices than those that haven't? How about how old the house is, or the zipcode in which it was built?

The following will attempt to build a prediction engine that prospective home buyers can use when searching for ideal home. In the future, this model can be used as the backbone for an app or website, in which you can input the information of a house that is on sale, predict what the market price should be, and compare it to listings across the internet on sites like Zillow.

## Data

The data in this project comes from King County of Washington State. The county includes both Seattle and Bellevue, so we're looking at a large number of houses - over 21K. The dependent variable in this analysis will be home prices.

To help predict the price, we will be using the following explanatory variables:

- Rooms
- Square footage in each house, and the square footage of the houses' 15 closest neighbors
- Year built
- Year renovated (if applicable)
- Condition (overall condition of the house)
- Grade (overall grade given to each house by the King County Grading System)
- Zipcode
- Latitude and longitude
- Using these variables, and others I create, I will attempt to create a quality model (defined by satisfying the assumptions of linear regression, a high R2, and a low root mean squared error) that can accurately predict the price of a house and also provide clarity into how different variables affect the price.

## Methods

To build a prediction engine, we utilized multiple linear regression. By regressing the variables listed above on price, we were able to account for a significant portion of the variation in price. To eliminate the influence of major outliers, we limited the sample to houses that sold for between $100,000 and $1,000,000, and that were smaller than 4500 square feet in total space.

In addition, we create a number of variables based on our existing data. These include each houses' distance from downtown Seatlle in miles, age, and a dummy variable for whether a house was renovated or not.

## Results

Our final model, which included zipcodes, improved the R2 value by 16 percentage points over our baseline model. It also reduced root mean squared error by $26K. 

Baseline Model:

![baseline model]

In addition, we calculated the impact that each independent variable had on price. These findings include:

Baseline 

![ratings and revenues](/images/ratings_revenue.png)

Average budgets are increasing year-over-year.

![budgets_year](/images/budgets_year.png)

The average rating for the top ROI movies is well below those of the top grossing

![rating_roi](/images/ratings_roi.png)

![rating_top_gross](/images/ratings_top_gross.png)

  - A one unit increase square footage increases price by 19% on average, holding all else equal.
  - An extra year of age decreases price by an average of about 1.4%.
  - One extra mile further from downtown decreases price by an average of about 13%.
  - A house on the waterfront is 72% more expensive than a house that isn't, on average.


## Conclusions

This analysis led to a number of useful findings:
- Dramas are far and away the most frequent type of movie produced. However, they are not the most lucrative. Adventure, animation, sci-fi, action, and fantasy rake in the most cash.
- We see a strong, positive correlation between budgets and revenues. Movies that tend to spend a lot, also make a lot of money, though this subject could use further analysis
- Average budgets per year are increasing while the number of movies produced a year are slightly decreasing. It's possible that that larger productions and their profitability are discouraging studios from financing smaller movies, that may have equal returns on their investment, but don't earn as much overall.
- There is a clear, strongly positive correlation between revenues and average ratings. This deserves further analysis, but if your movie is rated highly and the production budget was large, chances are the movie is making a lot of money.
- We found a negative correlation between ROI and average rating. This might just be noisy data but it does tell us that ROI has no real connection to ratings, nor does it with how much a movie will earn. The top ROI movies rated significantly worse than the top grossing movies

## Further Analysis

We could glean some additional insights from this data by increasing the rigour of our statistical analysis. Some areas I'd like to explore:

- Is the decreasing number of movies being produced a blip or a trend, and are growing production budgets in some way causing this to happen?
- Is there any sort of causation between average ratings and revenues? What other factors lead to high average ratings? Is there a way to engineer movie production to create only high rating movies?
- To what extent does there exist some causation between production budgets and average rating? We found a weak but positive correlation. At what spend threshold do we begin to see diminishing marginal returns?
- Would we see a positive correlation between ROI and ratings if we removed horror and mystery films? To what extent is there a real connection there?

## For More Information

Please find the full analysis in the Jupyter notebook contained in this respository.

For any questions, please contact Matt Schwartz at [mtschwart@gmail.com](mailto:mtschwart@gmail.com)




## Repository Structure

```
├── images
├── data
├── CONTRIBUTING.md
├── LICENSE.md
├── Link_to_Presentation_Recording.docx
├── Predicting_Housing_Prices_In_King_County_Presentation.pdf
├── Predicting_Housing_Prices_In_King_County.pdf
├── Predicting_Housing_Prices_In_King_County.ipynb
├── README.md
```
