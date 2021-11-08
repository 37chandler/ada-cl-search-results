# Pulling Craigslist Search Results

The first phase of our Craigslist (CL) car scraper requires us to extract the pages from the search results. 
I've created a data set for this project in our `UMT-MSBA` project on BigQuery called `carbitrage`. Within
that data set I've created a table called `search-terms`. This table tells us what make and model to search for
in which locations, as well as some additional information that might be useful such as a starting and ending
date for the query.

In your own GBQ project, create a dataset for this project and create a table to hold the search listings. The table should
have the following columns: location, make, model, listing url, and datetime pulled. 

For this assignment, I'd like you to write code that does the following: 

1. Query `search-terms` to get the location, make, and model combos where the current date is between date_start and date_end.
2. For each set of search terms, perform a search for *owner sales* at the given location. For instance, if you were searching for "Scion XB" in Atlanta, the search URL would "https://atlanta.craigslist.org/d/cars-trucks-by-owner/search/cto?query=scion%20xb".
3. From the results page, extract the listings and insert them into the table you created. If the results span multiple pages, include the subsequent pages. 
4. Bonus: one feature that we discussed which would be nice is to ensure the listing hasn't already been found. Feel free to add functionality that pulls the unique listing pages from your table and only adds new pages. 

