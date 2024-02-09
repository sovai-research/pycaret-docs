---
description: >-
  Use this indicator to understand the trajectory of global risks as perceived
  by investors.
---

# 📬 Accounting Data

{% hint style="info" %}
Daily index arrive between 11 pm - 4 am before market open in the US.
{% endhint %}

`Tutorials` are the best documentation — <mark style="color:blue;">`Business, Political, and Market Risk`</mark>

<table data-column-title-hidden data-view="cards"><thead><tr><th>Category</th><th>Details</th></tr></thead><tbody><tr><td>Input Datasets</td><td>SEC Filings, EDGAR API, Raw XBRL. </td></tr><tr><td>Models Used</td><td>Imputation Models, Validation  Against  Commerical Dataset</td></tr><tr><td>Model Outputs</td><td>Monthly Accounting Values</td></tr></tbody></table>

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

### Data Dictionary

<table><thead><tr><th width="176">name</th><th width="318">description</th><th width="130">domain</th><th width="140">characteristic</th></tr></thead><tbody><tr><td>working_capital</td><td>Working capital is the net amount of [current_assets] minus [current_liabilities], giving an indication of the short-term financial health of a company.</td><td>Metrics</td><td>Assets</td></tr><tr><td>ticker</td><td>A ticker symbol, often referred to as a stock symbol, is a unique [entity] that identifies a publicly traded security in financial markets</td><td>Entity</td><td>Entity</td></tr><tr><td>tax_liabilities</td><td>On the [balance sheet], this line item represents the total amount of tax obligations due, included within [total_liabilities], that the company is responsible for paying</td><td>Balance Sheet</td><td>Liabilities</td></tr><tr><td>tax_expenses</td><td>This represents the sum of current and deferred income tax expenses related to ongoing operations, as reported on the [income statement]. It reflects the company's tax liabilities for the period.</td><td>Income Statement</td><td>Expense</td></tr><tr><td>tax_assets</td><td>Tax assets, listed on the [balance sheet], include all tax-related receivables and potential tax benefits that are recognized as part of [total_assets].</td><td>Balance Sheet</td><td>Assets</td></tr><tr><td>tangible_assets</td><td>The value of a company's physical assets, or [tangible_assets], is calculated by subtracting [intangible_assets] from [total_assets], as indicated in [metrics].</td><td>Metrics</td><td>Assets</td></tr><tr><td>selling_general_admin_expenses</td><td>This [income statement] entry sums up all costs associated with selling the company's products and managing its operations, excluding production costs. It includes both direct selling expenses and broader administrative costs.</td><td>Income Statement</td><td>Expense</td></tr><tr><td>stock_based_compensation</td><td>This item on the [cash flow statement] reflects compensation given to employees in the form of equity or options, which is considered noncash and therefore added back to net cash from operating activities.</td><td>Cash Flow Statement</td><td>Cash Flow</td></tr><tr><td>research_development_expenses</td><td>This [income statement] line item tallies up all expenses associated with the development of new products or services, reflecting a company's investment in innovation.</td><td>Income Statement</td><td>Expense</td></tr><tr><td>revenue_usd</td><td>This [income statement] figure represents [total_revenue] converted into USD, using the [forex_usd] exchange rate, to standardize international revenue figures.</td><td>Income Statement</td><td>Income</td></tr><tr><td>total_revenue</td><td>The total amount recognized from providing goods and services, as seen on the [income statement], it's a fundamental gauge of the company's financial performance.</td><td>Income Statement</td><td>Income</td></tr><tr><td>retained_earnings</td><td>[balance sheet] Represents the cumulative earnings or deficit that an entity has retained over time as part of [total_equity]. This may be reported annually for some entities.</td><td>Balance Sheet</td><td>Equity</td></tr><tr><td>accounts_receivable</td><td>[balance sheet] Includes all trade and non-trade receivables as part of [total_assets], signifying amounts owed to the entity that are expected to be collected.</td><td>Balance Sheet</td><td>Assets</td></tr><tr><td>preferred_dividends</td><td>[income statement] Reflects dividends paid to preferred stockholders, deducted from [net_income] to determine the earnings available to common stockholders.</td><td>Income Statement</td><td>Expense</td></tr><tr><td>property_plant_equipment_net</td><td>[balance sheet] The net value of a company's investment in physical assets used in operations, net of depreciation and including Operating Right of Use Assets.</td><td>Balance Sheet</td><td>Assets</td></tr><tr><td>accounts_payable</td><td>[balance sheet] Represents amounts the company owes to suppliers and creditors, forming part of [total_liabilities].</td><td>Balance Sheet</td><td>Liabilities</td></tr><tr><td>operating_income</td><td>[income statement] Shows a company's earnings from core operations, derived as [gross_profit] minus [operating_expenses], excluding [interest_expense] and [tax_expenses].</td><td>Income Statement</td><td>Income</td></tr><tr><td>operating_expenses</td><td>[income statement] Encompasses all costs related to the day-to-day functioning of the business, excluding costs directly tied to production ([cost_of_revenue]).</td><td>Income Statement</td><td>Expense</td></tr><tr><td>net_income_non_controlling_int</td><td>[income statement] Reflects the share of earnings allocated to minority shareholders, deducted from [consolidated_income] to arrive at [net_income].</td><td>Income Statement</td><td>Income</td></tr><tr><td>net_income_discontinued_ops</td><td>[income statement] Represents the financial impact of ceasing operations or disposing of a part of the business, shown separately from ongoing operations.</td><td>Income Statement</td><td>Income</td></tr><tr><td>net_income_common_stock_usd</td><td>[income statement] The portion of [net_income_common_stock] presented in USD, converted using [forex_usd].</td><td>Income Statement</td><td>Income</td></tr><tr><td>net_income_common_stock</td><td>[income statement] The total earnings attributable to common shareholders, which may differ from [net_income] due to [preferred_dividends].</td><td>Income Statement</td><td>Income</td></tr><tr><td>net_income</td><td>[income statement] The total earnings or losses for the period attributable to the parent company, after accounting for non-controlling interests and before preferred dividends.</td><td>Income Statement</td><td>Income</td></tr><tr><td>net_cash_flow_fx</td><td>[cash flow statement] Reflects the impact of foreign exchange rate movements on the company's cash and cash equivalents held in different currencies.</td><td>Cash Flow Statement</td><td>Cash Flow</td></tr><tr><td>net_cash_flow_operating</td><td>[cash flow statement] Represents the cash a company generates from its ongoing, regular business activities.</td><td>Cash Flow Statement</td><td>Cash Flow</td></tr><tr><td>net_cash_acquisitions_disposals</td><td>[cash flow statement] Details the cash transactions involved in the company's investment acquisitions and disposals.</td><td>Cash Flow Statement</td><td>Cash Flow</td></tr><tr><td>net_cash_flow_investing</td><td>[cash flow statement] Reflects the cash transactions related to a company's investment activities within [net_cash_flow], including capital expenditures, acquisitions, and disposals.</td><td>Cash Flow Statement</td><td>Cash Flow</td></tr><tr><td>net_cash_flow_financing</td><td>[cash flow statement] Indicates the cash movements from financing activities within [net_cash_flow], including equity transactions, debt servicing, and dividends.</td><td>Cash Flow Statement</td><td>Cash Flow</td></tr><tr><td>net_cash_flow_dividends</td><td>[cash flow statement] Part of [net_cash_flow_financing], this represents the cash distributed to shareholders as dividends.</td><td>Cash Flow Statement</td><td>Cash Flow</td></tr><tr><td>net_cash_flow_debt</td><td>[cash flow statement] Represents the net cash from the issuance and repayment of debt within [net_cash_flow_financing].</td><td>Cash Flow Statement</td><td>Cash Flow</td></tr><tr><td>net_cash_flow_common</td><td>[cash flow statement] Details the cash changes from the sale or purchase of equity within [net_cash_flow_financing].</td><td>Cash Flow Statement</td><td>Cash Flow</td></tr><tr><td>net_cash_flow_business</td><td>[cash flow statement] Describes the net cash impact of buying or selling business units within [net_cash_flow_investing].</td><td>Cash Flow Statement</td><td>Cash Flow</td></tr><tr><td>net_cash_flow</td><td>[cash flow statement] Summarizes the total change in cash and equivalents, accounting for operational, investment, and financial cash flows, as well as foreign exchange effects.</td><td>Cash Flow Statement</td><td>Cash Flow</td></tr><tr><td>non_current_liabilities</td><td>[balance sheet] Represents long-term obligations of the company, which are not due within the next 12 months.</td><td>Balance Sheet</td><td>Liabilities</td></tr><tr><td>current_liabilities</td><td>[balance sheet] Represents obligations of the company due within the next 12 months.</td><td>Balance Sheet</td><td>Liabilities</td></tr><tr><td>total_liabilities</td><td>[balance sheet] The aggregate of all debts and financial obligations due by the company at any point in time.</td><td>Balance Sheet</td><td>Liabilities</td></tr><tr><td>non_current_investments</td><td>[balance sheet] Long-term investments not expected to be liquidated within the next year.</td><td>Balance Sheet</td><td>Assets</td></tr><tr><td>current_investments</td><td>[balance sheet] Short-term investments expected to be liquidated or used within one year.</td><td>Balance Sheet</td><td>Assets</td></tr><tr><td>total_investments</td><td>[balance sheet] Sum of all investments, both marketable securities and loans, reflecting a company's investment holdings.</td><td>Balance Sheet</td><td>Assets</td></tr><tr><td>inventory_amount</td><td>[balance sheet] Value of the company's stock of goods and materials held to be sold or used in production.</td><td>Balance Sheet</td><td>Assets</td></tr><tr><td>invested_capital</td><td>[metrics] Total money invested in a company for generating returns, not considering current obligations and liquid assets.</td><td>Metrics</td><td>Equity</td></tr><tr><td>interest_expense</td><td>[income statement] The total cost incurred by the company for the use of borrowed funds.</td><td>Income Statement</td><td>Expense</td></tr><tr><td>intangible_assets</td><td>[balance sheet] The net worth of non-physical assets like patents and copyrights held by the company.</td><td>Balance Sheet</td><td>Assets</td></tr><tr><td>gross_profit</td><td>[income statement] The profit a company makes after subtracting the costs associated with making and selling its products.</td><td>Income Statement</td><td>Income</td></tr><tr><td>free_cash_flow</td><td>[metrics] An important performance indicator that shows how much cash is generated from operations after subtracting capital expenditures.</td><td>Metrics</td><td>Cash Flow</td></tr><tr><td>enterprise_value</td><td>[metrics] The total valuation of a company, including its equity, debt, and cash holdings.</td><td>Metrics</td><td>Valuation</td></tr><tr><td>equity_usd</td><td>[balance sheet] The company's total equity, converted into USD using the appropriate foreign exchange rate.</td><td>Balance Sheet</td><td>Equity</td></tr><tr><td>total_equity</td><td>[balance sheet] The net value attributable to the parent company, including equity and all receivables from related parties.</td><td>Balance Sheet</td><td>Equity</td></tr><tr><td>earnings_before_tax</td><td>[metrics] The company's earnings calculated before any tax expenses are deducted.</td><td>Metrics</td><td>Profitability</td></tr><tr><td>ebit_usd</td><td>[income statement] The company's earnings before interest and taxes, reported in USD and adjusted for exchange rates.</td><td>Income Statement</td><td>Income</td></tr><tr><td>ebitda</td><td>[metrics] A common profitability measure excluding the non-cash expenses of depreciation and amortization from [ebit].</td><td>Metrics</td><td>Profitability</td></tr><tr><td>ebit</td><td>[income statement] The profit a company makes after all expenses except for interest and taxes have been subtracted from [net_income].</td><td>Income Statement</td><td>Income</td></tr><tr><td>bank_deposits</td><td>[balance sheet] The total of all customer deposits and other types of bank-held liabilities.</td><td>Balance Sheet</td><td>Liabilities</td></tr><tr><td>depreciation_amortization</td><td>[cash flow statement] The total non-cash expenses for asset depreciation, amortization, and accretion recognized during the period.</td><td>Cash Flow Statement</td><td>Cash Flow</td></tr><tr><td>deferred_revenue</td><td>[balance sheet] Income that has been received but not yet earned, and thus not recognized as revenue.</td><td>Balance Sheet</td><td>Liabilities</td></tr><tr><td>debt_usd</td><td>[balance sheet] Represents the total borrowings of a company, converted to USD using the current exchange rate.</td><td>Balance Sheet</td><td>Liabilities</td></tr><tr><td>non_current_debt</td><td>[balance sheet] The portion of [total_debt] that is not due within the next twelve months.</td><td>Balance Sheet</td><td>Liabilities</td></tr><tr><td>current_debt</td><td>[balance sheet] The portion of [total_debt] that is due within the next twelve months.</td><td>Balance Sheet</td><td>Liabilities</td></tr><tr><td>total_debt</td><td>[balance sheet] The aggregate amount of current and long-term borrowing obligations.</td><td>Balance Sheet</td><td>Liabilities</td></tr><tr><td>cost_of_revenue</td><td>[income statement] The total cost incurred to produce the goods or services sold during a specific period.</td><td>Income Statement</td><td>Expense</td></tr><tr><td>consolidated_income</td><td>[income statement] The total earnings for the consolidated entity after taxes but before deducting earnings attributable to non-controlling interests.</td><td>Income Statement</td><td>Income</td></tr><tr><td>cash_equiv_usd</td><td>[balance sheet] The amount of [cash_equivalents] held by a company, expressed in USD and converted using the [forex_usd] rate.</td><td>Balance Sheet</td><td>Assets</td></tr><tr><td>cash_equivalents</td><td>[balance sheet] Cash on hand and in banks, as well as cash equivalents, which are liquid and short-term in nature.</td><td>Balance Sheet</td><td>Assets</td></tr><tr><td>capital_expenditures</td><td>[cash flow statement] Outlays of cash intended to produce long-term benefits, such as purchasing or upgrading physical assets like property, plant, or equipment.</td><td>Cash Flow Statement</td><td>Cash Flow</td></tr><tr><td>non_current_assets</td><td>[balance sheet] The total value of assets that are not expected to be converted to cash within one year.</td><td>Balance Sheet</td><td>Assets</td></tr><tr><td>current_assets</td><td>[balance sheet] Assets that are expected to be converted to cash, sold, or consumed within a year.</td><td>Balance Sheet</td><td>Assets</td></tr><tr><td>total_assets</td><td>[balance sheet] The total value of all recognized assets owned by a company at the end of a reporting period.</td><td>Balance Sheet</td><td>Assets</td></tr><tr><td>accum_other_comp_income</td><td>[balance sheet] The total accumulated amount of income or loss not recognized in net income, including items like foreign currency translation adjustments and unrealized gains/losses on securities.</td><td>Balance Sheet</td><td>Equity</td></tr><tr><td>dividends_total</td><td>Total dividends paid, calculated as dividends per share times shares outstanding.</td><td>Income Statement</td><td>Expense</td></tr><tr><td>cash_short_term</td><td>Sum of cash and short-term investments.</td><td>Balance Sheet</td><td>Asset</td></tr><tr><td>total_operating_net_income</td><td>Combined income from ongoing operations and discontinued operations.</td><td>Income Statement</td><td>Income</td></tr><tr><td>net_income_excluding_discontinued</td><td>Net income with the income from discontinued operations removed.</td><td>Income Statement</td><td>Income</td></tr><tr><td>comprehensive_net_income</td><td>Aggregate net income including all operations and adjustments.</td><td>Income Statement</td><td>Income</td></tr><tr><td>adjusted_parent_equity</td><td>Parent equity adjusted for tax assets and preferred dividends.</td><td>Balance Sheet</td><td>Equity</td></tr><tr><td>book_equity_value</td><td>Final book value of equity after adjustments for invested capital, debt, and investments.</td><td>Balance Sheet</td><td>Equity</td></tr><tr><td>operating_working_capital</td><td>Capital used in the business's ongoing operations.</td><td>Balance Sheet</td><td>Asset</td></tr><tr><td>total_nonoperating_assets</td><td>Assets not directly related to the company's core operations.</td><td>Balance Sheet</td><td>Asset</td></tr><tr><td>operating_accruals</td><td>Accruals related to operating activities, adjusted for net income and cash flow.</td><td>Cash Flow Statement</td><td>Cash Flow</td></tr><tr><td>operating_cash_flow</td><td>Cash flow from operating activities, adjusted for net income and accruals.</td><td>Cash Flow Statement</td><td>Cash Flow</td></tr><tr><td>total_operating_assets</td><td>Total assets attributed to the company's primary business activities.</td><td>Balance Sheet</td><td>Asset</td></tr><tr><td>cash_operating_profit</td><td>Operating profit adjusted for non-cash EBITDA and accruals.</td><td>Income Statement</td><td>Income</td></tr><tr><td>total_accruals</td><td>Total accrual-based adjustments to net income.</td><td>Cash Flow Statement</td><td>Cash Flow</td></tr></tbody></table>

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



