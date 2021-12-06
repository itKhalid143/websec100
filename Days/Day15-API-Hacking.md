# API Hacking

- **API** is the acronym for **Application Programming Interface**, which is a software intermediary that allows two applications to talk to each other.

***

## Importing the Application's API to our Postman! for more Testing!

![****](/websec100/Days/Screenshots/Day15/api-import.PNG)

- Give us details about the API, Postman will generate a Collection from the imported API!

![****](/websec100/Days/Screenshots/Day15/api-import1.PNG)

![****](/websec100/Days/Screenshots/Day16/api-import2.PNG)

Thanks to Postman! did all the heavy work for us!

***

## Types of  API Vulnerabilities

### API Exposure


### Misconfigured Caching
- Occurs when an API does not use the standard Authorization header, instead using a custom header such as X-API-Key.

### Exposed tokens
- Secret tokens may be discovered in code repositories, client-side JavaScript, intercepting traffic, etc.

### JWT Weaknesses
- Occurs when the developer mess up the implementation in a way that introduces security issues.

### Authorization Issues / IDOR
Known also as **Broken Level Authorization**
- Occurs when the attacker is able to access to unauthorized resource! 
- Happens when there's a problem in the process of checking whether an authenticated user has access to a specific object.

### Rate Limiting
- APIs do not have any protection on the number of times a user can request them. 
- Vulnerable to Brute forcing attacks!

### Undocumented Endpoints
 

### Reference: https://labs.detectify.com/2021/08/10/how-to-hack-apis-in-2021/



