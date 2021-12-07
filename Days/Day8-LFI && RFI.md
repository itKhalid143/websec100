# File Inclusion Vulnerability


`GET /upload?name=../../../../../../../../../proc/self HTTP/1.1`

Remote File Inclusion (RFI) and Local File Inclusion (LFI) are vulnerabilities that are often found in poorly-written web applications. These vulnerabilities occur when a web application allows the user to include and read local files on the server.

- RFI vulnerabilities are easier to exploit but less common. Instead of accessing a file on the local machine, the attacker is able to execute code hosted on their own machine.

```php
$file = $_GET['file'];
include($file);
include();
require();
include_once(); 
require_once ();
```

## Differences between LFI & RFI
| LFI | RFI |
|---- | ----| 
|View Local files|View remote files|
|More Common|Less Common|
|Harder to exploit|Easier to exploit|


***

## Detection Payloads
- Linux:
	- /etc/passwd
	- ../../../ && ....//
- Windows:
	- %WINDIR%\win.ini

Check for more: https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/File%20Inclusion

***

## PHP Filter

- The PHP filter wrapper is used in LFI to read the actual PHP page content.
	- It is not possible to read a PHP file's content via LFI because PHP files get executed and never show the existing code. 
```php
php://filter/resource=file
filter/read=string.rot13/resource=file
php://filter/convert.base64-encode/resource=file
```

### Other PHP wrappers
- php://input
- php://output
- php://fd
- php://memory

#### Documentation : https://www.php.net/manual/en/wrappers.php.php

***
## Filter Evasion:
- Encodings
	- Null byte Termination ***%00***
	- Double HTML Encoding
	- UFT-8/Base64 Encoding
- Path & Dot Truncation

## Countermeasures:

- Validating User Input.
- Avoid Remote File Inclusion

***

## Takeaways: 

- Pay attention to the files that are :
	- Printed to a page.
	- Served as a download. (Downloaded through web application)
	- Parsed by Interpreter.
- Other entry points can be used depending on the web application, and where can consider the User-Agent, Cookies, session, and other HTTP headers.