# trading_challenge

1.Go to https://www.dukascopy.com/swiss/english/marketwatch/historical/

Change filter for candlestick to hour and number to 1

put from date as jan 1 2019 - jan 1 2020

put day start time as UTC

Choose forex -> Major -> EUR/USD


2.Clone the repo and email me link

3.Task

a) pull the CSV from Step #1 and commit to repo

b)make an migrate.php script that reads the CSV and save into a mysql table 

ticker Table fields should be (id, currency, Gmt time,Open,High,Low,Close,Volume)

c)make a table ta (id, ticker_id, ticker_diff, ticker_high, ticker_low, ticker_open_price, ticker_volume, ticker_hour, ticker_minute, ticker_day_of_week, ticker_month, ticker_year, ticker_close_price(this is close field in ticker), sma2, sma3 ... sma100(so have field for every # from 2 - 100), rsi2, rsi3 ... rsi100(so have field for every # from 2 - 100))

ticker_id is foreign key to ticker table

ticker_diff = ticker_close_price - ticker_close_price(1 hour before)

d)Take this file and change it to your class in this project

https://github.com/joeldg/bowhead/blob/master/app/Util/Indicators.php

ticker_session,ticker_new_event,price_eur_cad,price_eur_aud,price_eur_jpy,price_eur_chf

e)Make a ta.php file

where you loop through ticker table each row and insert a row into ta table.

use this https://www.investopedia.com/terms/s/sma.asp#:~:text=Key%20Takeaways-,A%20simple%20moving%20average%20(SMA)%20calculates%20the%20average%20of%20a,a%20bull%20or%20bear%20trend.

 to calculate sma value.

For example to calculate sma9 you take the last 9 tickers before current hour and plug into sma formula and get value to save. To get sma15, you take the last 15 tickers before current hour and plugin into sma formula

once calculated, insert into the column for that row

For RSI here the formula https://school.stockcharts.com/doku.php?id=technical_indicators:relative_strength_index_rsi

f)make a file called chart.php where you will graph ticker data on this graph

https://wiki.manaknightdigital.com/link/99#bkmrk-https%3A%2F%2Fwww.anychart
 
https://www.anychart.com/blog/2020/03/25/js-candlestick-chart-steps/
