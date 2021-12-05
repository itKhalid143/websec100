# File Inclusion Vulnerability


`GET /upload?name=../../../../../../../../../proc/self HTTP/1.1`

Remote File Inclusion (RFI) and Local File Inclusion (LFI) are vulnerabilities that are often found in poorly-written web applications. These vulnerabilities occur when a web application allows the user to submit input into files or upload files to the server.

- RFI vulnerabilities are easier to exploit but less common. Instead of accessing a file on the local machine, the attacker is able to execute code hosted on their own machine.

```php
$file = $_GET['file'];
include($file);
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
	- ../../../
- Windows:
	- %WINDIR%\win.ini

Check for more: https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/File%20Inclusion
***

## Filter Evasion:
- Encodings
	- Null byte Termination ***%00***
	- Double HTML Encoding
	- UFT-8 Encoding
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

