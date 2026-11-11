# Reproducible mini-study: Internet use in Nigeria

## Research question
How did the percentage of Nigeria's population using the internet change between 2010 and 2024?

## Dataset
World Bank World Development Indicators, `IT.NET.USER.ZS` — Individuals using the Internet (% of population), country code `NGA`.

- Indicator page: https://data.worldbank.org/indicator/IT.NET.USER.ZS?locations=NG
- API request: https://api.worldbank.org/v2/country/NGA/indicator/IT.NET.USER.ZS?date=2010:2024&format=json&per_page=100
- Data accessed and baseline snapshot compiled: 11 November 2026.
- The notebook retrieves the observations directly from the API when run. The API is the authoritative reproducible source; historical values may be revised by the publisher.

## Tool
Python with `pandas`, `requests`, and `matplotlib`. Run in Google Colab or Jupyter Notebook.

## Cleaning steps
1. Retrieve only Nigeria (`NGA`), indicator `IT.NET.USER.ZS`, years 2010–2024.
2. Retain year and value fields and rename them.
3. Convert both fields to numeric; invalid values become missing.
4. Sort by year ascending.
5. Keep missing observations visible; exclude them only from the endpoint calculation and chart.
6. Do not impute, remove outliers, or delete any other rows.

## Calculation and finding (baseline snapshot compiled 11 November 2026)
Change in percentage points = last available non-missing observation minus first available non-missing observation.

In the 2010–2024 World Bank WDI series, the estimate increased from **11.50% in 2010** to **41.21% in 2024**, a rise of approximately **29.71 percentage points**. This is an increase in the share of the population estimated to have used the internet in the previous three months; it is not a measure of daily use or internet access quality. The notebook recalculates the result from the API when rerun. `Nigeria_Internet_Use_2010_2024.csv` is the dated reference snapshot included to make the displayed baseline independently inspectable.

## Plain-language finding (under 150 words)
World Bank data indicate that internet use in Nigeria rose from 11.5% of the population in 2010 to about 41.2% in 2024. That is an increase of about 29.7 percentage points over the period. The trend shows a substantial rise in the share of people estimated to have used the internet at least once in the previous three months. It does not mean that 41.2% used the internet every day, had reliable connections, or could afford data. This is a national-level trend and does not show which groups or states experienced the greatest change.

## What the data cannot tell us
This national indicator does not reveal individual identities, frequency or purpose of use, affordability, connection quality, or differences by state, age, gender, disability, income, or urban/rural location. It cannot explain why use changed or establish that a policy caused the change. The latest observation may be earlier than 2024.

## Re-run
Open `Nigeria_Internet_Use_Mini_Study.ipynb` in Google Colab or Jupyter and run all cells from top to bottom. Internet access is required. The output prints the API URL and date of execution. Since the World Bank may revise historical observations, record the output values and date when you rerun.
