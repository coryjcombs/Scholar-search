# Scholar-Search
A multi-page, multi-term scraper for Google Scholar results (version 1.0.6)

## Background
This scraper was developed for use in a systematic review of scholarship on electricity generation, co-authored by Sarah M. Jordaan, Cory J. Combs, and Edeltraud Günther. The collected data served as the basis for an article being prepared for submission in early 2020.

## Details
* Designed to scrape all results of Google Scholar searches, up to Scholar's imposed maximum of 100 pages (1000 results) for each search.
* Developed using BeautifulSoup, Pandas, and the requests and time packages.

## Credits
* This code build upon a single-page scraper for Google.com search results developed by Edmund Martin, whose original work is [available here](https://edmundmartin.com/scraping-google-with-python/). Many thanks and all due credit to Edmund Martin!
* Adaptation for Google Scholar, as well as iteration over pages, data extraction and manipulation, and export control were coded by Cory J. Combs.

## Scraper Components
1. A user agent, which provides identifying information to the server
2. A function to fetch results
3. A function to parse results
4. An function to execute fetching and parsing with error handlers
5. The main search script, which:
  * executes the search with the input parameters,
  * outputs the results in a pandas data frame,
  * extracts metadata elements not consistently identifiable through Google Scholar's html or xml alone,
  * cleans and formats the data, and
  * exports the fully formatted dataframe into Excel

The results may be explored in the output Excel file or in Python using pandas. The final formatted pandas data frame is called "data_df_clean" by default.

## Ethics of Scraping
Without appropriate constraints, web scraping can cause undue stress on a server. As such, special care was taken in implementing this scraper to ensure ethical use of server requests, first by scripting pauses between both page iterations and individual result collections, and second by separating execution of each search across the day, over multiple days, and avoiding peak usage times. When developing the script, a sample test was manually confirmed to yield a small number of results prior to execution to avoid unnecessary server burden.
For an interesting exploration of scraping Google Scholar results at a far larger scale, and through different means, see [Else 2018 in Nature](https://www.nature.com/articles/d41586-018-04190-5).
