<h1 align='center'ETL PROJECT</h1>
<h2 align='left'> GROUP MEMBERS</h2>


Scope

Our goal was to create database using an existing Kaggle data set for various wines and scraping data from a website to add additional information for user ratings.

Extract 

For first data set Kaggle was used to extract a csv file with over 83000 rows of wine info.
Data collected from this csv file contained wine brand, type of grape, and its geographical info of wine’s origins.

Kaggle’s link:
https://www.kaggle.com/gcspkmdr/wine-dataset

Vivino’s web page was used to scrape data for our second set of data.
Vivino’s link: 
https://www.vivino.com/explore?e=eJwtzjEOwjAMBdDb_DltU0EHb9wAMSGETAhRJNIiJyrt7QlJFj_5fw8OQh2Cn6lTCLzRqBTMTpczTB4nfHLtXrSyeJv4jeVBwsnPLt55tcLOYqGnjQbfdL3l40JfGSq6cmidhvy749Acm1Oxr6vOf5R40ojk-AfdtDSE"

Web scrapping

Most of our time scrapping the Vivino site. The issue we ran into was with infinite scroll of Vivino’s web page. The web used a scroll feature to load new wine on a page after a certain number of scrolls. The auto scroll made it very hard to retrieve a high count of different wines to be scrapped. Originally, we created a while loop that cause the page to loop, but that caused us to get repeat wines. To alleviate this problem, we had to do a loop on the scroll function instead looping the web page itself. In addition, the original loop did not allow enough time for new wines to get loaded into the html page.

The code we used to scroll the web page was:
browser.execute_script("window.scrollTo(0, document.body.scrollHeight);") 

After we fixed the infinite scroll problem, we were able to scrape the site for gather wine rating, number of reviews, brand and type of wine.


Transformation

Once Vivino was scraped we merged the wines brand and title into one column for the clean wine dataframe.

For the Kaggle csv we drooped a few unneeded columns and renamed ones that we kept to better suit our dataframe.

