---
description: Chapter 7 and Chapter 11 Predictions made available to Sovai subscribers.
---

# 📬 Bankruptcy Predictions

{% hint style="info" %}
Monthly corporate bankruptcy predictions arrive the **2nd of every month**_._
{% endhint %}

`Tutorials` are the best documentation — <mark style="color:blue;">`Corporate Bankruptcy Tutorial`</mark>

<table data-view="cards" data-full-width="false"><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><strong>Input Datasets</strong></td><td>SEC Bankruptcies, Delistings, Market Data, Financial Statements</td></tr><tr><td><strong>Models Used</strong></td><td>CNN, LightGBM, RocketModel, AutoEncoder</td></tr><tr><td><strong>Model Outputs</strong></td><td>Calibrated Probabilities, Shapley Values</td></tr></tbody></table>

The Bankruptcy SDK predict the likelihood of bankruptcies in the next 6-months for US publicly listed companies using advanced machine learning models.&#x20;

With an accuracy of around 89% and ROC-AUC of 85%, these models represent the forefront of machine learning in equity selection.

## Data Access

### **Probabilities (Daily)**

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

**The model attempts to predict the likelihood of bankruptcies in the next 6-months. The likelihood that companies would go bankrupt in the next 6-months is very low. The change of this value over time can however be very revealing.**&#x20;



### **Advanced Modeling Techniques**:

* **The Boosting Model**: Utilizes LightGBM technology, integrating both fundamental and market data for accurate predictions.
* **The Convolutional Model**: Employs a Convolutional Neural Network (CNN) for efficient pattern recognition in market trends.
* **The Rocket Model**: Specializes in time series data, using random convolutional kernels for effective classification and forecasting.
* **The Encoder Model**: Combines LightGBM with CNN autoencoders, enhancing feature engineering for more precise predictions.
* **The Fundamental Model**: Focuses solely on fundamental data via LightGBM, without extra architectural layers, for straightforward financial analysis.



### Potential Use-cases

1. **Bankruptcy Prediction Analysis**: Offer insights into predicted corporate bankruptcies and identify key factors, clarifying main drivers across different cycles.
2. **Variable Impact Breakdown**: Analyze how each individual variable affects bankruptcy predictions, providing in-depth feature contribution insights.
3. **Temporal Feature Distribution Analysis**: Reveal how variables contribute to predictions over time, emphasizing key features in forecasting models.
4. **Feature Impact Visualization**: Highlights how different factors influence predictions.
5. **Correlation Discovery**: Identify stocks with similar bankruptcy probability trends, revealing correlated market behaviors.
6. **Probability Shift Overview**: Showcase changes in bankruptcy probabilities among correlated stocks, providing a comprehensive market perspective.
7. **Sentiment Inversion Analysis**: Convert bankruptcy predictions into positive sentiment indicators to gauge potential impacts on stock returns.
8. **Behavioral Similarity Mapping**: Locate stocks with similar behaviors to a selected reference, based on bankruptcy trends and PCA feature analysis.