---
description: >-
  Chapter 7 and Chapter 11 bankruptcy predictions made available to Sovai
  subscribers.
---

# 📬 Bankruptcy Predictions

{% hint style="info" %}
Monthly corporate bankruptcy predictions arrive the **2nd of every month**_._
{% endhint %}

<table data-view="cards" data-full-width="false"><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><strong>Input Datasets</strong></td><td>SEC Bankruptcies, Delistings, Market Data, Financial Statements</td></tr><tr><td><strong>Models Used</strong></td><td>CNN, LightGBM, RocketModel, AutoEncoder</td></tr><tr><td><strong>Model Outputs</strong></td><td>Calibrated Probabilities, Shapley Values</td></tr></tbody></table>



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

###

### Probabilities (Daily)

```python
import sovai as sov
df_bankrupt = sov.data('bankruptcy/daily', tickers=["MSFT","TSLA","META"])
```

The daily probabilities are experimental, and have a very short history of just a couple of months.&#x20;

###

### Feature Importance (Shapleys)

```python
import sovai as sov
df_importance = sov.data('bankruptcy/shapleys', tickers=["MSFT","TSLA","META"])
```





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
