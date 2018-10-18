## Data 512 A1 (Data Curation)

Goal: The goal of the assignment is to construct, analyze, and publish a dataset of monthly traffic on English Wikipedia from January 1 2008 through September 30 2018.
The intermediate datasets are saved as json and csv files, and the final graph displays the trends over time. 
For the assignment, two different Wikimedia REST API endpoints are used (Legacy and Pageviews).

### Terms of Use and License of Source Data
- Wikimedia contains their own license and terms of use as described below:

    - The Wikimedia REST API offers access to Wikimedia's content and metadata in machine-readable formats. Focused on high-volume use cases, it tightly integrates with Wikimedia's globally distributed caching infrastructure. As a result, API users benefit from reduced latencies and support for high request volumes.

    - The REST API along with its documentation is available for all major Wikimedia projects at the location /api/rest_v1/. For example, for the English Wikipedia it is available at [https://en.wikipedia.org/api/rest_v1/](https://en.wikipedia.org/api/rest_v1/).

    - While the functionality offered by most projects closely matches that on English Wikipedia, there are some noteworthy exceptions:

        - wikimedia.org offers cross-project information like page view metrics.
        - en.wiktionary.org offers an experimental definition end point, exposing Wiktionary information as structured data. Support for other languages is under discussion.

    More can be read at: [https://www.mediawiki.org/wiki/REST_API#Terms_and_conditions](https://www.mediawiki.org/wiki/REST_API#Terms_and_conditions)

### APIs Used for Data Collection

- Wikimedia Legacy Pagecounts API : [https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts)
- Wikimedia Pageviews API : [https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews)

### Curated Data

Final csv data has the following fields: 

-year
-month
-pagecount_all_views (total number of views,  source: legacy pagecounts API) 
-pagecount_desktop_views (total number of views from desktop clients, source: legacy pagecounts API)
-pagecount_mobile_views	(total number of views from mobile clients, source: legacy pagecounts API)
-pageview_all_views (total number of views, source: pageviews API)
-pageview_desktop_views (total number of views from desktop clients, source: pageviews API)
-pageview_mobile_views (total number of views from mobile clients, source: pageviews API)

### Considerations
Overlap can be seen from July 2015 to July 2016, as both the APIs were in effect during the sepcified timeperiod. Data from the pageview API excludes crawlers/spiders, whereas the data from legacy API does not. Pageviews API provide data seperately for mobile web and mobile app, which is merged into one for the purpose of the analysis. 

