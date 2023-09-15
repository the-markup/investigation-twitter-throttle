# Data for “Twitter is Still Throttling Competitors’ Links”

Here is the data for our story "[Twitter is Still Throttling Competitors’ Links](https://themarkup.org/2023/09/15/twitter-is-still-throttling-competitors-links-check-for-yourself)"
Twitter continues to slow traffic to competing sites nearly a month after it partially pulled back from such throttling, a Markup analysis has found. Read the [full story](https://themarkup.org/2023/09/15/twitter-is-still-throttling-competitors-links-check-for-yourself).


# Methodology

The slowdowns identified by The Markup occur through X’s automatic link shortening service, which converts URLs posted to the platform to short links to the t.co domain, which is controlled by Twitter, officially known as X. 

For our tests, we created a list of 20 website domains we suspected might be throttled. This includes sites previously reported as slowed by X, previously banned or blocked by X, or previously criticized by X owner Elon Musk, including the New York Times, Reuters, Linktree, and outposts of the rival social networks Mastodon and Nostr. 


We also created a control group, chosen at random from a pool of 1,924 domains made up of [news websites](https://github.com/palewire/news-homepages/blob/main/newshomepages/sources/sites.csv), [non-profit organizations](https://www.charitywatch.org/top-rated-charities/all-charities), [companies](https://web.archive.org/web/20230724140856/https://fortune.com/fortune500/), and [popular domains](https://tranco-list.eu/).

We then searched X for tweets containing links to those sites, choosing a random sample from the search results for each site. Our test measured the amount of time it took for a X shortened link to successfully expand, redirecting users to the full URL. We stopped the timer once the full URL was successfully requested, and we did not record the amount of time it takes for content to fully load on the page. 

In our tests, links to Bluesky, Facebook, Instagram, and Substack shortened by X took 2,544 milliseconds (2.5 seconds) on average to redirect to the original site, compared with an average redirect time of 39 milliseconds for links to the other 59 other domains in our control group.

We tested X’s links over a period of four days, requesting the links each hour. The delayed responses to these requests remained consistent at all hours of our test period. It also remained consistent throughout various parts of the U.S. when we requested the links from computers in New York City, Detroit, and Los Angeles.


X’s slow responses also contrasted sharply with the performance of the popular link-shortening service Bit.ly. In our tests, involving the same links we tested on X, Bit.ly loaded links to Bluesky, Facebook, Instagram, and Substack faster than the average load time we measured, 50 milliseconds.

Questions? Write to us: [keegan@themarkup.org](mailto:keegan@themarkup.org) 

# Data

**[tco-test-results.csv](https://github.com/the-markup/investigation-twitter-throttle/blob/main/tco-test-results.csv)** - 30.6 KB KB. 97 rows. First row is the header (CSV).
This file contains our test results, measuring the amount of time in milliseconds it took for X to expand a shortened URL for a given domain. Each column header is a domain that we tested. The time column is a timestamp of the test (UTC). Each domain had up to 4 shortened t.co URLs that were tested, and the value in the data is the average time that it took from the time the shortened t.co url was requested until the time the final page request was successful. We did not measure the amount of time it took for the page itself to load.  


**[tco-bitly-series.csv](https://github.com/the-markup/investigation-twitter-throttle/blob/main/tco-bitly-series.csv)**- 5.7 KB KB. 97 rows. First row is the header (CSV).
To add evidence that the delays we were seeing for the four domains was added intentionally by X, we tested the same destination URLs from popular link-shortening service Bit.ly. This file contains the average time in milliseconds that it took from the time the shortened t.co and bit.ly urls were requested until the time the final page request was successful. We did not measure the amount of time it took for the page itself to load. 
In our tests, involving the same links we tested on X, Bit.ly loaded links to Bluesky, Facebook, Instagram, and Substack faster than the average load time we measured, 50 milliseconds.

