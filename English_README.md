# Stock Data Description Document

English | [简体中文](README.md)

## ℹ️ Basic Introduction

This project contains multi-dimensional, multi-source data related to stocks and indices from 1990 to August 2025, covering basic stock information, market performance, financial indicators, factor analysis, index weights, and other content. It is suitable for stock research, data analysis, strategy backtesting, and other scenarios. The data is logically divided into four modules: **Basic Data**, **Market Data**, **Financial Data**, and **Factor Data**. Each module contains subdivided data tables that detailedly record various attributes and indicators of stocks.
The data in this project is updated monthly. Please stay tuned for the latest data.

Please refer to the `Data Dictionary.md` document for the data dictionary.

## 📑 Table of Contents

- `daily_basic/` Contains daily basic indicators of stocks, such as price-to-earnings ratio (pe), turnover rate, etc.

- `fina_indicator/` Contains financial indicators of listed companies, including solvency, profitability, operational capacity, and other related indicators.

- `index/` Contains stock index-related data, such as index codes, names, and daily market quotes.

- `stock_daily/` Contains daily market data of stocks, including opening price, closing price, highest price, lowest price, and trading volume.

- `stock_daily_hfq/` Contains daily stock market data after forward 复权 processing (adjusted according to dividends and stock splits).

- `adj_factor.7z` Contains the adjustment factors for stock prices, used to calculate adjusted market data.

- `dividend.7z` Contains dividend and stock split data of listed companies.

- `fina_mainbz.7z` Contains data on the composition of the main business of listed companies, including income from different business segments.

- `financial_factor.7z` Contains derivative financial factors calculated based on financial statements.

- `stock_balancesheet.7z` Contains balance sheet data of listed companies, reflecting assets, liabilities, and shareholders' equity.

- `stock_cashflow.7z` Contains cash flow statement data of listed companies, recording cash inflows and outflows from operating, investing, and financing activities.

- `stock_income.7z` Contains income statement data of listed companies, including revenue, costs, and profits.

  ##### Data stored in Baidu Netdisk (see the remarks section for the network disk link; some large - volume data and data from other sources are stored here):

- `quantity_price_factor.tar` Contains data related to quantity - price factors.

- `Resse daily data.7z` Contains daily stock market data from the Resse platform.

- `Fund.7z` Contains fund - related data.

- `Index data.7z` Contains stock index data.

- `Income statement.7z` Contains income statement data of listed companies.

- `Daily market value.7z` Contains daily market value data of stocks.

- `Guotai'an index component stocks.7z` Contains data related to Guotai'an platform index component stocks.

- `Balance sheet.7z` Contains balance sheet data of listed companies.

- `Bond.7z` Contains bond - related data.

- `Resse index classification.7z` Contains data related to Resse platform index classification.

- `Suspension and resumption.7z` Contains data related to stock suspension and resumption.

- `Circulating share capital.7z` Contains data on the circulating share capital of stocks.

- `Exchange share capital.7z` Contains data related to share capital at the exchange level.

- `Trading day.7z` Contains data related to stock trading days.

## 📊 Details of Data Modules

### 1. Basic Data

Basic data includes static information of stocks and basic information of listed companies, which is used to identify stock identities, affiliated fields, and core company information.

#### 1. Basic Information

Records the core identifiers and basic attributes of stocks, including codes, names, and affiliated markets.



| Name     | Type | Description         |
| -------- | ---- | ------------------- |
| code     | str  | Stock code          |
| symbol   | str  | Stock code          |
| name     | str  | Stock name          |
| area     | str  | Region              |
| industry | str  | Affiliated industry |
| ...      | ...  | ...                 |

#### 2. Basic Information of Listed Companies

Records details such as registration information, management, and business scope of listed companies.



| Name        | Type  | Description                      |
| ----------- | ----- | -------------------------------- |
| code        | str   | Stock code                       |
| com_name    | str   | Full company name                |
| chairman    | str   | Legal representative             |
| reg_capital | float | Registered capital (10,000 yuan) |
| setup_date  | str   | Registration date                |
| province    | str   | Province located                 |
| ...         | ...   | ...                              |

### 2. Market Data

Market data records dynamic information such as stock price fluctuations, trading volume, and suspension/resumption, reflecting the market performance of stocks.

#### 1. Daily Market Quotes

Core price and trading volume data of daily transactions, including opening price, closing price, price change, etc.



| Name       | Type  | Description   |
| ---------- | ----- | ------------- |
| code       | str   | Stock code    |
| trade_date | str   | Trading date  |
| open       | float | Opening price |
| high       | float | Highest price |
| ...        | ...   | ...           |

#### 2. Daily Indicators

Daily derivative indicators, including valuation indicators (price-to-earnings ratio, price-to-book ratio), equity indicators (total share capital, circulating market value), etc.



| Name          | Type  | Description         |
| ------------- | ----- | ------------------- |
| code          | str   | Stock code          |
| trade_date    | str   | Trading date        |
| close         | float | Daily closing price |
| turnover_rate | float | Turnover rate (%)   |
| ...           | ...   | ...                 |

#### 3. Daily Suspension and Resumption Information

Records of the dates and types of stock suspensions and resumptions.



| Name           | Type | Description                                                |
| -------------- | ---- | ---------------------------------------------------------- |
| code           | str  | Code                                                       |
| trade_date     | str  | Suspension/resumption date                                 |
| suspend_timing | str  | Intraday suspension time period                            |
| suspend_type   | str  | Suspension/resumption type: S - suspension, R - resumption |

### 3. Financial Data

