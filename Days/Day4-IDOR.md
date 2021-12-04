# Insecure direct object reference Vulnerability

An insecure direct object reference (IDOR) is an access control vulnerability that occurs when an application exposes a reference to an internal implementation object, and the Attacker can access or modify those references, IDORs can manifest in both horizontal and vertical privilege escalation.


`GET /account/info?id=12`

`GET /backup/10.txt`

`POST /Credentials
	{UID:23,Email"example@test.com"}
`

![IDOR](https://securiumsolutions.com/blog/wp-content/uploads/2020/11/idor-1024x512.png)

***

## Countermeasures:

	- Replacing Direct Objects with Indirect Object References that are then internally mapped to actual objects.
		- Using a temporary per-session reference map populated.
	- Using secure hashes instead of actual object references.

***

## Takeaways: 

	- Changing parameters and see if you can get access to permitted features.
	- Look for parameters that could contain ID values.
	- Make sure to find leaked IDs from different OSINT Technologies.

