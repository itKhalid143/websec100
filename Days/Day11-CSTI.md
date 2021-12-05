# Client Site Template Injection Vulnerability

CSTI could allow you to execute arbitrary JavaScript code in the victim occurs when developers use a client site templating engine (Example of Vue, Angular, etc), allowing users to push code to the client that contains placeholders ```{{NAME}}```.

***

## Attack Strategy: 

- Inserting CSTI Attack vector in every possible input field to identify the vulnerability.
- In case the Vulnerability is Identified, we must understand the targeted templating engine and get the basics of it and how it works to perform more attacks on it.
- Payload to test for the CSTI Vulnerability:
	- ```{{5*5}}```
- The attack would resolve to 25 means the payload has worked we must increase the impact of the vulnerability.
- CSTI leads to perform Cross-site scripting attacks.

***

## Takeaways

- You could confirm this by using tool such as  **Wappalyzer**or **BuiltWith** or by vewing the source and looking for ng- HTML attribues.
- Understanding how the software you're testing works will help you uncover vulnerabilities.

***

## References
- https://book.hacktricks.xyz/pentesting-web/client-side-template-injection-csti
	- For different Attack method applied on Different Template Engines.