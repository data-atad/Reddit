# Reddit API documentation

> Author: Giorgi Kochiashvili
> [giofolio.com](http://giofolio.com)


## Description
 Reddit API provides the top mentioned stock tickers and their sentiment analysis. These analysis are done on posts and comments for each post.

 It also provides the data of top mentioned stock tickers and sentiment analysis from Dailiy Discussion posts (_pinned_ posts by admin) by analysing the comment sections.

 The data is avaliable by the multiple subreddits (list below) and by different filters (list below).

 __Subreddits__

 * stocks
 * wallstreetbets
 * investing
 * pennystocks

 __Filters__

 * hot
 * new
 * rising
 * top_day

 Please note that the data is refreshed multiple times throughout the day.


## How to get Access Tokens

1. Go to [API Manager by Giorgi Kochiashvili](http://apimanager.giofolio.com/) and login or create the account.
1. Click on APIs tab from the side menu.
1. Click on Details under Reddit (this will show you the specifications of the API).
1. Click on Get a Token.
1. Now you can see _Your Token_ and also _Public Token_. You will need both of them to access the Reddit API endpoints.


## Endpoints
##### Data from the Regular (unpinned) Posts


> Get top #howmany mentioned tickers by a subreddit and a filter
```HTML
http://reddit.giofolio.com/endpoint/unpinned/by/subreddit_and_category/<Your_Token>/<Public_Token>/<subreddit>/<filter>/<howmany>
```

> Get top #howmany mentioned tickers by only a subreddit
```HTML
http://reddit.giofolio.com/endpoint/unpinned/by/subreddit/<Your_Token>/<Public_Token>/<subreddit>/<howmany>
```

> Get top #howmany mentioned tickers by all subreddits and filters
```HTML
http://reddit.giofolio.com/endpoint/unpinned/<Your_Token>/<Public_Token>/<howmany>
```



##### Data from the Pinned (Daily Discussion) Posts

> Get top #howmany mentioned tickers by each pinned post in a given subreddit
```HTML
http://reddit.giofolio.com/endpoint/pinned/by/subreddit_and_post/<Your_Token>/<Public_Token>/<subreddit>/<howmany>
```

> Get top #howmany mentioned tickers by a subreddit
```HTML
http://reddit.giofolio.com/endpoint/pinned/by/subreddit/<Your_Token>/<Public_Token>/<subreddit>/<howmany>
```

> Get top #howmany mentioned tickers by all subreddits
```HTML
http://reddit.giofolio.com/endpoint/pinned/<Your_Token>/<Public_Token>/<howmany>
```


## Interpretation of Results

The response of the endpoint is jsonified. It consists of two parts - _results_ and _server response_.

_results_ contain the actual data requested. It contains a ticker, number of mentions, sentiment and subjectivity of the posts and comments regarding the ticker.
> Please note that the _result_ of the pinned posts will not contain post sentiment and subjectivity but only comment sentiment and subjectivity.

_server response_ contains the meta data from the API manager. Here you can see if you were successfully authenticate or not, the remaining calls for the day. This can be useful while debugging.

