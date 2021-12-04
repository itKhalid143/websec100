# SQL Injection

- SQL stands for Structed Query Language.

## Type of Querying methods:
### Normal Query
```mysql
SELECT username 
FROM users
WHERE
	username = 'INPUT' 
	AND
	password='INPUT' 
;
```
### Prepared Statement
```mysql
database.query(SELECT username FROM users WHERE username = ? AND password= ?', (username, password)
				)
```
- A prepared statement or a parameterized statement is used to execute the same statement repeatedly with high efficiency and protect against SQL injections.

*** 

## What is SQL Injection
SQL injection allows an attacker to interfere with the queries that an application makes to its database.
(Allows to view data that they are not normally able to retrieve)

### Example

- ```SELECT username FROM users WHERE username = 'INPUT' AND password= 'INPUT';```
	- This is a normal query to get the username with the credential we pass, how about, we force the server to send inputs that might cause errors, as an example sending ```admin' OR 1=1-- -``` the Query will be seen as:
	- ```SELECT username FROM users WHERE username = ' OR 1=1--``` ``` - AND password= 'INPUT';```
		- This query returns the user whom username is admin and successfully logs in, ignoring the password part, as it acts as a comment after adding ``--``.


## Types of SQL Injections: 

- In-band SQLi
	- Error-Based
		- The attacker causes the database to produce error messages. (Can be used to gather information about the database)
	- Union-Based
		- It takes advantage of UNION SQL operator, which adds multiple select statements to get a single HTTP response.
- Blind
	- Occurs when you can inject SQL statements into a query but can't get a query's direct output.
	- Boolean
		- the result will vary depending o whether the query is true or false.
	- Time-Based
		- The attacker can see from the time database takes to respond, whether a query is true or false.
- Others: Out-Of-Band, Stacked Queries and Routed SQLI (Very Uncommon)
***

## Countermeasures:

- Always use prepared statements!
- Never put user input directly into the query.
- Implementing WAF (Web Application Firewall)
	- WAF uses signature recognition, IP reputation, and other security methodologies to identify and block SQL injections, with a minimal amount of false positives.

***

## WAF Bypasses

Depends on the WAF mechainsms, here's few bypasses:
- No Whitespace
	- ‘/**/OR/**/1=1/**/--
	- ‘AND(1)=(1)--
- No Equal using
	- LIKE, (NOT) IN, BETWEEN
	- ‘text’ LIKE ‘text’
	- ‘text’ IN ‘text’
	- ‘b’ BETWEEN ‘a’ AND ‘c’
- No AND or OR
	- && and ||

Great Resource: https://github.com/khalid0143/PayloadsAllTheThings

***

## SQL Map
- SQLMAP is an open source penetration testing tool writted in python to detect and exploit SQL Injection flaws. It works for all modern databases including mysql, postgresql, oracle, microsoft sql server, etc.
![slqMAP](https://sectechno.com/wp-content/uploads/2020/05/sqlmap-1.png)

***

## Takeaways: 

- One way to find SQLi Vulnerabilities is to test URL parameters and look for subtle changes to query results.
- Keep an eye out for HTTP requests that accept encoded parameters.
- When looking for SQLI Vulnerabilities, explore places where you can pass unescaped single or double quotes for a query.
- Look for places where you can pass data to a site in unexpected ways, such as where you can substitute array parameters in request data

