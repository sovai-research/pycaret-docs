---
description: >-
  Here we develop three tables to develop a final score of corporate risk to US
  equities. More than 100+ institutional trading variables.
---

# 🗣️ Insider Flow Prediction

{% hint style="info" %}
Data is updated quarterly as data arrives after market close US-EST time.&#x20;
{% endhint %}

`Tutorials` are the best documentation — <mark style="color:blue;">`Financial Ratio Analysis`</mark>

<table data-column-title-hidden data-view="cards"><thead><tr><th>Category</th><th>Details</th></tr></thead><tbody><tr><td><strong>Input Datasets</strong></td><td>13F Filings, Market Data</td></tr><tr><td><strong>Models Used</strong></td><td>Simple Calculations, Aggregations</td></tr><tr><td><strong>Model Outputs</strong></td><td>Standardized Ratios</td></tr></tbody></table>

Diversified selection of ratios for factor development or bottum-up equity selection strategies.&#x20;

## Data Access

#### Institutional Trading Data

This data is around 1GB if you download the entire dataset.

```python
from sovai import sov
df_institute = sov.data("institutional/trading")
```

<figure><img src="../.gitbook/assets/image (19) (1).png" alt=""><figcaption></figcaption></figure>

#### Filtered Dataset

```python
from sovai import sov
df_institute = sov.data("institutional/trading", start_date="2004-04-30", tickers=["MSFT"])
```



## Data Dictionary

