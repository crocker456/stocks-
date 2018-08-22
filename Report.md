

# Portfolio Cumulative Return Forecasting

#### Bryant Crocker 

### Overview:

In the following analysis I look at a select number of fashion and sportswear company historical stock prices, calculate returns and forecast cumulative returns for various portfolios using Facebook's Prophet API.

**Selected Securities:**

- nke - Nike Athletics
- ads - Adidas Athletics
- vfc - Vans Footwear Company
- uaa - Under Armor Athletics
- aeo - American Eagle Outfitters
- lb - Lbrands
- goos - Canadian Goose
- ges - Guess?, Inc.
- rl - Ralph Lauren

**Start Date: 2017-03-16**

**End Date: 2018-08-21**

### Exploratory Data Analysis:

Exploratory data analysis, or EDA, was a term coined by my favorite statistician John Tukey.  During exploratory data analysis basic summary statistics and probability distributions are plotted ahead of mathematical models to lead intuition, further questions and data discoveries.  

To start I will plot a histogram of the returns or percent changes in price of the selected securities.

**Figure 1: Histograms of Selected Securites:**

![INDret](/Users/bryant/stocks-/INDret.png)

There is a good spread of volatility across the securites. It is likely that these can be constructed into a well diversified portfolio that minimizes risk and maximizes returns.

**Figure 2: Correlation Heatmap of Selected Securities**![cormat](/Users/bryant/stocks-/cormat.png)

The securites, in general have a low correlation among each other.  There are no negative correlations presents. It is often good to have negative correlation between assets.  The intuition behind this being that when one asset down another goes up, evening out losses.

### Portfolio Construction:

In this analysis I will use several different methods to compute portfolio weights and compare performance.

### Method 1: Equal Weight Portfolio:

In this portfolio an equal amount is invested into each security.  This is a common place to start with portfolio analysis.

**Figure 3: Equal Weight Portfolio Cumulative Returns and Weight Allocation:**![Equal](/Users/bryant/stocks-/Equal.png)

Investings equally in each security leads to cumulative returns of about 70%.

**Figure 4: One Year Forecast of Cumulative Equal Weight Portfolio Returns:**

![Portfolio2](/Users/bryant/stocks-/Portfolio2.png)

The portfolio is expected to reach cumulative returns of about 150% within one year.

### Method 2: Inverse Volatility Portfolio:

In this portfolio the weight is defined by the inverse volatility of each stock. 

**Figure 5: Inverse Volatility Weight Portfolio Cumulative Returns and Weight Allocation:**

![InvVol](/Users/bryant/stocks-/InvVol.png)

The inverse volatility weighting strategy led to just over 60% cumulative return in our observed data.

**Figure 6: One Year Forecast of Cumulative Inverse Volatility Portfolio Returns:**

![Portfolio](/Users/bryant/stocks-/Portfolio.png)

### Method 3: Mean Variance Optimization Portfolio:

This portfolio uses the weights that maximizes the sharpe ratio on the efficent frontier.

**Figure 7: Mean Variance Optimization Weight Portfolio Cumulative Returns and Weight Allocation:**

![MeanVar](/Users/bryant/stocks-/MeanVar.png)

The mean variance optimization weighting strategy led to just over 125% cumulative return in our observed data.

**Figure 6: One year Forecast of Cumulative Mean Variance Optimization Portfolio Returns:**

![MeanVarForecast](/Users/bryant/stocks-/MeanVarForecast.png)



Code to perform this analysis can be found at: https://github.com/crocker456/stocks-