---
description: >-
  Use this indicator to understand the trajectory of global risks as perceived
  by investors.
---

# 📬 Turing Risk Index

{% hint style="info" %}
Daily index arrive between 11 pm - 4 am before market open in the US.
{% endhint %}

`Tutorials` are the best documentation — <mark style="color:blue;">`Business, Political, and Market Risk`</mark>

<table data-column-title-hidden data-view="cards"><thead><tr><th>Category</th><th>Details</th></tr></thead><tbody><tr><td>Input Datasets</td><td>Hundreds of leading indicators.</td></tr><tr><td>Models Used</td><td>Imputation Models, Time Series Forecast Models</td></tr><tr><td>Model Outputs</td><td>Market, Business, and Political risk indicators,</td></tr></tbody></table>

This indicator uses leading as opposed to lagging inputs. The constituents of the indicator has been selected for their recessionary predictive qualities.&#x20;

The final Turing Index is a simple average of Market, Business, and Political risk.

### Data Access

#### Retrieving Data

Fetch the latest index data using the SDK:

```python
from sovai import sov
df_risks = sov.data("risks")
```

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

#### Market Risks

Isolating market risk indicators

```python
from sovai import sov
df_market = sov.data("risks/market")
```

#### Business Risks

Isolating business risk indicators

```python
from sovai import sov
df_business = sov.data("risks/business")
```

#### Business Risks

Isolating business risk indicators

```python
from sovai import sov
df_political = sov.data("risks/political")
```

####

