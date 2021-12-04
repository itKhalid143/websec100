# Broken Access Control Vulnerability

Broken Access Control is an attack vector, allows the attack to perform actions (whether from the Application Functionalities, Accessing Resources) outside of its intended permissions.

`http://site.com/info?id=differentID`

`http://site.com/admin/view/`

`http://site.com/admin/add?isAdmin=true`


![BAC](https://cdn.packetlabs.net/wp-content/uploads/2019/10/29102102/broken-access-control.png)

## Types of Broken Access Control: 

- Vertical access controls
	- The Attacker has access to different application functions. For example, He is able to modify or delete any user's account, which those commands are made for the Administrator role. (Users with different access levels)
- Horizontal access controls
	- The Attacker has restricted access to resources to the users who are intended to access those resources. (Resources of the same type)

***

## Takeaways: 

- Must acknowledge our target technologies and functionalities.
- Writing down every possible role.