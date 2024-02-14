---
description: >-
  More than 80+ financial ratios calculated from financial statement and market
  data.
---

# 📬 Corporate Risk Indicators

{% hint style="info" %}
Data arrives late Friday night 11 pm - 12 am after market close US-EST time.&#x20;
{% endhint %}

`Tutorials` are the best documentation — <mark style="color:blue;">`Financial Ratio Analysis`</mark>

<table data-column-title-hidden data-view="cards"><thead><tr><th>Category</th><th>Details</th></tr></thead><tbody><tr><td><strong>Input Datasets</strong></td><td>SEC Filings, EDGAR API, Exchange Data. </td></tr><tr><td><strong>Models Used</strong></td><td>Transformations, Simple Maths</td></tr><tr><td><strong>Model Outputs</strong></td><td>Standardized Ratios</td></tr></tbody></table>

Diversified selection of ratios for factor development or bottum-up equity selection strategies.&#x20;

### Data Access

#### Financial Statement Risk

Fetch the latest index data using the SDK:

```python
from sovai import sov
df_actg_risk = sov.data("corprisk/accounting")
```

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

#### Financial Event Risk

Fetch the latest index data using the SDK:

```python
from sovai import sov
df_events_risk = sov.data("corprisk/events")
```

<figure><img src="../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

#### Misstatement Risk

Fetch the latest index data using the SDK:

```python
from sovai import sov
df_miss_risk = sov.data("corprisk/misstatement")
```

###

### Financial Risks Dictionary

<table><thead><tr><th width="224">Name</th><th width="304">Description</th><th width="114">Sentiment</th><th>Type</th></tr></thead><tbody><tr><td>piotroski_score</td><td>A score based on financial strength indicators from the Piotroski F-score</td><td>Positive</td><td>float64</td></tr><tr><td>altman_z_score</td><td>A score measuring a company's financial health and bankruptcy risk</td><td>Positive</td><td>float64</td></tr><tr><td>graham_number</td><td>A figure that measures a stock's fundamental value named after Benjamin Graham</td><td>Positive</td><td>float64</td></tr><tr><td>lynch_fair_value</td><td>An estimation of fair value using Peter Lynch's valuation method</td><td>Positive</td><td>float64</td></tr><tr><td>yacktman_frr</td><td>Yacktman's Forward Rate of Return, a measure of expected return</td><td>Positive</td><td>float64</td></tr><tr><td>ortiz_liquidity</td><td>A measure of asset liquidity relative to market assets</td><td>Positive</td><td>float64</td></tr><tr><td>tangibility</td><td>A ratio indicating the tangible assets held by a company</td><td>Positive</td><td>float64</td></tr><tr><td>age</td><td>The age of the company or asset in question</td><td>Positive</td><td>float64</td></tr><tr><td>oshaughnessy_1</td><td>A composite score based on value factors as per James O'Shaughnessy</td><td>Positive</td><td>float64</td></tr><tr><td>oshaughnessy_2</td><td>Another composite score following James O'Shaughnessy's methodology</td><td>Positive</td><td>float64</td></tr><tr><td>oshaughnessy_3</td><td>A third composite score by James O'Shaughnessy focusing on different factors</td><td>Negative</td><td>float64</td></tr><tr><td>beneish_m_score</td><td>A score to measure the probability of a firm manipulating its earnings</td><td>Negative</td><td>float64</td></tr><tr><td>erp5</td><td>A ranking system for stocks combining value and quality measures</td><td>Negative</td><td>float64</td></tr><tr><td>sloan_ratio</td><td>A ratio to identify earnings manipulation by comparing accruals to net income</td><td>Negative</td><td>float64</td></tr><tr><td>ohlson_score</td><td>A probability score of corporate financial distress</td><td>Negative</td><td>float64</td></tr><tr><td>dechow_equity_duration</td><td>A measure of the sustainability of a firm's earnings</td><td>Negative</td><td>float64</td></tr><tr><td>kaplan_zingales_index</td><td>An index measuring a company's financial constraints</td><td>Negative</td><td>float64</td></tr></tbody></table>



### Financial Event Dictionary

Some of these events are difficult to map to negative and positive sentiment, however, for calculating the average, we had to apply a mapping. Moreover, in the real table all values have been transformed into negative values.&#x20;

