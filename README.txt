HISTORICAL DATA ON STOCK PRICE OF 10 POPULAR COMPANIES
Dashboard Created by Nnamdi Leonard

-------------------------------------------------------------------------------------------------------------------
Order Of Execution:
- Understanding the Business Requirement and dataset, then organised the data dictionary.
- Data Cleaning Processes / Data Transformation
- Analysis 
- Insights
- Recommendation

-------------------------------------------------------------------------------------------------------------------
BUSINESS REQUIREMENT:

- The subject matter of this dataset contains the stock prices of the 10 popular companies ( Apple, Amazon, 
Netflix, Microsoft, Google, Facebook, Tesla, Walmart, Uber and Zoom) from year 2015 to 2021. The task is to
compare the stock price growth between the companies and provide a time series forecast.

-------------------------------------------------------------------------------------------------------------------
DATA CLEANING / TRANSFORMATION PROCESSES:

- The data contained headers but was stored as records, so I promoted the headers in the power query.

- Checked for duplicates and removed them.

- Checked for inconsistencies in datatypes and corrected them.

- The Date column was split into date and time columns by delimeter, and Month and Year columns were extracted from the date 
  column as well.

- Removed the time column and other unncessary columns.

- Filtered rows to remove nulls

- Added a new date table for Time Series Forecasting.

- Created a table called 'Company' using DAX to amalgamate the data from these company's individual tables into one, 
  which consists of the required calculated fields for comparison; average Highs, close and Open Price, and Total 
  Volume.

Challenges:
1. The data came in seperately for each company, so the cleansing process was rigorous as I had to perform it for each.

-------------------------------------------------------------------------------------------------------------------
ANALYSIS 

1. Calculated the Average Daily and Annual Trade Volume. 

2. Calculated the Annual Percentage Change in trade, which is calculated by; 
   (Avg. Close Price - Open Price)/Open Price x 100

3. Calculated a 30-day Moving Average, which is calculated using DAX by; 
   AVERAGEX(DATESINPERIOD('Company'[Date], LASTDATE('Company'[Date]), -30, DAY), 'Company'[High])

4. Total Volume of Stock Traded

5. Comparisons for Average High Price recorded.

Challenges:
1. Efforts to plot the Time Series for these Companies proved abortive, because:
	i. The date recorded could not be used for the companies collectively, but separately since data for the
           companies are in different folders - Transpose on the data to solve this didn't work either as modelling
	   returned errors. 
	ii.The dates recorded were inconsistent and had a lot of gaps. Despite creating a date table and filtering out 
     	   blanks, plotting the Time Series Forecasting was futile.

-------------------------------------------------------------------------------------------------------------------
INSIGHTS AND RECOMMENDATION:

- Insights and Recommendation was provided in the story telling part of my report, after careful analysis of the data
  as seen.


THANKS FOR YOUR TIME