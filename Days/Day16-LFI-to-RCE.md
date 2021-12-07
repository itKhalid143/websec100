# (LFI to RCE) via Log Poisoning Attack

It is a technique used to gain **remote command execution** on the webserver. The attacker needs to **include a malicious payload into services log files** such as Apache, SSH, etc. Then, the LFI vulnerability is used to request the **page that includes the malicious payload**.

- Injecting via User-Agent
```java
curl -A "testing" http://<Machine IP>/login.php
``` 

Then we're viewing the Log files! to check our executed command!

***

# (LFI to RCE) via PHP Sessions

The LFI to RCE via PHP sessions follows the same concept of the log poisoning technique.
- **PHP sessions** are **files** within the operating system that **store temporary information**.
	-After the user logs out of the web application, the PHP session information will be deleted.


## Attack Vector
- Enumerate to read the PHP configuration file.
- Then we can discover where the PHP sessions files are.
	- PHP stores session data in files within the system in different locations based on the configuration.
	- PHP, by default use the following sheme ```sess_<SESSION_ID>```, it's copied from the cookies.

	![****](/websec365/Days/Screenshots/Day16.PNG)

- Include a **PHP code into the session** and finally call the file via LFI

```
https://<Machine IP>/login.php?file=/tmp/sess_ogvclskuv4b4pllugqm0i9f6u5
```
### Common Locations where PHP store sessions:

```java
c:\Windows\Temp
/tmp/
/var/lib/php5
/var/lib/php/session
```
