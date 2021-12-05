# Command Injection Vulnerability

Command injection is a cyber attack that involves executing arbitrary commands on a host operating system (OS)

!Sample RCE](https://farm1.staticflickr.com/882/41036646032_7fe328f7b2_b.jpg)

## Attack Strategy:

- We have to fuzz every possible parameter to find a process that will trigger the back end shell.

#### Commands Separators
- ```&```
- ```&&```
- ```|```
- ```||```
- ```;```
- Linux based
	- ```0x0a```,```\n```,``` `id` ```, $(id)


### Usefull Commands
| Linux Command		| Windows Command		|Description		|
|----|-----|-------|
|whoami |whoami | current user|
|uname -a |ver  |print the OS|
|ifconfig |ipconfig /all |Network Configuration|
| netstat -an|netstat -an |Network Configuration|
|ps -ef|tasklist |Runnng processes |

## Blind Command Injection
- We can test for blind command injection by launching a request that will execute a
ping command to the loopback address.
	- If longer than 10 seconds, we probably have a blind command injection, which can be a false positive as well.
```& ping -c 10 127.0.0.1 &
```