| Column Name                                                  | Description                                                                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------- |
| `ticker`                                                     | Stock ticker symbol associated with the transaction.                                                                |
| `date`                                                       | Date when the transaction was reported.                                                                             |
| `market_impact`                                              | Sum of the effect of all transactions on the market value.                                                          |
| `market_impact_percentage`                                   | Mean impact of transactions as a percentage of the transaction value.                                               |
| `percentage_shares`                                          | Average portion of shares transacted relative to total shares outstanding.                                          |
| `transaction_value`                                          | Total value of the transactions.                                                                                    |
| `transaction_shares`                                         | Total number of shares involved in the transactions.                                                                |
| `days_to_file`                                               | Average number of days between the transaction and filing dates.                                                    |
| `row_number`                                                 | Count of transactions within the dataset.                                                                           |
| `cumulative_market_impact`                                   | Aggregate impact of transactions over time (not directly computed in the provided code but implied).                |
| `relative_transaction_size`                                  | Size of a transaction relative to other transactions, combining absolute ratios of shares and values.               |
| `holding_period`                                             | Average time between the acquisition and sale of stock.                                                             |
| `sale_to_purchase_ratio`                                     | Ratio of the sum of sales to purchases by absolute value.                                                           |
| `holding_period_pert`                                        | Perturbation or change in holding period (calculated as a percentage change or variation).                          |
| `sale_to_purchase_ratio_pert`                                | Variability or percentage change in the sale-to-purchase ratio.                                                     |
| `derivative_nonderivative_value_abs_ratio`                   | Absolute ratio comparing values of derivative and non-derivative transactions.                                      |
| `long_term_alignment_ratio_relativesize_abs_ratio`           | Ratio of long-term alignment (options granted) to relative transaction size.                                        |
| `relative_transaction_size_pert`                             | Variability in the size of a transaction relative to others.                                                        |
| `derivative_nonderivative_impact_abs_ratio`                  | Absolute ratio of market impact between derivative and non-derivative transactions.                                 |
| `tenpercent_nintypercent_impactperc_net_ratio`               | Net ratio of market impact percentage between entities owning ten percent and others.                               |
| `none_to_manager_shares_net_ratio`                           | Net ratio of shares held by non-managers to managers.                                                               |
| `tenpercent_nintypercent_percshares_abs_ratio`               | Absolute ratio of percentage shares held by ten percent owners to others.                                           |
| `direct_indirect_value_net_ratio_pert`                       | Variability in the net ratio of transaction values between direct and indirect ownership.                           |
| `direct_indirect_insiderscore_abs_ratio`                     | Absolute ratio of insider scores for direct versus indirect transactions.                                           |
| `director_officer_impactperc_net_ratio`                      | Net ratio of market impact percentage between directors and officers.                                               |
| `director_officer_shares_net_ratio`                          | Net ratio of shares held by directors to officers.                                                                  |
| `director_officer_occurrences_abs_ratio`                     | Absolute ratio of transaction occurrences between directors and officers.                                           |
| `both_to_all_value_net_ratio`                                | Net ratio of transaction values for individuals with dual roles (both director and officer) compared to all others. |
| `both_to_all_percshares_abs_ratio`                           | Absolute ratio of percentage shares held by individuals with dual roles compared to all others.                     |
| `none_to_manager_percshares_abs_ratio`                       | Absolute ratio of percentage shares held by non-managers to managers.                                               |
| `sale_purchase_ratio_impactperc_abs_ratio_pert`              | Variability in the absolute ratio of market impact percentage between sales and purchases.                          |
| `sale_purchase_ratio_insiderscore_abs_ratio`                 | Absolute ratio of insider scores between sales and purchases.                                                       |
| `willing_acquisitions_ratio_occurrences_abs_ratio`           | Absolute ratio of occurrences of willing acquisitions compared to other transaction types.                          |
| `liquidity_situation_ratio_impact_abs_ratio`                 | Absolute ratio of market impact for transactions related to liquidity situations.                                   |
| `liquidity_situation_ratio_percshares_abs_ratio`             | Absolute ratio of percentage shares involved in liquidity-related transactions.                                     |
| `sale_press_impactperc_director_to_officer_net_ratio_pert`   | Variability in net ratio of market impact percentage from sales pressure between directors and officers.            |
| `sale_press_shares_director_to_officer_net_ratio_pert`       | Variability in net ratio of shares involved in sales pressure between directors and officers.                       |
| `sale_press_impactperc_director_to_officer_abs_ratio_pert`   | Variability in the absolute ratio of market impact percentage from sales pressure between directors and officers.   |
| `sale_press_value_director_to_officer_abs_ratio`             | Absolute ratio of transaction values under sales pressure from directors to officers.                               |
| `sale_press_impact_ten_ninety_net_ratio`                     | Net ratio of market impact for transactions involving top ten percent owners versus others.                         |
| `sale_press_percshares_ten_ninety_net_ratio`                 | Net ratio of percentage shares involved in transactions for top ten percent owners versus others.                   |
| `sale_press_impact_ten_ninety_abs_ratio`                     | Absolute ratio of market impact for transactions involving top ten percent owners versus others.                    |
| `sale_press_insiderscore_ten_ninety_abs_ratio`               | Absolute ratio of insider scores for transactions involving top ten percent owners versus others.                   |
| `sale_press_impact_direct_to_indirect_net_ratio`             | Net ratio of market impact between direct and indirect sales pressure.                                              |
| `sale_press_percshares_direct_to_indirect_net_ratio_pert`    | Variability in net ratio of percentage shares under direct versus indirect sales pressure.                          |
| `sale_press_impactperc_direct_to_indirect_abs_ratio_pert`    | Variability in the absolute ratio of market impact percentage under direct versus indirect sales pressure.          |
| `sale_press_relativesize_direct_to_indirect_abs_ratio`       | Absolute ratio of relative transaction size under direct versus indirect sales pressure.                            |
| `row_number_pert`                                            | Variability or percentage change in the count of transactions.                                                      |
| `derivative_nonderivative_value_net_ratio_pert`              | Variability in the net ratio of values between derivative and non-derivative transactions.                          |
| `derivative_nonderivative_occurrences_abs_ratio_pert`        | Variability in the absolute ratio of occurrences between derivative and non-derivative transactions.                |
| `tenpercent_nintypercent_impact_net_ratio_pert`              | Variability in net ratio of market impact between ten percent owners and others.                                    |
| `tenpercent_nintypercent_percshares_net_ratio_pert`          | Variability in net ratio of percentage shares between ten percent owners and others.                                |
| `tenpercent_nintypercent_value_net_ratio_pert`               | Variability in net ratio of transaction values between ten percent owners and others.                               |
| `tenpercent_nintypercent_percshares_abs_ratio_pert`          | Variability in absolute ratio of percentage shares between ten percent owners and others.                           |
| `direct_indirect_percshares_abs_ratio_pert`                  | Variability in absolute ratio of percentage shares between direct and indirect ownership.                           |
| `director_officer_impact_net_ratio_pert`                     | Variability in net ratio of market impact between directors and officers.                                           |
| `director_officer_percshares_abs_ratio_pert`                 | Variability in absolute ratio of percentage shares between directors and officers.                                  |
| `both_to_all_impact_net_ratio_pert`                          | Variability in net ratio of market impact between dual-role individuals and others.                                 |
| `both_to_all_percshares_abs_ratio_pert`                      | Variability in absolute ratio of percentage shares between dual-role individuals and others.                        |
| `none_to_manager_percshares_abs_ratio_pert`                  | Variability in absolute ratio of percentage shares between non-managers and managers.                               |
| `sale_purchase_ratio_value_abs_ratio_pert`                   | Variability in absolute ratio of transaction values between sales and purchases.                                    |
| `willing_acquisitions_ratio_occurrences_abs_ratio_pert`      | Variability in absolute ratio of occurrences in willing acquisitions.                                               |
| `long_term_alignment_ratio_occurrences_abs_ratio_pert`       | Variability in absolute ratio of occurrences related to long-term alignment transactions.                           |
| `liquidity_situation_ratio_value_abs_ratio_pert`             | Variability in absolute ratio of transaction values in liquidity situations.                                        |
| `sale_press_relativesize_director_to_officer_abs_ratio_pert` | Variability in absolute ratio of relative transaction size under director to officer sales pressure.                |
| `sale_press_value_ten_ninety_net_ratio_pert`                 | Variability in net ratio of transaction values for top ten percent owners versus others.                            |
| `sale_press_impact_ten_ninety_abs_ratio_pert`                | Variability in absolute ratio of market impact for top ten percent owners versus others.                            |
| `sale_press_occurrences_ten_ninety_abs_ratio_pert`           | Variability in absolute ratio of occurrences for top ten percent owners versus others.                              |
| `sale_press_impact_direct_to_indirect_net_ratio_pert`        | Variability in net ratio of market impact under direct versus indirect sales pressure.                              |
| `sale_press_occurrences_direct_to_indirect_abs_ratio_pert`   | Variability in absolute ratio of occurrences under direct versus indirect sales pressure.                           |
| `flow_prediction`                                            | Predicted transaction flow based on analysis (not directly computed in the provided code but implied).              |

