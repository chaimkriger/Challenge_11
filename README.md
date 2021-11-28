# *Forecasting Net Prophet

Overview- With over 200 million users, MercadoLibre is the most popular e-commerce site in Latin America. Iv've been tasked with analyzing the company's financial and user data in clever ways to make the company grow. In this application, I you want to find out if the ability to predict search traffic can translate into the ability to successfully trade the stock.

My first step is to find unususual patterns in hourly Google search traffic. Does the Google search traffic for the company link to any financial events at the company? To answer this question, I pick out any unusual patterns in the Google search data for the company, and connect them to the corporate financial events.
I read the search data into a dataframe, and sliced the data to just the month of May 2020, the month that MercadoLibre released its quarterly financial results. I used hvplot to visualize the results and found that indead, there was a spike in search traffic during the month of May. The stock price for MercadoLibre spiked during the same month. This information can definetly be of use to the company.

My next step is to mine the search traffic data for predictable seasonal patterns of interest in the company. To do so, I group the hourly search data to plot the average traffic by the day of the week. Then, I use hvplot to visualize this traffic as a heatmap. Doing so allows me to determine the times and days of the week when MercadoLibre recieves the most Google searches. I also group the search data by week of year which shows me that search traffic tends to increase during the winter holiday period, weeks 40-52.

The company would now like to know if there is any relationship between the search data, and the company stock price. To do so, I read in the stock price data, and concatenate the dataframe with the google search trends dataframe. I slice the data to just the first hald of 2020, and use hvplot to help me determine if indeed there is any relationship or not. Doing so helps me determine that there was a significant drop in search trends during March, and the stock price trended downwards during that timeframe. Similarly, in may 5th there was a sharp increase in search traffic, which was reflected in the stock price trending upward.
I then create 3 new columns in my dataframe. Lagged search trends, stock volatility, and hourly stock return in an attempt to find correlation between the lagged search traffic and the stock volatility, and between the lagged search traffic and the stock price returns. After reviewing the data, there didnt seem to be any significant correlation.

Now, I need to produce a time series model that analyzes and forecasts patterns in the hourly search data. To do so, I set up the google search data for a Propher forecasting model. After estimating the model, I plot the forecast. The near term forecast for the popularity of MercadoLibre is looking great! The marketing team will be pleased!

I then plot the individual time series components of the model to show that 12:00-1:00 am seem exhibit the greatest popularity, tuesday and thursday seem to get the most search traffic per week, and October gets the least search traffic out of the rest of the months.

With that, my data analytics for MercadoLibre is complete.




