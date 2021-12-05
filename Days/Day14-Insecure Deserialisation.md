# Insecure Desrialization Vulnerability
- Refers aswell to Object Injection.

Insecure deserialization is when user-controllable data is deserialized by a website. This potentially enables an attacker to manipulate serialized objects in order to pass harmful data into the application code.
- It does require decent knowledge of the programming languages in question but it can also occur very trivially if you have some knowledge of the programming languages.

![Serialisation](https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2016/01/serialize-deserialize-java.png)

## Serialization
- The processing complex structures such as objects into a much flatter format so that it can be sent and received in a sequential stream of bytes. 
	- This allows us to write complex data structures to memory, files or databases and also to send that data over the network to different API's.
	- When we serilalise data, we save it's attributes and their values, this is really important to remember. 
		- Example; ``` {lastname,firstname,ageage}```
			- ```O:4:"User":2:{s:4:"firstname":s:6:"john"; s:10:"isLoggedIn":b:1;}```
				```O:4:"User" - An object with the 4-character class name "User"
				2 - the object has 2 attributes
				s:4:"name" - The key of the first attribute is the 4-character string "name"
				s:6:"john" - The value of the first attribute is the 6-character string "john"
				s:10:"isLoggedIn" - The key of the second attribute is the 10-character string "isLoggedIn"
				b:1 - The value of the second attribute is the boolean value true```
	- ```Python``` refers to serialization as pickling
	- ```Ruby``` refers to serialization as marshalling
- Some might turn the objects into binary formats where others might use different string formats. 		- Some are easy to read, some are very hard to read

***

## Further topics to check on
- Binary insecure desiriliazation
- Gadget chains
- Creating your own exploit
- PHAR deserialization
- Deseriliazation using memory corruption


***

## Takeaways: 

- Always pay attention to cookies and Javascripts. 