# Stock Market Analysis

## Table of contents
- [Project Overview](#Project-Overview)
- [Business Demand Letter](#Business-Demand-Letter)
- [Business Request and user stories](#Business-Request-and-user-stories)
- [Tools used](#Tools-used)
- [Data Preperation](#Data-Preperation)
- [Data Visualisation](#Data-Visualisation)
- [Data Source](#Data-Source)
- [Results / Findings](#Results-Findings)
- [Conclusion](#Conclusion)


## Project Overview
The Stock Market Analysis Project provides a comprehensive evaluation of stock price trends and performance for six leading companies over an extended period. By leveraging Pandas for robust data analysis and Tableau for dynamic visualizations, this project aims to identify critical patterns and insights, including price fluctuations, moving averages, and overall market performance. 

Sourced from Kaggle, the historical stock data is cleaned and transformed, enabling the creation of interactive dashboards. These dashboards facilitate tracking of stock performance and allow for filtering by stock symbols and time periods.
This project aims to provide valuable insights that support informed investment decisions, helping investors navigate the complexities of the stock market effectively.

## Business Demand Letter [View](https://github.com/itsmanishjoshi/StockMarket-Analysis/blob/master/Business%20Ticket/Business%20Demand%20Overview%20%26%20User%20Stories..docx)
Client: John – Portfolio Manager

Hi Manish,

I hope you are doing well. We are looking to improve our stock analysis reports and transition from basic charts to more advanced visual dashboards. Specifically, we want to focus on stock price movements over time, comparing performance across sectors and individual companies. It would also be beneficial to filter by various factors like stock symbols, industries, and time periods. Additionally, we often compare stock performance against market indices, so I've included historical index data in a spreadsheet. Our primary focus will be on the past 4 years of data, and I would like a dashboard that allows for easy comparison. Let me know if you need any further details.

Best regards,
John

## Business Requests and User Stories [View](https://github.com/itsmanishjoshi/StockMarket-Analysis/blob/master/Business%20Ticket/Eample%20Business%20Request%20-%20Mail%20from%20Client..docx)

|No. | As a (role) | I want (request/demand) |
|---|---|---|
|1. | Portfolio Manager |To get a dashboard overview of stock market performance over time. |
|2. | Investment Analyst |A detailed overview of stock price movements by individual stock symbols. |



## Tools Used
- Pandas: Data Cleaning, adding columns and calculating Moving Averages.
- Tableau: Creating Interactive Visualizations and Dashboards.

## Data Preparation
In the initial data preperation phase, we performed the following tasks:

1. Data loading and inspection.
2. Handling Missing Data.
3. Data cleaning and preperation.

### Excel
The raw data looks similar to the pic below, (Apple)
![Excel data sample](https://github.com/itsmanishjoshi/StockMarket-Analysis/blob/master/Pandas/Raw%20data%20-%20apple%20ss.png)

### Pandas
During the initial data preparation phase, the following tasks were performed:

1. Data loading and inspection.
 ```python
   import pandas as pd
    apple = pd.read_csv("apple_data.csv")
    facebook = pd.read_csv("facebook_data.csv")
    google = pd.read_csv("google_data.csv")
    nvidia = pd.read_csv("nvidia_data.csv")
    tesla = pd.read_csv("tesla_data.csv")
    twitter = pd.read_csv("twitter_data.csv")
   ```
2. Handling Missing Data/adding columns.
```python
df = [apple, facebook, google, nvidia, tesla, twitter]


for i in df:
    i['MA50'] = i.Close.rolling(50).mean()
    i['MA200'] = i.Close.rolling(200).mean()
```
Adding columns:
1. Creating column 'Previous day closing price'.
```python
for i in df:
    i['Previous day closing price'] = i.Close.shift(1)
```
2. Creating column Change in price:
```python
for i in df:
    i['Change in price'] = i['Close'] - i['Previous day closing price']
```

Here's how the final processed data looks in python(pandas):
![pandas](https://github.com/itsmanishjoshi/StockMarket-Analysis/blob/master/Pandas/Pandas%20final%20out%20ss.png)

## Data Visualisation (Tableau)

"Below are snapshots illustrating key analyses from the project.

### 1.Moving Average
- The first set of visuals highlights changes in stock prices and calculated moving averages over time.
![Moving Average](https://github.com/itsmanishjoshi/StockMarket-Analysis/blob/master/Dashboard/Moving%20average.png)


### 2.Price Percent change
- The second set of visuals highlights changes in stock prices and providing insights into price trends and the volume of price.
![Price change](https://github.com/itsmanishjoshi/StockMarket-Analysis/blob/master/Dashboard/Price%20percent%20change.png)


### 3.Dashboard

- The final image showcases the completed interactive Tableau dashboard, integrating these insights for comprehensive stock performance tracking."

![](https://github.com/itsmanishjoshi/StockMarket-Analysis/blob/master/Dashboard/Dashboard%20ss.jpg)

To download the final Tableau file, please [click here](https://github.com/itsmanishjoshi/StockMarket-Analysis/blob/master/Dashboard/Stock%20Market.twb)


## Data Source
The dataset for this project was sourced from [Kaggle](https://www.kaggle.com), a reputable platform for high-quality datasets. It contains historical stock market data, including stock prices, trading volumes, and other relevant financial metrics. 

This data was used to perform in-depth analyses and build visualizations that provide insights into stock performance and market trends.[Download dataset](https://www.kaggle.com/datasets/jacksoncrow/stock-market-dataset)


## Insights / Findings


### Moving Average

- The analysis of moving averages for six selected companies reveals notable stock price trends between 2016 and 2020:

- Initial Rise (March 2016 - March 2019): Starting from March 1, 2016, the stock prices of all six companies showed an upward trajectory, increasing from ₹100 to ₹200. This steady growth reflects positive market sentiment and strong performance across the companies during this period.

- Decline (March 2019): On March 1, 2019, the stock prices of the companies saw a significant decline, falling to ₹130. This drop could indicate market volatility or adverse external factors affecting the overall market or specific sectors during this time.

- Recovery and Continued Growth (March 2019 - 2020): Following the decline, from March 2019 through to 2020, the stocks regained momentum, rising beyond ₹300. This recovery and sustained growth suggest a positive market turnaround, with potential factors like improved financial performance, better market conditions, or strategic business decisions contributing to the upward movement.

These moving averages highlight the dynamic nature of stock market performance, showcasing periods of both growth and decline, followed by a strong recovery across the companies.

### Price Percent change


The analysis of price percentage changes for the selected companies reveals the following insights:

- Apple exhibited the highest price percentage increase, ranging between 58% and 60%, reflecting strong growth and market performance.
- Facebook followed closely, with a price percentage change of 48% to 50%, indicating robust performance.
- Google showed a more moderate increase, with a price percentage change between 35% and 40%.
- NVIDIA demonstrated a steady increase of 22%, showcasing consistent market growth.
- Tesla experienced a price percentage change of 15%, reflecting a more gradual rise.
- Twitter had the lowest increase, with a price percentage change ranging from 5% to 8%.

These figures highlight the varying levels of growth among the companies, with Apple and Facebook leading the way.


## Recommendations and Suggestions



### 1. Leverage Apple and Facebook's Momentum:
With the highest price percentage increases (Apple at 58-60% and Facebook at 48-50%), these companies demonstrate strong growth potential. Consider increasing investment allocations in these stocks to capitalize on their continued upward trajectory.
Monitor upcoming product launches, innovations, and earnings reports, which could further boost their performance.
Diversify into Google for Moderate Growth:

### 2. Google:
with a 35-40% price increase, presents a solid option for steady growth. Its diverse business model and dominance in digital advertising make it a safer long-term investment. A balanced portfolio should include Google for its resilience and consistent performance.
Focus on NVIDIA for Technological Growth:

### 4. NVIDIA:
with a 22% increase, offers growth potential in the fast-evolving tech sector, especially with its leadership in AI and gaming technologies. Consider positioning more investments in NVIDIA for exposure to cutting-edge tech developments.
Monitor Tesla's Market Movements:

### 5. Tesla:
Tesla's price percentage change of 15% is lower than other tech giants, its potential for future growth remains strong due to its innovation in electric vehicles and clean energy. However, given its volatility, maintain a cautious yet optimistic outlook and invest incrementally.
Consider Reevaluating Twitter's Performance:

### 6. Twitter:
Twitter's price percentage change of 5-8% indicates the slowest growth among the companies analyzed. It may be prudent to reevaluate investments in Twitter unless there are strategic changes or improvements that could enhance its market position.
Alternatively, look for other high-potential tech stocks that may offer stronger returns.
Regularly Review and Adjust Portfolio:

- Given the dynamic nature of the stock market, it is essential to regularly review your portfolio and adjust allocations based on market trends, emerging opportunities, and changes in company performance.
- Employ moving averages and other key metrics to track stock performance and identify early signals for buying or selling.


These recommendations aim to balance high-growth opportunities with stable investments to maximize returns while managing risk.



## Future Recommendations

### 1. Monitor Emerging Market Trends:

- Stay informed about developments in key sectors such as technology, healthcare, and clean energy, as these industries are likely to drive future growth. Investing in companies that are leaders in innovation within these sectors, such as AI, renewable energy, and biotechnology, could provide strong returns over the next few years.

### 2. Keep an Eye on Regulatory Changes:

- Regulatory changes in data privacy, environmental policies, and corporate taxation could impact tech giants like Apple, Facebook, and Google. Monitor the regulatory landscape to adjust your investments based on potential risks or opportunities stemming from new policies.



### 3. Explore International Markets:

- Diversifying into international stocks can provide growth opportunities beyond the U.S. market. With emerging markets showing potential, consider expanding investments into international companies, particularly in Asia and Europe, which may outperform in sectors like manufacturing, technology, and e-commerce.


### 4. Focus on Sustainability and ESG Investing:

- Sustainable investing is becoming a dominant theme in global markets. Companies with strong Environmental, Social, and Governance (ESG) practices, such as Tesla and NVIDIA, are likely to attract more investor attention. Prioritize investments in companies that demonstrate a commitment to sustainability and ethical practices.


### 5. Consider Long-Term Investments in Tech and AI:

- Artificial Intelligence (AI), cloud computing, and 5G technologies are expected to drive future growth in the tech sector. Companies like NVIDIA and Google, which have strong AI initiatives, are poised to benefit from these advancements. Long-term investments in these areas could yield significant returns.



### 6. Be Cautious of Market Volatility:

- While companies like Tesla and Twitter have shown slower or more volatile growth, they could still be valuable if you’re prepared for short-term fluctuations. However, it’s essential to manage risk carefully by keeping a diversified portfolio and staying updated on market conditions.



### 7. Invest in Defensive Stocks During Economic Uncertainty:

- In times of economic uncertainty or market corrections, consider investing in defensive sectors like consumer staples, utilities, and healthcare. These industries tend to be more resilient during market downturns, providing stability in your portfolio.



### 8. Utilize Data-Driven Strategies:

- Continue leveraging data analytics and tools like Pandas and Tableau to track stock performance, identify emerging patterns, and make informed decisions. Use technical indicators, moving averages, and historical data to optimize your investment strategy.
These future-focused recommendations aim to help you stay ahead of market trends, diversify wisely, and invest in areas with long-term growth potential while managing risks effectively.




## Conclusion

This stock market analysis has provided valuable insights into the performance of six key companies over the past few years, highlighting trends in price changes and moving averages. Companies like Apple and Facebook demonstrated the highest growth, presenting strong investment opportunities, while Google and NVIDIA showed steady and consistent performance. Tesla and Twitter exhibited more moderate or volatile growth, requiring cautious consideration.

The analysis underscores the importance of data-driven decision-making in stock market investments. By leveraging tools like Pandas for data analysis and Tableau for visualization, we can track performance trends, make informed comparisons, and adapt investment strategies based on market dynamics.

Looking forward, it's crucial to stay updated on market trends, regulatory changes, and emerging technologies, while maintaining a balanced and diversified portfolio. With careful monitoring and a focus on sectors with high growth potential, this approach will help maximize returns and minimize risks in a constantly evolving market.


🤝💻