## Institutional Investment  Analysis

This dataset provides a comprehensive analysis of institutional investment behaviors, strategies, and portfolio dynamics. It covers various aspects like fund ratios, growth metrics, derivative concentrations, shareholder dynamics, and more. The data is designed to assist professional investors in understanding market trends, evaluating investment strategies, and making informed decisions.



### Data Applications

* **Market Trend Analysis:** Understand broad market trends by analyzing growth metrics and standard deviations.
* **Risk Assessment:** Evaluate the risk profiles of different funds and strategies using volatility and diversification metrics.
* **Strategy Evaluation:** Assess and compare the effectiveness of different investment strategies.
* **Investment Decision Making:** Utilize historical data and flow metrics to make informed investment decisions.

### Feature Descriptions

1. **Standard Deviation Metrics (Columns 0-38)**
   * **Purpose:** These metrics provide insights into the volatility and risk associated with various investment strategies and portfolio compositions.
   * **Usage:** Investors can use these metrics to assess the risk profile of different funds and compare the stability of their investment strategies.
2. **Growth Metrics (Columns 75-79)**
   * **Purpose:** These metrics track the growth or decline in the value of investments, the number of shareholders, and their share value over time.
   * **Usage:** Useful for identifying trends in investment preferences and shareholder behaviors.
3. **Diversification Score (Column 80)**
   * **Purpose:** Indicates the level of diversification in a portfolio based on different types of investments.
   * **Usage:** Investors can evaluate the risk mitigation strategies of different funds based on their diversification scores.
4. **Derivative and Put-Call Metrics (Columns 81-88)**
   * **Purpose:** Provide insights into the use of derivatives and options in investment strategies.
   * **Usage:** These metrics help in understanding the risk appetite and hedging strategies of investors.
5. **Historical Highs and Debt-Equity Ratio (Columns 90-94)**
   * **Purpose:** Offers a historical perspective on share values and assesses the leverage used by funds.
   * **Usage:** Useful for long-term investment analysis and understanding the use of debt in investment strategies.
6. **Allocation Pressure and Flow Metrics (Columns 96-107)**
   * **Purpose:** These metrics assess the inflows and outflows from funds, alongside the allocation pressure on investments.
   * **Usage:** Essential for understanding market liquidity, investor sentiment, and pressure on asset allocation.
7. **Overloaded Indicators (Columns 108-109)**
   * **Purpose:** Indicate high concentrations in derivatives and puts.
   * **Usage:** Investors can gauge the level of speculation and potential overexposure to certain investment instruments.

###







***
