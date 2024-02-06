---
description: Quick start guide to Sovai
---

# 🚀 Quickstart

To keep the software experience clean, there are only four code submodules, [`data`](quickstart.md#download-datasets) ,[`plot`](quickstart.md#visualizing-data), [`report`](quickstart.md#running-reports), and [`compute`](quickstart.md#running-calculations).

## Introduction

* [Download Datasets](quickstart.md#download-datasets)
* [Visualizing Data](quickstart.md#visualizing-data)
* [Running Reports](quickstart.md#running-reports)
* [Running Calculations](quickstart.md#running-calculations)
* [Performing Studies](quickstart.md#performing-studies)

## Download Datasets

You will be unable to access **Sovai Datasets** without authenticating your requests. There are three ways to authenticate your requests.

```python
import sovai as sov

# There are three ways how to login to the API

# 1. Configuration API connection
sov.ApiConfig.token = "super_secret_token"
sv.ApiConfig.base_url = "https://google.com"

# 2. Read token from .env file e.g API_TOKEN=super_secret_token
sov.read_key('.env')

# 3. The Basic authentication method
sov.basic_auth("test@test.com", "super_strong_password")

# And then continue working with get some data from API and manipulating them
```

Once this is done, downloading datasets becomes as easy as using the following commands.

```python
# Retrieve data
gs_df = sov.data("bankruptcy/monthly")
```

We access  tables "corprisk", "breakout", "news", "institutional", "insider", "wikipedia", "spending", "market", "accounting", and many more from the **data repository**.&#x20;



## Visualizing Data

### Unique Plots

Certain datasets have unique visualization that you access from their respective pages.&#x20;

```python
sov.plot('bankruptcy', chart_type='compare')
```

In these scenarios, you would directly call up the dataset, in this case **'bankruptcy'** and the associated **chart\_type.**&#x20;

### Universal Plots

Some visualizations are universally applicable to multiple datasets. We could also rely heavily on the built-in plots in pandas.&#x20;

```python
df_risks = sov.data("risks")
df_risks[["MARKET_RISK","TURING_RISK"]].tail(15400).plot()
```



## Running Reports

Another option is for us to run reports on the dataset, which largely allows us to explore the dataset.&#x20;

```python
sov.report("corprisk/accounting",report_type="sector-top")
```

We can also make use of pandas' built in functions to run queries on top of the data.&#x20;

```python
df_risks.query("ticker == 'CGRNQ'")
```



## Running Calculations

Sovai simplifies many calculations that would otherwise take many lines to compute. We also write the code to be as fast as possible .

Here is an example of one line of code needed to calculate Principal Components.&#x20;

```python
pca_df = sov.compute("pca",df_risks)
```

This is an example of calculating a distance-matrix on a dataset.

```python
df_distance = sov.compute('distance-matrix', on="ticker", df=df_risks)
```



## Performing Studies

Studies include more advanced methods than calculations, and currently include software for portfolio-optimization, and time-series forecasts.&#x20;

### Forecasting

```python
df_future = sov.forecast(df_risks, horizon=12)
```

### Portfolio Optimization

```
df_future = sov.optimize(df_positions, scale="week")
```

Our studies is a growing area of research and we will keep expanding and enchancing our offering in this space.&#x20;
