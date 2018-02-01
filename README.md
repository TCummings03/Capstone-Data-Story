## Capstone Data Story - DC Area Rent Prices

The dataset I will be focusing on is the same one I will use in my capstone project: webscrapped data of DC area rent prices [Code](https://github.com/TCummings03/Capstone-Data-Story/blob/master/Capstone%20Visualizations.ipynb). Housing prices are some of the biggest expenses people incur on a monthly basis. Therefore, finding the best or fair price for rentals is crucial to making sure your money is well spent. Analyzing rental prices in DC to glean some insight into what effects the rental price will provide both renters and leaders a better framework for understanding how much they should be paying for rent or how much they should be charging for rent.  Some important questions worth asking in order to gain this insight are:

1. What is the median/mean rental price and what does this distribution look like?
2. Where are the most expensive and cheapest rental neighborhoods? How do these values compare?
3. Does there seem to be a connection between location and price? Which neighborhoods are the most expensive?
4. How much more money does an extra bedroom cost? An extra bathroom? 
5. Prove Location, Location, Location


We will explore these questions below:


1. What does the rent price distribution look like?

![Distribution Prices](https://github.com/TCummings03/Capstone-Data-Story/blob/master/Images/download.png)

From the plot above, we can see that the distribution looks to be right skewed. In this plot, the mean and median are higher than the mode. In other words, there are a higher number of observations to the left of the mean. In addition, the mean is lifted higher as a result of some larger observations.  After checking these observations in the data wrangling portion of this project, we know that these larger values are not outliers. However, if this was initial exploratory data analysis, it would be wise to check the more extreme values to see if they are in fact valid points.  

The mean and median values are $2,366 and $2,100 respectively with a standard deviation of $1,148.51. In addition, the mean and median values based on sqft are $1.84 and $1.56 respectively with a standard deviation of $1.06.

2. Location! Location! Location!
![Link](https://github.com/TCummings03/Capstone-Data-Story/blob/master/Images/bokeh%20plot.png)

Looking at the distribution of rentals above by median locality price and colored by decile, we can see some interesting trends in the data. Perhaps, one of the most obvious trends is that the most expensive localities appear to be located in DC. Furthermore, as you move farther from DC (in all directions), rent prices appear to get cheaper with the darker points (lower deciles) located on the outskirts of DC. This makes sense intuitively as DC is an urban area with many attractions and the localities surrounding DC are suburbs. Let's take a closer look at the lower and upper deciles.

Most/Least Expensive Rentals (Top and Bottom Decile)
![Upper Decile](https://github.com/TCummings03/Capstone-Data-Story/blob/master/Images/Top10.png)

From looking at the plot above, it looks like the median sqft median price is around $3 which is almost double the median value of $1.56. Furthermore, the localities with the highest median sqft price are Downton DC (Dupont) and Tysons, which have median sqft prices around $4 per sqft. It is also interesting to note that Tysons and Aurora Highlands appear to have the largest interquartile ranges with the edges of the boxes extending farther than other localities.  In addition, we should notice that Northwest Washington appears to have many listings outside of the whiskers of the boxplot, which suggests there may be a lot of outliers.

![Lower Decile](https://github.com/TCummings03/Capstone-Data-Story/blob/master/Images/Bottom10.png)

From the plot above, we can tell that there is a drastic different in terms of median sqft price. Whereas the top decile consisted of a median price around $3, the median price for the lower decile looks to be around $1 per square foot. However, we also know that from looking at our plot of deciles by locality, that these cheaper priced listings are located farther from DC proper.  Another interesting thing to note about this plot is that compared to the top decile plot, most of the localities appear to have listings that are relatively similar in price with smaller boxes and whiskers.  

3. Bedrooms and Bathrooms

Another important factor that affects the rental price is the number of bedrooms and bedrooms. Let's take a closer look at the marginal prices of these to see how much and extra bedroom or bathroom affects the rental price.  For this, we will look at the median prices:

![Bedrooms](https://github.com/TCummings03/Capstone-Data-Story/blob/master/Images/Bedrooms.png)

Price of an extra bedroom:

0.5 -1: $53

1 -2 : $250

2 -3 : $200

3 -4 : $595

4 -5 : $602

From the table above, we can see that studio apartments and one bedroom apartments are similarly priced, whereas rentals with multiple bedrooms seem to have a larger difference in price.  One would guess that the more bedrooms a rental has, the more expensive it is, and it seems like that is the general trend from the graph above. However, we can also notice that the difference between 1-2 bedrooms($250) is larger than the difference between 2-3 bedrooms ($200), which may suggest that 3 bedroom rentals are a better value when looking for multiple bedrooms.


![Bathrooms](https://github.com/TCummings03/Capstone-Data-Story/blob/master/Images/Bathrooms.png)

Price of an extra bathroom:

1-2: $450

2-3: $495

3-4: -$300

From the table above, it appears that having an extra bathroom seems to have a greater effect on rent price than an extra bedroom.  However, as we suspected from bedrooms, we'd expect that the more bathrooms an apartment has, the higher the price. This seems to be the case for most of the differences, however, an interesting deviation is the change from 3-4 bathrooms.  Here, 4 bathrooms is actually cheaper ($2295) than 3 bathrooms ($2595).  Perhaps there are other factors contributing to the difference in price here, and this would require further investigation.

4. The bigger, the more expensive?

![Rent Price vs SQFT](https://github.com/TCummings03/Capstone-Data-Story/blob/master/Images/Rent%20price%20vs%20SQFT.png)

As we have hypothesized earlier, the larger the apartment, the higher the price. We can see this fairly clearly in the plot above, which shows rent price vs. sqft.  In the plot above, we see a postive correlation between rent price and sqft implying the more sqft, the higher the price.  However, from looking at the deciles above, we have the added benefit of knowing where the value lies in terms of price per sqft broken down by decile.  

# Conclusion:

From our visual exploration of the data, we have gained a greater insight into what effects rent price. First and foremost, we know that the number one rule in real estate holds true here: Location! Location! Location! The closer the rental is to DC, the higher the price.  In addition, we found out that the larger the rental (sqft), the higher the price.  Similarly, the more bedrooms/bathrooms a rental has, the higher the price and this makes sense because this generally means extra beds/baths lead to higher sqft, which in turn leads to a higher rental price. These intuitions will help lead us in the right direction when trying to build a model to predict rental price based on our features.
