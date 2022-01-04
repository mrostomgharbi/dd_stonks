## About 


The original AutoDD produced a simple table of the stock ticker and the number of threads talking about the ticker.

This version adds some options and features that the original did not have.
	- ability to display a change in results (ie, from the previous day to today)
	- ability to pull additional stock information from yahoo (such as open and close price, volume, average volumn, etc)
	- ability to pull results from multiple subreddits (pennystocks, RobinHoodPennyStocks, stocks, Daytrading, etc)
	- added score system to calculate a score for each ticker based on the number of occurrences, DD or Catalyst flair, and number of upvotes

## Requirements 

Python 3.8

psaw - pip install psaw https://pypi.org/project/psaw/

yahooquery - pip install yahooquery https://pypi.org/project/yahooquery/

## Running
Simply open the terminal and navigate to the AutoDD.py folder, then type:

    python AutoDD.py

Running the script typically takes 1 minute or so, depending on your options and the number of results found
Once the script finishes running:
	
	1. The terminal will output: "Wrote to file successfully: C:\AutoDD-folder\table_records.txt"
	2. An output called table_records.txt will be created in the same folder as AutoDD.py.
		- If table_records.txt already exists, it will append to the text file instead 


## Options

In terminal, type:

	python AutoDD.py -h
	
This will produce the following help text:

	usage: AutoDD.py [-h] [--interval [INTERVAL]] [--min [MIN]] [--adv] [--sub [SUB]] [--sort [SORT]] [--filename [FILENAME]]

	AutoDD Optional Parameters

	optional arguments:
	  -h, --help            show this help message and exit
	  --interval [INTERVAL]
							Choose a time interval in hours to filter the results, default is 24 hours
	  --min [MIN]           Filter out results that have less than the min score, default is 10
	  --adv                 Using this parameter shows advanced ticker information, running advanced mode is slower
	  --sub [SUB]           Choose a different subreddit to search for tickers in, default is pennystocks
	  --sort [SORT]         Sort the results table by descending order of score, 1 = sort by total score, 2 = sort by recent score, 3 = sort by previous score, 4 = sort by change in score
	  --filename [FILENAME]
							Change the file name from table_records.txt to whatever you wish
			
			
Interval (Time interval)
	- Choose a time interval in hours to filter the results, default is 24 hours
	- The score in the Total column shows the score for each ticker in the last 24 hours
	- The score in the Recent column shows the score for each ticker in the last 12 hours
	- The score in the Prev column shows the score for each ticker in the last 12-24 hours
	- The score in the other subreddit columns shows the score for each ticker in the last 24 hours
	
Min (Minimum score)
	- Filter out results that have less than the min score in the Title column, default is 10
	
Adv (Advanced settings)
	- Using this parameter shows advanced ticker information, running advanced mode is slower
	- This options shows additional yahoo information on the ticker, such as open price, day low, day high, forward PE, beta, volume, etc.
	
Sub (Subreddit)
	- Choose a different subreddit to search for tickers in, default is pennystocks
	- When a different subreddit is choosen, the total, recent, prev columns contain the score for the choosen subreddit
	- Possible choices: pennystocks, RobinHoodPennyStocks, Daytrading, StockMarket, stocks

Sort
	- Sort the results by descending order of score, by default the table shows the highest total score first
	-  pass in values 1, 2, 3, or 4
	- 1 = sort by total score, 2 = sort by recent score, 3 = sort by previous score, 4 = sort by change in score

Filename
	- choose a different filename, this programs saves the table results to table_records.txt in the same folder as the AutoDD.py program
	
