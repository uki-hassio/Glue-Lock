# Glue-Lock

// New to home assistant, so I have not made a nifty intigration YET - might come in to future, but this works for me so far. 


You have som attributes:  
**USERNAME** = Your Glue lock username  
**PASSWORD** = Your Glue lock passowrd  
**LOCK_ID** = your uniqe lock ID hash  
**HUB_ID** = Your uniqe hub ID hash  

##GETTING LOCK_ID & HUB_ID
Open any webbrowser surf to:   
https://api.gluehome.com/api/Hubs/  

Enter your credentials eg. Username and password  
Response would be something like:  
```
[
	{
		"Id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
		"SerialNumber": "GH01A.AL1849.0245",
		"Status": 2,
		"Description": "GH01A.AL1849.0245",
		"FirmwareVersion": "2.96",
		"HardwareVersion": "1",
		"Created": "2019-12-20T14:59:16.33",
		"BusyUntil": null,
		"LastCommunication": "2020-05-27T01:04:02.703",
		"OwnerId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
		"LockIds": [
			"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
		],
		"AvailableFirmwareVersion": "2.96"
	}
]
```
Id: = HUB_ID  
LockId: = LOCK_ID  
  
Insert into your configuration.yaml  
Restart HASSIO  
And you should have Entities to read batterystatus and be able to lock/unlock  

NOTE.  
* There is no way to se locked status. Only assume last locked state.

