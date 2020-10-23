# RSS Feed

#### Including RSS 
To allow your users to subscribe to Trase RSS feed, you will need to add a rule on you server **redirecting /rss to this [url](https://schema-cms-api-appf1b96344-h125qh2n240n.s3.amazonaws.com/rss/7/trase-insights-rss.xml)** or simply redirect to http://trase-prod.schemacms.com/rss

If you have an nginx server, the format should look similar to 

```
server {
  ...
  location /rss {
    return 301 http://trase-prod.schemacms.com/rss
  }
  ...
}
```