<table><thead><tr><th width="255">Name</th><th width="269">Description</th><th>Sentiment</th><th>Type</th></tr></thead><tbody><tr><td>average</td><td>The mean value of various indicators, scaled and ranked over a rolling period</td><td>Negative</td><td>float64</td></tr><tr><td>industryadjustedavg</td><td>Industry-adjusted average value</td><td>Negative</td><td>float64</td></tr><tr><td>accountantchange</td><td>Indicator for changes in accountant</td><td>Negative</td><td>float64</td></tr><tr><td>agreementtermination</td><td>Indicator for termination of agreements</td><td>Negative</td><td>float64</td></tr><tr><td>assetacquisitioncompletion</td><td>Indicator for completion of asset acquisition</td><td>Positive</td><td>float64</td></tr><tr><td>attorneynoticereceipt</td><td>Indicator for receipt of an attorney's notice</td><td>Negative</td><td>float64</td></tr><tr><td>bankruptcy</td><td>Indicator for bankruptcy occurrences</td><td>Negative</td><td>float64</td></tr><tr><td>controlchanges</td><td>Indicator for changes in control of the registrant</td><td>Negative</td><td>float64</td></tr><tr><td>creditenhancementchange</td><td>Indicator for changes in credit enhancement or external support</td><td>Negative</td><td>float64</td></tr><tr><td>definitiveagreement</td><td>Indicator for entry into a material definitive agreement</td><td>Positive</td><td>float64</td></tr><tr><td>delistingnotice</td><td>Indicator for notice of delisting or failure to satisfy listing rules</td><td>Negative</td><td>float64</td></tr><tr><td>directorofficerchanges</td><td>Indicator for departure of directors or certain officers</td><td>Negative</td><td>float64</td></tr><tr><td>distributionfailure</td><td>Indicator for failure to make a required distribution</td><td>Negative</td><td>float64</td></tr><tr><td>ethicsamendments</td><td>Indicator for amendments to the registrant's code of ethics</td><td>Positive</td><td>float64</td></tr><tr><td>exitcosts</td><td>Indicator for costs associated with exit or disposal activities</td><td>Negative</td><td>float64</td></tr><tr><td>financialexhibits</td><td>Indicator for financial statements and exhibits</td><td>Positive</td><td>float64</td></tr><tr><td>financialobligationcreation</td><td>Indicator for creation of a direct financial obligation</td><td>Negative</td><td>float64</td></tr><tr><td>impairments</td><td>Indicator for material impairments</td><td>Negative</td><td>float64</td></tr><tr><td>incorporationamendments</td><td>Indicator for amendments to articles of incorporation or bylaws</td><td>Negative</td><td>float64</td></tr><tr><td>minesafetyreports</td><td>Indicator for mine safety reporting</td><td>Negative</td><td>float64</td></tr><tr><td>nonreliancestatement</td><td>Indicator for non-reliance on previously issued financial statements</td><td>Negative</td><td>float64</td></tr><tr><td>obligationtriggerevents</td><td>Indicator for triggering events that affect financial obligations</td><td>Negative</td><td>float64</td></tr><tr><td>operationsresults</td><td>Indicator for results of operations and financial condition</td><td>Positive</td><td>float64</td></tr><tr><td>otherevents</td><td>Indicator for other events (ambiguous context)</td><td>Negative</td><td>float64</td></tr><tr><td>regfddisclosure</td><td>Indicator for regulation FD disclosure</td><td>Positive</td><td>float64</td></tr><tr><td>schedule13dfiling</td><td>Indicator for Schedule 13D filing</td><td>Negative</td><td>float64</td></tr><tr><td>schedule13gfiling</td><td>Indicator for Schedule 13G filing</td><td>Negative</td><td>float64</td></tr><tr><td>securitiesactupdate</td><td>Indicator for Securities Act updating disclosure</td><td>Positive</td><td>float64</td></tr><tr><td>securityholdermodifications</td><td>Indicator for material modifications to rights of security holders</td><td>Positive</td><td>float64</td></tr><tr><td>servicertrusteechange</td><td>Indicator for change of servicer or trustee</td><td>Negative</td><td>float64</td></tr><tr><td>shareholdernominations</td><td>Indicator for shareholder nominations pursuant to Exchange Act Rule 14a-11</td><td>Positive</td><td>float64</td></tr><tr><td>shellstatuschange</td><td>Indicator for change in shell company status</td><td>Negative</td><td>float64</td></tr><tr><td>tenderofferstatement</td><td>Indicator for tender offer statement</td><td>Negative</td><td>float64</td></tr><tr><td>tradingsuspension</td><td>Indicator for temporary suspension of trading</td><td>Negative</td><td>float64</td></tr><tr><td>unregisteredequitysales</td><td>Indicator for unregistered sales of equity securities</td><td>Negative</td><td>float64</td></tr><tr><td>votesubmission</td><td>Indicator for submission of matters to a vote of security holders</td><td>Negative</td><td>float64</td></tr><tr><td>acquisitions</td><td>Indicator for acquisitions</td><td>Positive</td><td>float64</td></tr><tr><td>mergers</td><td>Indicator for mergers</td><td>Positive</td><td>float64</td></tr><tr><td>spinoffs</td><td>Indicator for spin-offs</td><td>Positive</td><td>float64</td></tr><tr><td>split</td><td>Indicator for splits</td><td>Positive</td><td>float64</td></tr><tr><td>tickerchange</td><td>Indicator for ticker changes</td><td>Negative</td><td>float64</td></tr></tbody></table>



