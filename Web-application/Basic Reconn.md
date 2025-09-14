# Manual Discovery

## **I. Robots.txt**
> - The robots.txt file is a document that tells search engines which pages they are and aren't allowed to show on their search engine results or ban specific search engines from crawling the website altogether. It can be common practice to restrict certain website areas so they aren't displayed in search engine results. These pages may be areas such as administration portals or files meant for the website's customers. This file gives us a great list of locations on the website that the owners don't want us to discover as penetration testers.

Example: 
```
https://x.x.x.x/robotx.txt
```

## **II. Favicon**
> - Sometimes when frameworks are used to build a website, a favicon that is part of the installation gets leftover, and if the website developer doesn't replace this with a custom one, this can give us a clue on what framework is in use. OWASP host a database of common framework icons that you can use to check against the targets favicon [https://wiki.owasp.org/index.php/OWASP_favicon_database](https://wiki.owasp.org/index.php/OWASP_favicon_database). Once we know the framework stack, we can use external resources to discover more about it (see next section).

Step 1:
Get the url that stores the favicon.ico.
```
https://example.com/sites/favicon/images/favicon.ico
```

Step 2:
Download the favicon and get its md5 hash value with the command.
```
curl https://example.com/sites/favicon/images/favicon.ico | md5sum
```

Step 3:
Look up on `https://wiki.owasp.org/index.php/OWASP_favicon_database` to find the framework version based on the md5 hash value.

## **III. Sitemap.xml**
> - Unlike the robots.txt file, which restricts what search engine crawlers can look at, the sitemap.xml file gives a list of every file the website owner wishes to be listed on a search engine. These can sometimes contain areas of the website that are a bit more difficult to navigate to or even list some old webpages that the current site no longer uses but are still working behind the scenes.

Example:
```
http://example.com/sitemap.xml
```


## **IV. HTTP Headers**
> - When we make requests to the web server, the server returns various HTTP headers. These headers can sometimes contain useful information such as the webserver software and possibly the programming/scripting language in use. In the below example, we can see the webserver is NGINX version 1.18.0 and runs PHP version 7.4.3. Using this information, we could find vulnerable versions of software being used. Try running the below curl command against the web server, where the `-v` switch enables verbose mode, which will output the headers (there might be something interesting!).

Example:
```
user@machine$ curl http://10.201.16.168 -v 
* Trying 10.201.16.168:80... 
* TCP_NODELAY set 
* Connected to 10.201.16.168 (10.201.16.168) port 80 (#0) 
> GET / HTTP/1.1
> Host: 10.201.16.168
> User-Agent: curl/7.68.0
> Accept: */* 
> 
* Mark bundle as not supporting multiuse 
< HTTP/1.1 200 OK 
< Server: nginx/1.18.0 (Ubuntu) 
< X-Powered-By: PHP/7.4.3 
< Date: Mon, 19 Jul 2021 14:39:09 GMT 
< Content-Type: text/html; charset=UTF-8 
< Transfer-Encoding: chunked < Connection: keep-alive
```
