# Stock-Trends-with-Linear-Regression-and-Meta-Prophet

This project applies linear regression and the Meta Prophet model (formerly Facebook Prophet) to Meta’s closing price, for the sake of prediction and improved technical analysis. It models the impact of external features like the CPI, inflation, unemployment, and the federal funds rate on short term stock performance, as well as providing a brief overview of several significant tech stocks for context. 

## Background and Business Question
As the rise of generative AI has shown, tech can be wildly unpredictable. This is a reality that investors must contend with, especially day traders and others focused on short term gain. Many novices in this area may focus on metrics they hear on the news- inflation rates, unemployment rates, the CPI, and so on. Making the stock market more predictable makes investors more confident, less likely to take unnecessary risks, and reduces the chance of losses and panic.

## Goal
The goal of this project is to show how the stocks of several tech industry giants have trended from the end of 2020 to 2025, find useful insights for understanding the stock market, and create models that predict how one of these giants-Meta- will trend in the future.



## Datasets Used
This project used historical OHLC data pulled from the yfinance API. Monthly unemployment, inflation, and CPI data was imported from the Bureau of Labor Statistics (BLS). A dataset of the Federal Funds rate from 1954 to 2025, as well as two datasets of industry information were also used.

## EDA Part 2
EDA consisted of comparing Meta’s performance to several other companies from industries considered “tech,” before showing how macroeconomic factors trended during the same period. Since Meta is the focus of the project and for ease of viewing, other companies' stocks are filtered out
<img width="1402" height="525" alt="Meta_vs_unemployment" src="https://github.com/user-attachments/assets/65687c21-e0c9-49af-9c4b-1b625c68734e" />





Once the analysis narrowed to Meta, I showed how Meta's closing price varied from month to month and quarter to quarter.


<img width="1402" height="525" alt="Price_Change_Box_Plot" src="https://github.com/user-attachments/assets/87ebabb1-d8a2-4671-a606-08f390220367" />
<img width="1402" height="525" alt="Meta_Box_Quarterly" src="https://github.com/user-attachments/assets/c5210aa9-6a6c-463f-847e-8cfbab3ef02e" />
<img width="1402" height="525" alt="Meta_Box_Monthly" src="https://github.com/user-attachments/assets/e9456028-e8a3-4749-b0fe-05f6cb2454f2" />


## Methodology
I began by taking a look at the performance of several tech stocks based on niche-Snowflake (SNOW), Oracle (ORCL), and Salesforce (CRM) to represent small and large SaaS companies, Nvidia (NVDA) and Taiwan Semiconductor Manufacturing (TSM) to represent semiconductor manufacturers, and Microsoft (MSFT), IBM (IBM), and Intel Corporation (INTC) to represent traditional tech giants. After comparing them, I showed how inflation, unemployment, treasury bill rates, and the CPI trended during the same period. I then prepared for regression by joining those rates to the OHLC tables, adjusting monthly data to daily data and handling any missing features. After checking the assumptions of regression, I ran a basic linear regression model with Meta’s closing price, the inflation rate, the CPI, the federal funds rate, and the unemployment rate. This is followed by a linear regression model with the same features as well as the one, ten, and thirty year treasury bill rates. The analysis concludes with a look at the data with Meta’s own Prophet model.

## Performance
Models one and two, while performing exceptionally well on training data, did not perform well on the testing data. The FB prophet model had the same issue. While linear regression may not be the best for working with time series information, FB Prophet’s failure suggests an issue with the data itself. While macroeconomic indicators are an important part of stock movement, sentiment, the performance of rivals, product releases, and a number of other factors can affect a stock’s price. Unfortunately the models created were not useful

<img width="1402" height="525" alt="Meta_Stock_Prophet" src="https://github.com/user-attachments/assets/b0ede828-7f62-4e09-b996-414c85704ffd" />

## Insights
A linear relationship between Meta_Close and the inflation rate was observed, along with a curvilinear relationship between Meta_Close and the CPI. EDA revealed quarter four stock performance to be much more varied than quarters one through three.
<img width="1402" height="525" alt="Inflation_Rate vs Meta_Close" src="https://github.com/user-attachments/assets/7ab77def-20b3-4f42-8b46-50255cce8082" />


## Further steps
Additional features are necessary in order for the models to truly be effective. A feature to model sentiments like fear and greed, along with others to model product launches, global affairs, seasonality and industry changes is necessary to create an effective model. Additional models like decision trees and regularized regression may also prove to be a better fit for the data than simple linear regression. Further feature engineering is also necessary to get the most out of the data.