<table><thead><tr><th width="232">Column</th><th>Description</th></tr></thead><tbody><tr><td><code>TURING_RISK</code></td><td>Index combining Market, Business, and Political Risk using scholarly and research data.</td></tr><tr><td><code>MARKET_RISK</code></td><td>Global Value-at-Risk estimate for country indices using various models and an ensemble approach.</td></tr><tr><td><code>BUSINESS_RISK</code></td><td>Index tracking sentiment and conditions across business sectors using surveys, indicators, and news analysis.</td></tr><tr><td><code>POLITICAL_RISK</code></td><td>Index assessing domestic and global policy uncertainty using news, web search data, and reports.</td></tr><tr><td><code>HS</code></td><td>Historical Simulation method for VaR using the empirical distribution of past returns.</td></tr><tr><td><code>MA</code></td><td>Moving Average method for VaR assuming normally distributed returns.</td></tr><tr><td><code>EWMA</code></td><td>Volatility estimation method weighting recent observations more heavily.</td></tr><tr><td><code>GARCH</code></td><td>GJR-GARCH model estimating VaR incorporating responses to positive and negative shocks.</td></tr><tr><td><code>ENSEMBLE</code></td><td>Combined VaR estimate from multiple models to mitigate misspecification.</td></tr><tr><td><code>VIX</code></td><td>Index reflecting expected market volatility over the next 30 days.</td></tr><tr><td><code>SYSTEMIC</code></td><td>Measurement of global financial market interconnectedness using the absorption ratio.</td></tr><tr><td><code>TURBULENCE</code></td><td>Measure of financial turbulence calculated using the Mahalanobis Distance.</td></tr><tr><td><code>RECESSION_6</code></td><td>Six-month recession prediction probability using real-time data and gradient boosting models.</td></tr><tr><td><code>RECESSION_12</code></td><td>Twelve-month recession prediction probability with a proprietary diversification head.</td></tr><tr><td><code>RECESSION_24</code></td><td>Twenty-four-month recession prediction probability using economic and financial variables.</td></tr><tr><td><code>CAPE</code></td><td>Cyclically Adjusted Price-to-Earnings, a long-term stock valuation metric.</td></tr><tr><td><code>NAIIM_NEG</code></td><td>NAAIM Exposure Index reflecting active risk managers' equity market exposure.</td></tr><tr><td><code>AAII_NEG</code></td><td>AAII Sentiment Survey indicating individual investors' market direction opinions.</td></tr><tr><td><code>ADS_BUSINESS_NEG</code></td><td>ADS business conditions index tracking relative performance to average economic conditions.</td></tr><tr><td><code>NONMAN_OUTLOOK_NEG</code></td><td>Survey data on nonmanufacturing sector outlook from the Third Federal Reserve District.</td></tr><tr><td><code>MAN_PHIL_NEG</code></td><td>Monthly manufacturing survey from the Third Federal Reserve District assessing the sector's outlook.</td></tr><tr><td><code>MAN_TEX_NEG</code></td><td>Texas Manufacturing Outlook Survey tracking various sector indicators monthly.</td></tr><tr><td><code>MAN_NY_NEG</code></td><td>Monthly survey measuring manufacturing executives' perspectives in New York State.</td></tr><tr><td><code>CFNAI_FNEG</code></td><td>Composite index based on 85 monthly indicators of national economic activity.</td></tr><tr><td><code>ZEW_SENT_NEG</code></td><td>ZEW Economic Sentiment indicator measuring financial experts' economic outlook expectations.</td></tr><tr><td><code>ATLANTA_UNC</code></td><td>Survey on business uncertainty levels providing insights into economic conditions.</td></tr><tr><td><code>BUILDING_INDEX_NEG</code></td><td>Survey assessing sentiment in the building and construction industry.</td></tr><tr><td><code>CONSUMER_INDEX_NEG</code></td><td>Survey measuring consumer sentiment and perceptions in the economy.</td></tr><tr><td><code>INDUSTRY_INDEX_NEG</code></td><td>Survey capturing sentiment within the industrial sector.</td></tr><tr><td><code>MAIN_INDEX_NEG</code></td><td>Survey monitoring main economic indicators and business sentiment.</td></tr><tr><td><code>RETAIL_INDEX_NEG</code></td><td>Survey gauging sentiment within the retail sector.</td></tr><tr><td><code>SERVICES_INDEX_NEG</code></td><td>Survey measuring sentiment in the services sector.</td></tr><tr><td><code>MICS_ICS_NEG</code></td><td>Michigan series Monthly Indicator of Consumer Sentiment.</td></tr><tr><td><code>MICS_ICC_NEG</code></td><td>Michigan series Monthly Indicator of Consumer Confidence.</td></tr><tr><td><code>MICS_ICE_NEG</code></td><td>Michigan series Monthly Indicator of Consumer Expectations.</td></tr><tr><td><code>NEWS_SENT_NEG</code></td><td>Daily measure of economic sentiment from news articles.</td></tr><tr><td><code>TERM_SPREAD</code></td><td>Indicator representing the yield difference between long-term and short-term government bonds.</td></tr><tr><td><code>CREDIT_SPREAD</code></td><td>Measure of yield difference between below and above investment-grade bonds.</td></tr><tr><td><code>CORP_BOND_DISTRESS</code></td><td>Index quantifying distress in the corporate bond market.</td></tr><tr><td><code>MISERY_INDEX</code></td><td>Economic indicator combining unemployment and inflation rates.</td></tr><tr><td><code>HOUSING_AFFORD_NEG</code></td><td>Index measuring the affordability of housing.</td></tr><tr><td><code>NEW_TRUCKS</code></td><td>Sales data for heavy trucks above 14,000 pounds.</td></tr><tr><td><code>NEW_HOMES</code></td><td>Data on newly authorized housing units.</td></tr><tr><td><code>CFSEC_NEG</code></td><td>Diffusion indexes reflecting changes in organizations' operations and outlook.</td></tr><tr><td><code>US_POLICY_UNC_D</code></td><td>Daily Economic Policy Uncertainty Index based on American newspaper counts.</td></tr><tr><td><code>UK_POLICY_UNC_D</code></td><td>Daily Economic Policy Uncertainty Index based on British</td></tr><tr><td><code>CHINA_POLICY_UNC_M</code></td><td>Monthly index tracking economic policy uncertainty in China based on term frequency in Chinese newspapers.</td></tr><tr><td><code>US_MARKET_UNC_D</code></td><td>Daily index derived from term frequency analysis in American newspapers, focused on market uncertainty.</td></tr><tr><td><code>US_POLICY_VOL_M</code></td><td>Monthly tracker measuring market volatility through the lens of economic and stock market-related terms.</td></tr><tr><td><code>GLOBAL_POLICY_UNC_M</code></td><td>Monthly global economic policy uncertainty index, GDP-weighted, based on global newspaper term analysis.</td></tr><tr><td><code>US_SOVEREIGN_UNC_M</code></td><td>Categorical monthly data tracking US policy uncertainty across various domains using news article frequency.</td></tr><tr><td><code>GEO_UNC_D</code></td><td>Daily index quantifying geopolitical risk through newspaper coverage of geopolitical tensions.</td></tr><tr><td><code>GEO_UNC_M</code></td><td>Monthly index measuring geopolitical risk intensity based on media coverage of global tensions.</td></tr><tr><td><code>GEO_EQUAL_M</code></td><td>Monthly averaged geopolitical risk index across 22 countries, based on media coverage.</td></tr><tr><td><code>WEB_SEARCH_UNC_M</code></td><td>Monthly uncertainty index based on the intensity of web searches mimicking news-based approaches.</td></tr><tr><td><code>THINKTANK_UNC_M</code></td><td>Uncertainty index for 77 countries based on the frequency of 'uncertainty' in Economist Intelligence Unit reports.</td></tr></tbody></table>



