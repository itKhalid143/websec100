#Open Redirect Vulnerability#

Occurs when the application allows us to redirect to the Attacker's website, which can be leveraged for phishing attacks against users of the application. (low impact)

`http://site.com/search?url=http://evil.com`

![Open Redirect](https://1tskcg39n5iu1jl9xp2ze2ma-wpengine.netdna-ssl.com/wp-content/uploads/2019/03/open-redirection-vulnerability.png)

## Types of Redirections: 
Markup :
	* Header-Based
	* Javascript-Based

***

## Countermeasures:

	- Implementing Interstitial web pages which display before the expected content, Any time you redirect a user to an URL, the Interstitial web page is shown to indicate and explain to the user that they're leaving the domain they're in.
	- Removing the redirection function, replacing it with direct links.
	- Adding a while list website that can allow redirection to.

***

## Takeaways: 
Markup :
	- Changing the domain_name parameter to an external site would redirect the user offsite
	- Notice the services and technology that are being used in the application, each represents a new attack vector.

