---
description: >-
  A dataset with daily updated predictions of price breaking upwards for US
  Equities.
---

# 📬 Price Breakout Prediction

{% hint style="info" %}
Daily predictions arrive between 11 pm - 4 am before market open in the US.
{% endhint %}

`Tutorials` are the best documentation — <mark style="color:blue;">`Price Breakout Prediction`</mark>

<table data-column-title-hidden data-view="cards"><thead><tr><th>Category</th><th>Details</th></tr></thead><tbody><tr><td>Input Datasets</td><td>Historical Stock Prices, Trading Volumes, Technical Indicators</td></tr><tr><td>Models Used</td><td>Classification Algorithms, Regression Models, Conformal Predictors</td></tr><tr><td>Model Outputs</td><td>Price Movement Predictions, Probability Scores, Confidence Intervals</td></tr></tbody></table>

The Breakout SDK predicts the probabillty of price increases over the next 30-60 days for US Equities.&#x20;

The accuracy is around 65% and ROC-AUC of 68%, it is one of the strongest price breakout models on the market.&#x20;

## Data Access

### **Probabilities (Monthly)**

**Specific Tickers**

```python
import sovai as sov
df_bankrupt = sov.data('bankruptcy', tickers=["MSFT","TSLA","META"])
```

**Specific Dates**

```python
import sovai as sov
df_bankrupt = sov.data('bankruptcy', start_date="2017-01-03", tickers=["MSFT"])
```

**All Data**

```python
import sovai as sov
df_bankrupt = sov.data('bankruptcy')
```

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

### Probabilities (Daily)

```python
import sovai as sov
df_bankrupt = sov.data('bankruptcy/daily', tickers=["MSFT","TSLA","META"])
```

The daily probabilities are experimental, and have a very short history of just a couple of months.&#x20;



### Feature Importance (Shapleys)

```python
import sovai as sov
df_importance = sov.data('bankruptcy/shapleys', tickers=["MSFT","TSLA","META"])
```



## Data Dictionary

<table><thead><tr><th width="295">Name</th><th width="246">Description</th><th width="89">Type</th><th>Example</th></tr></thead><tbody><tr><td><code>ticker</code></td><td>Stock ticker symbol.</td><td>TEXT</td><td>"TSLA"</td></tr><tr><td><code>date</code></td><td>Record date.</td><td>DATE</td><td>2023-09-30</td></tr><tr><td><code>probability_light</code></td><td>LightGBM Boosting Model prediction.</td><td>FLOAT</td><td>1.46636</td></tr><tr><td><code>probability_convolution</code></td><td>CNN Model prediction for bankruptcies</td><td>FLOAT</td><td>0.135975</td></tr><tr><td><code>probability_rocket</code></td><td>Rocket Model prediction for time series classification</td><td>FLOAT</td><td>0.02514</td></tr><tr><td><code>probability_encoder</code></td><td>LightGBM and CNN autoencoders Model prediction.</td><td>FLOAT</td><td>0.587817</td></tr><tr><td><code>probability_fundamental</code></td><td>Prediction using accounting data only.</td><td>FLOAT</td><td>1.26148</td></tr><tr><td><code>probability</code></td><td>Average probability across models.</td><td>FLOAT</td><td>0.553823</td></tr><tr><td><code>sans_market</code></td><td>Fundamental prediction adjusted for market predictions.</td><td>FLOAT</td><td>-0.20488</td></tr><tr><td><code>volatility</code></td><td>Variability of model predictions.</td><td>FLOAT</td><td>0.62934</td></tr><tr><td><code>multiplier</code></td><td>Coefficient for model prediction calibration.</td><td>FLOAT</td><td>1.951868</td></tr><tr><td><code>version</code></td><td>Model/data record version.</td><td>INT</td><td>20240201</td></tr></tbody></table>

## Custom Analytics

Every dataset has some custom Reports, Plots, and Computations that has been preloaded for quick execution and vizualisation.

***

### Reports

Generate insightful summary reports to understand bankruptcy trends:

*   **Top Sector Predictions:**

    ```python
    sov.report("bankruptcy", report_type="sector-top")
    ```

    This report filters sectors with the highest bankruptcy prediction scores.
*   **Monthly Sector Change Summary:**

    ```python
    sov.report("bankruptcy", report_type="sector-change")
    ```

    Track monthly prediction changes across different sectors.

### Plots

Visualize the data with a variety of chart types to enhance understanding:

*   **Bankruptcy Comparison Chart:**

    ```python
    sov.plot('bankruptcy', chart_type='compare')
    ```

    Compare bankruptcy probabilities across different tickers.
*   **Feature Importance Over Time:**

    ```python
    sov.plot("bankruptcy", chart_type="shapley", tickers=["Ticker"])
    ```

    Examine how feature importance values evolve over time.
*   **Bankruptcy vs. Security Price Chart:**

    ```python
    sov.plot("bankruptcy", chart_type="line", tickers=["Ticker"])
    ```

    Analyze the relationship between bankruptcy probabilities and stock prices.
*   **PCA Similarity Plot:**

    ```python
    sov.plot("bankruptcy", chart_type="pca", tickers=["Ticker"])
    ```

    Explore the principal component analysis to identify similar tickers.
*   **Correlation Plot:**

    ```python
    sov.plot("bankruptcy", chart_type="similar", tickers=["Ticker"])
    ```

    Discover correlated stocks based on bankruptcy risk profiles.

### Computations

Leverage advanced computational tools for deeper analysis:

*   **Distance Matrix:**

    ```python
    sov.compute('distance-matrix', on="attribute", df=dataframe)
    ```

    Assess the similarity between entities based on selected attributes.
*   **Percentile Calculation:**

    ```python
    sov.compute('percentile', on="attribute", df=dataframe)
    ```

    Calculate the relative standing of values within a dataset.
*   **Feature Mapping:**

    ```python
    sov.compute('map-accounting-features', df=dataframe)
    ```

    Map accounting features to standardized metrics.
*   **PCA Calculation:**

    ```python
    sov.compute('pca', df=dataframe)
    ```

    Perform principal component analysis for dimensionality reduction.

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