### Computations

#### Custom Aggregates

We can use the inputs to come up with new aggregartes of the original input data, doing that we can come up with new indices. Here I have come up with a few new ones.&#x20;

```python
df_risks_agg = sov.compute('risk-aggregates', df=df_risks)
```

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

| Column                    | Description                                                                       |
| ------------------------- | --------------------------------------------------------------------------------- |
| VOLATILITY\_RISK          | A score calculated from market volatility indicators like ENSEMBLE and VIX.       |
| RECESSION\_PROBABILITY    | An average probability score of recession forecasted at 6, 12, and 24 months.     |
| GEOPOLITICAL\_RISK        | A score summarizing various geopolitical risk indicators.                         |
| DOMESTIC\_POLITICAL\_RISK | A composite score of US-specific political risk indicators.                       |
| BOND\_RISK                | An average score of bond market risks including credit and term spreads.          |
| ECONOMIC\_SENTIMENT       | A sentiment score based on economic indicators such as housing and vehicle sales. |
| INVESTOR\_SENTIMENT       | A score reflecting the sentiment of investors based on surveys.                   |
| CONSUMER\_SENTIMENT       | A score summarizing consumer confidence and economic outlook indicators.          |
| MANUFACTURING\_SENTIMENT  | A sentiment score derived from manufacturing sector surveys.                      |
| SERVICES\_SENTIMENT       | An index reflecting sentiment in the non-manufacturing industries.                |

#### Pandas Plots

```python
df_risks[["MARKET_RISK","BUSINESS_RISK","POLITICAL_RISK","TURING_RISK"]].tail(15400).plot()
```



####

####

####

#### Retrieve Specific Ticker Data

Get breakout data for a specific ticker such as Microsoft (MSFT):

```python
df_msft = sov.data("breakout", tickers=["MSFT"])
```

### Visualization

#### Breakout Predictions

Visualize breakout predictions using the SDK's plotting capabilities:

```python
sov.plot("breakout", chart_type="predictions", df=df_msft)
```

#### Prediction Accuracy

Assess the accuracy of breakout predictions:

```python
sov.plot("breakout", chart_type="accuracy", df=df_msft)
```

## Data Dictionary