## Risk Database Description

### Overview

The Risk Database is a sophisticated analytical tool designed to evaluate and forecast a wide range of risks across different sectors of the economy and financial markets. Utilizing an extensive collection of time-series data, the database aids investors in navigating the complex landscape of market, business, and political risks.

#### Potential Use Cases

1. **Strategic Investment Decisions**: Investors can use the database to understand the impact of various risks on asset classes, thereby tailoring their investment strategies to mitigate potential downsides or capitalize on emerging opportunities.
2. **Risk Management**: By quantifying and forecasting risk, the database serves as a critical component in the formulation of risk management policies for financial institutions.
3. **Economic Analysis**: Policymakers and economic analysts can leverage the insights to gauge economic health and prepare for potential market shifts caused by political or business developments.

### Key Components

#### Risk Indices

1. **Turing Risk Index**: A composite measure combining Market, Business, and Political Risks to provide an overarching view of the risk environment.
2. **Market Risk Score**: Evaluates the potential volatility and the downside risk within global markets using advanced statistical models.
3. **Business Risk Score**: Aggregates various measures of business conditions, sector sentiment, and economic indicators.
4. **Political Risk Score**: Measures the level of uncertainty in domestic and international policy-making spheres.



### Technical Use Cases

#### Market Dynamics

**Rolling Correlation**: Pinpoint emerging risks by monitoring the evolving correlations among key risk indices, useful for adjusting asset allocations.

#### Volatility Forecasting

**Rolling Standard Deviation**: Use trends in risk volatility to inform timing for investment decisions and risk hedging strategies.

#### Risk-Return Relationship

**Concurrent Correlation**: Apply insights from the risk-return interplay to refine predictive models for asset pricing and strategic investment planning.

#### Stock Risk Profiling

**Beta Distributions**: Leverage beta scores to align investment choices with risk profiles, potentially aiding in the construction of bespoke investment solutions.

#### Predictive Analytics

**Causal Analysis & Risk Forecasting**: Incorporate statistical significance testing and advanced forecasting methods to predict market movements and inform proactive risk management.

#### Trend Analysis

**Heatmap Visualization & Historical Comparison**: Utilize visual trend analysis and historical parallels to anticipate shifts in the risk environment and adapt investment strategies accordingly.













***