### Misstatement Dictionary

For the misstatements, all of the variables have been changed into negative indicators, so that when the company overreports the financial health and corrects it later on, that is a negative sign.&#x20;

| Name                 | Description                                                     | Sentiment | Type    |
| -------------------- | --------------------------------------------------------------- | --------- | ------- |
| cashneq              | Cash and cash equivalents                                       | Positive  | float64 |
| ppnenet              | Property, plant, and equipment, net                             | Positive  | float64 |
| sbcomp               | Stock-based compensation                                        | Negative  | float64 |
| revenue              | Total revenue                                                   | Positive  | float64 |
| retearn              | Retained earnings                                               | Positive  | float64 |
| payables             | Accounts payable                                                | Negative  | float64 |
| opinc                | Operating income                                                | Positive  | float64 |
| opex                 | Operating expenses                                              | Negative  | float64 |
| netinc               | Net income                                                      | Positive  | float64 |
| ncfo                 | Net cash flow from operating activities                         | Positive  | float64 |
| ncfi                 | Net cash flow from investing activities                         | Positive  | float64 |
| liabilitiesnc        | Non-current liabilities                                         | Negative  | float64 |
| liabilitiesc         | Current liabilities                                             | Negative  | float64 |
| intexp               | Interest expense                                                | Negative  | float64 |
| intangibles          | Intangible assets                                               | Positive  | float64 |
| fcf                  | Free cash flow                                                  | Positive  | float64 |
| ebitda               | Earnings before interest, taxes, depreciation, and amortization | Positive  | float64 |
| depamor              | Depreciation and amortization                                   | Negative  | float64 |
| deferredrev          | Deferred revenue                                                | Negative  | float64 |
| assetsnc             | Non-current assets                                              | Positive  | float64 |
| assetsc              | Current assets                                                  | Positive  | float64 |
| misstatmentper\_neg  | Proportion of negative misstatements                            | Negative  | float64 |
| misstatmentper\_pos  | Proportion of positive misstatements                            | Positive  | float64 |
| misstate\_weight     | Weighted median of misstatements                                | Mixed     | float64 |
| emptycounts          | Proportion of empty or missing data points                      | Negative  | float64 |
| misstatement\_signal | Overall signal indicating the presence of misstatements         | Mixed     | float64 |

<table><thead><tr><th width="169">Name</th><th width="361">Description</th><th>Type</th></tr></thead><tbody><tr><td>cashneq</td><td>Cash and cash equivalents</td><td>float64</td></tr><tr><td>ppnenet</td><td>Property, plant, and equipment, net</td><td>float64</td></tr><tr><td>sbcomp</td><td>Stock-based compensation</td><td>float64</td></tr><tr><td>revenue</td><td>Total revenue</td><td>float64</td></tr><tr><td>retearn</td><td>Retained earnings</td><td>float64</td></tr><tr><td>payables</td><td>Accounts payable</td><td>float64</td></tr><tr><td>opinc</td><td>Operating income</td><td>float64</td></tr><tr><td>opex</td><td>Operating expenses</td><td>float64</td></tr><tr><td>netinc</td><td>Net income</td><td>float64</td></tr><tr><td>ncfo</td><td>Net cash flow from operating activities</td><td>float64</td></tr><tr><td>ncfi</td><td>Net cash flow from investing activities</td><td>float64</td></tr><tr><td>liabilitiesnc</td><td>Non-current liabilities</td><td>float64</td></tr><tr><td>liabilitiesc</td><td>Current liabilities</td><td>float64</td></tr><tr><td>intexp</td><td>Interest expense</td><td>float64</td></tr><tr><td>intangibles</td><td>Intangible assets</td><td>float64</td></tr><tr><td>fcf</td><td>Free cash flow</td><td>float64</td></tr><tr><td>ebitda</td><td>Earnings before interest, taxes, depreciation, and amortization</td><td>float64</td></tr><tr><td>depamor</td><td>Depreciation and amortization</td><td>float64</td></tr><tr><td>deferredrev</td><td>Deferred revenue</td><td>float64</td></tr><tr><td>assetsnc</td><td>Non-current assets</td><td>float64</td></tr><tr><td>assetsc</td><td>Current assets</td><td>float64</td></tr><tr><td>average</td><td>Average of various financial indicators (context-specific)</td><td>float64</td></tr><tr><td>industryadjustedavg</td><td>Industry-adjusted average of indicators</td><td>float64</td></tr><tr><td>misstatement_pctl</td><td>Misstatement percentile based on the average of features</td><td>float64</td></tr><tr><td>misstatmentper_neg</td><td>Misstatement percentage (negative context)</td><td>float64</td></tr><tr><td>misstatmentper_pos</td><td>Misstatement percentage (positive context)</td><td>float64</td></tr></tbody></table>











***