<table><thead><tr><th width="237">Column</th><th>Description</th><th>Type</th><th>Example</th></tr></thead><tbody><tr><td><code>ticker</code></td><td>Stock ticker symbol.</td><td>object</td><td>"AAPL"</td></tr><tr><td><code>date</code></td><td>Date when the data was recorded.</td><td>datetime64[ns]</td><td>2023-09-30</td></tr><tr><td><code>target</code></td><td>Target variable for predictions.</td><td>float64</td><td>0.05</td></tr><tr><td><code>future_returns</code></td><td>Future returns of the stock.</td><td>float32</td><td>0.10</td></tr><tr><td><code>prediction</code></td><td>Predicted probability from the model.</td><td>float64</td><td>1.25</td></tr><tr><td><code>bottom_prediction</code></td><td>Lower bound of the prediction interval.</td><td>float64</td><td>1.20</td></tr><tr><td><code>top_prediction</code></td><td>Upper bound of the prediction interval.</td><td>float64</td><td>1.30</td></tr><tr><td><code>standard_deviation</code></td><td>Standard deviation of the predictions.</td><td>float64</td><td>0.02</td></tr><tr><td><code>bottom_conformal</code></td><td>Lower bound of the conformal prediction interval.</td><td>float64</td><td>1.18</td></tr><tr><td><code>top_conformal</code></td><td>Upper bound of the conformal prediction interval.</td><td>float64</td><td>1.32</td></tr><tr><td><code>slope</code></td><td>Slope derived from the rolling regression of predictions over a window.</td><td>float64</td><td>0.003</td></tr></tbody></table>

***

## **Description**



***

### Prediction Model for Price Increases

This document outlines the prediction model used to forecast stock price movements. The model employs a variety of machine learning techniques and is optimized for equity selection. With an emphasis on pricing information, it is designed to predict significant price increases with high accuracy.

### Model Description

The model is constructed using a series of Python-based machine learning algorithms, with data processing and feature engineering steps to prepare the data for analysis.

#### Data Preparation

Data is initially sourced from a BigQuery table containing historical pricing information, such as adjusted close prices and trading volume. The data is preprocessed to generate features that capture historical trends and patterns, including:

* **Return Features**: Percent changes in price and volume over specified time windows.
* **Rolling Features**: Rolling statistics (mean, standard deviation, skewness, etc.) calculated over different periods to capture short- and long-term movements.
* **Date Features**: Time-based features to account for seasonal trends and temporal patterns.
* **Target Variable**: A binary classification target indicating whether the stock price will see a significant increase (`1`) or decrease (`0`) over a given time horizon.

#### Feature Engineering

The model includes extensive feature engineering to enhance the predictive power of the training data:

* **Standardized Returns**: The return of a stock over a specified period divided by the rolling standard deviation of the return, offering a normalized measure of price movement.
* **Summary Statistics**: Aggregated metrics derived from the newly created lagged return features, providing a comprehensive view of recent price behavior.

#### Model Training

Several machine learning models are trained using the prepared dataset:

* **Calibrated Classifier**: A classification model trained on the engineered features to predict the binary target.
* **Proprietory Regressor**: A proprietory regression model is used to predict the probability of a price increase.
* **Conformal Regressor**: Used to provide calibrated confidence intervals around the predictions, offering an additional measure of uncertainty.

#### Model Usage

The model can be applied to new data to generate predictions for the likelihood of price increases. It utilizes the trained classifiers and regressors to provide both point estimates and confidence intervals for these predictions.



### Potential Use-cases

1. **Bankruptcy Prediction Analysis**: Offer insights into predicted corporate bankruptcies and identify key factors, clarifying main drivers across different cycles.
2. **Variable Impact Breakdown**: Analyze how each individual variable affects bankruptcy predictions, providing in-depth feature contribution insights.
3. **Temporal Feature Distribution Analysis**: Reveal how variables contribute to predictions over time, emphasizing key features in forecasting models.
4. **Feature Impact Visualization**: Highlights how different factors influence predictions.
5. **Correlation Discovery**: Identify stocks with similar bankruptcy probability trends, revealing correlated market behaviors.
6. **Probability Shift Overview**: Showcase changes in bankruptcy probabilities among correlated stocks, providing a comprehensive market perspective.
7. **Sentiment Inversion Analysis**: Convert bankruptcy predictions into positive sentiment indicators to gauge potential impacts on stock returns.
8. **Behavioral Similarity Mapping**: Locate stocks with similar behaviors to a selected reference, based on bankruptcy trends and PCA feature analysis.
