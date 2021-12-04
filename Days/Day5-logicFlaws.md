# Business Logic Flaws Vulnerability

Business Logic Flaws occurs when users pass values to the target which are not expected, the attack makes assumptions about the normal behavior of the functionalities and tries to pass values which can break the logic of the application. (Hard to look for, as you need to have a full understanding of the technologies and mechanisms used within the application)


## Development processes

	### Waterfall Model
		![waterfall](https://static.javatpoint.com/tutorial/jira/images/jira-waterfall-model.png)

	### V-Model
		![vmodel](https://miro.medium.com/max/676/1*1_y1njK_-OW_Sqv1cKlDcg.png)

	### Agile
		![agile](https://www.nvisia.com/hubfs/agile-methodology-chicago.png

***

## Countermeasures:

	- Developers must have a full understanding of the technologies being used/been used to perform any updates or changes, with the need of great documentation for every change. 
	- Avoid making implicit about user's behaviors dealing with functionalities of the application. 
	- Always make sure that the input is sanitized before being processed.

***

## Takeaways: 

	- Always look for the technologies and the functionalities that the application uses.(Read Documentations)