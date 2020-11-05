# RSS Feed

#### Including RSS 
To allow your users to subscribe to Trase RSS feed, you will need to add a rule on you server **redirecting /rss to this [url](https://schema-cms-api-appf1b96344-yc10r82aohto.s3.amazonaws.com/rss/1/trase-insights-rss.xml)**. You can also find this url when fetching the project (GET .../projects/<id>) under meta.xml_file

If you have an nginx server, the format should look similar to 

```
server {
  ...
  location /rss {
    return 301 <url>
  }
  ...
}
```
