# Server Side Request Forgery Vulnerability

While CSRF exploits another user, an SSRF explpots a targeted application server, SSRF Vulnerabilities provide attackers access to a broader network to tager, attacker makes a server perform unintended requests.
- Another way to abuse this vulnerability would be to make a request to a third
party or external server that only accepts requests coming from our target.

```
POST /random.php
url=127.0.0.1:8080/getCredentials.php
```

***

## Attack Strategy: 

- Testing any URL that gets resolved by the server and.
	- Sometimes Partial URLS in the body instead of a full URL.
	- URL within data files usch as XML, CSF, etc.
	- The referer header can sometimes contain SSRF defects. 
- 

***

## Blind SSRF
- When you can't access to the response, you've found a blind SSRF.
	- One way of exploiting response time is to port scan inaccessible servers )Might determine wether the server is open, closed, filtered based on wthether a response from a known port returns in 1 or 10 seconds)

*** 

## Countermeasures:

- Implementing CSRF Tokens
- CORS - How and when websites are communicated with each others.

***

## Takeaways: 

- When looking for SSRF, URL paramerter is a red flag.
- Google dorking can save you time when you're looking for vulnerabilities that require URLs set up in a specific way.
- Sometimes sites are meant to perform HTTP requests to external sites only. When you find sites with this functionalitym chjeck wether you can abuse it to access internal networks.
- The wording "Did not repond' is crucial because it implies that the server allows internal connections.
- Be on lookou for websites that include futionality to make external HTTP requests.