Financial data includes financial statements and derivative indicators of listed companies, reflecting the company's operating conditions and financial health.

#### 1. Income Statement

Records core profit data such as revenue, costs, and profits of the company during a specific reporting period.



| Name          | Type  | Description                                                  |
| ------------- | ----- | ------------------------------------------------------------ |
| code          | str   | Stock code                                                   |
| ann_date      | str   | Announcement date                                            |
| f_ann_date    | str   | Actual announcement date                                     |
| end_date      | str   | Reporting period                                             |
| report_type   | str   | Report type (see the table at the bottom)                    |
| comp_type     | str   | Company type (1 general industry and commerce, 2 banks, 3 insurance, 4 securities) |
| end_type      | str   | Reporting period type                                        |
| basic_eps     | float | Basic earnings per share                                     |
| diluted_eps   | float | Diluted earnings per share                                   |
| total_revenue | float | Total operating revenue                                      |
| revenue       | float | Operating revenue                                            |
| ...           | ...   | ...                                                          |

#### 2. Balance Sheet

Records the assets, liabilities, and shareholders' equity of the company on a specific date, reflecting the company's financial structure.



| Name        | Type  | Description                |
| ----------- | ----- | -------------------------- |
| code        | str   | Stock code                 |
| ann_date    | str   | Announcement date          |
| total_share | float | Ending total share capital |
| cap_rese    | float | Capital reserve            |
| ...         | ...   | ...                        |

#### 3. Cash Flow Statement

Records the cash inflows, outflows, and net amount of the company during a specific reporting period, reflecting the cash flow health of the company.



| Name       | Type  | Description        |
| ---------- | ----- | ------------------ |
| code       | str   | Stock code         |
| ann_date   | str   | Announcement date  |
| net_profit | float | Net profit         |
| finan_exp  | float | Financial expenses |
| ...        | ...   | ...                |

#### 4. Dividends and Stock Splits

The plans and implementation progress of company dividends and stock splits.



| Name        | Type  | Description                         |
| ----------- | ----- | ----------------------------------- |
| code        | str   | Stock code                          |
| end_date    | str   | Dividend year                       |
| stk_bo_rate | float | Stock dividend per share ratio      |
| stk_co_rate | float | Stock split per share ratio         |
| cash_div    | float | Cash dividend per share (after tax) |
| ...         | ...   | ...                                 |

#### 5. Financial Indicator Data

Derived indicators calculated based on financial statements, including profitability, solvency, growth capacity, etc.



| Name             | Type  | Description                 |
| ---------------- | ----- | --------------------------- |
| code             | str   | Stock code                  |
| ann_date         | str   | Announcement date           |
| end_date         | str   | Reporting period            |
| eps              | float | Basic earnings per share    |
| dt_eps           | float | Diluted earnings per share  |
| total_revenue_ps | float | Operating revenue per share |
| ...              | ...   | ...                         |

#### 6. Main Business Composition

The distribution of income, costs, and profits of the company's main business.



| Name      | Type  | Description                 |
| --------- | ----- | --------------------------- |
| code      | str   | Stock code                  |
| end_date  | str   | Reporting period            |
| bz_item   | str   | Source of main business     |
| bz_sales  | float | Main business income (yuan) |
| bz_profit | float | Main business profit (yuan) |
| bz_cost   | float | Main business cost (yuan)   |

### 4. Factor Data

Factor data is derived indicators calculated based on price, trading volume, and financial data, used for quantitative analysis and strategy construction.

#### 1. Price - Volume Factors

Technical indicators calculated based on price and trading volume, reflecting market trading sentiment and trends.



| Name       | Type    | Description                            | Calculation formula                                          |
| ---------- | ------- | -------------------------------------- | ------------------------------------------------------------ |
| code       | VARCHAR | Stock code                             |                                                              |
| trade_date | DATE    | Trading date                           |                                                              |
| boll_up    | FLOAT   | Upper track (Bollinger Band) indicator | (MA (CLOSE, M) + 2 * STD (CLOSE, M)) / Today's closing price; M = 20 |
| boll_down  | FLOAT   | Lower track (Bollinger Band) indicator | (MA (CLOSE, M) - 2 * STD (CLOSE, M)) / Today's closing price; M = 20 |
| EMA5       | FLOAT   | 5 - day exponential moving average     | 5 - day exponential moving average / Today's closing price   |
| ...        | ...     | ...                                    | ...                                                          |

#### 2. Financial Factors

Indicators calculated based on financial data, reflecting the company's financial quality and operational efficiency.



| Name                                    | Type    | Description                                    | Calculation formula                                          |
| --------------------------------------- | ------- | ---------------------------------------------- | ------------------------------------------------------------ |
| code                                    | VARCHAR | Stock code                                     |                                                              |
| end_date                                | DATE    | End date of the reporting period               |                                                              |
| f_ann_date                              | DATE    | Announcement date of financial report          |                                                              |
| net_profit_to_total_operate_revenue_ttm | FLOAT   | Ratio of net profit to total operating revenue | Ratio of net profit to total operating revenue = Net profit (TTM) / Total operating revenue (TTM) |
| ...                                     | ...     | ...                                            | ...                                                          |

## 📝 Remarks

- The data is stored in the github repository, and larger files such as financial factor data and multi - source data are stored in Baidu Netdisk. Link: https://pan.baidu.com/s/1eyeHp6ftDZ4M9lcFurZkgQ Extraction code: hpa6
- Please refer to [Data Dictionary](数据字典.md) for the data dictionary.
- See [Chinese](README.md) for the Chinese document.