## Customers (/customers) - Get and Put Operations only.
Customers end point helps you to manage customer details. Request and Response format will be only in JSON format.

### Customers 
Customers resource represents following details

| Property | Type | As request | As response | Description |
| :-------------------- | :---------- | :-------------------- | :-------------------- | ------------------------------------------------------------ |
| id | String | `Optional` | `Returned always` | Its helps to identify customer resource. Value is combination of bpcp and unique id. |
| title | String | `Optional` | `Returned always` | Its helps to identify customer title value. |
| firstName | String  | `Optional` | `Returned always` | Its helps to identify customer first name value. |
| middleName | String | `Optional` | `Returned always` | Its helps to identify customer middle name value. |
| lastName | String | `Optional` | `Returned always` | Its helps to identify customer last name value. |
| emailReminderOpt | Boolean | `Optional` | `Returned always` | Its helps to identify customer Email Reminder status . Value will be either True or False. |
| smsReminderOpt|  Boolean | `Optional` | `Returned always` | Its helps to identify customer SMS Reminder status. Value will be either True or False. |
| phoneReminderOpt | Boolean | `Optional` | `Returned always` | Its helps to identify customer Phone Reminder status.  Value will be either True or False. |
| letterReminderOpt | Boolean | `Optional` | `Returned always` | Its helps to identify customer Letter Reminder status. Value will be either True or False. |
| phoneNumber | PhoneNumber| `Optional` | `Returned always` | Its helps to identify customer phone number value. |
| emailAddress | String | `Optional` | `Returned always` | Its helps to identify customer email value. |
| roleProfile | String | `Optional` | `Returned always` | Its helps to identify customer role profile value. |
| businessName | String | `Optional` | `Returned always` | Its helps to identify customer business name value. |

##### PhoneNumber

| Name | Type | As request | As response | Description |
| :---------- | :------ | -------- |---------|------------------------------------ |
| number | string | `Mandatory`| `Returned always` | Valid Phone number applicable. |
| type | string | `Optional` | `Returned always` |Phone number type, it can be `home`, `work`, `mobile`|


### Use cases


#### Get customers [GET/customers] - Customer details found

Headers
 
         Authorization: Bearer {accesstoken}
         cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526
		
Response 200 (application/json)
```json
	{  
		"status":"SUCCESS",
		"data":{  
		"customer":[  
			{  
				"id":"20053224845678",
				"firstName":"Asd",
				"middleName":"",
				"lastName":"Asd",
				"title":"Mr",
				"emailReminderOpt":true,
				"smsReminderOpt":true,
				"letterReminderOpt":true,
				"phoneReminderOpt":true,
				"emailAddress":"setupdddata20@bg.com",
				"phoneNumber":{  
				"number":"07404669698",
				"type":null
					},
				"roleProfile":"RP02",
				"businessName":"St Edwards Church"
			}
			]
			},
		"errors":{}
	}
```





#### Get customers [GET/customers/{id}] - Customer details found
 Parameters
	
	id - 	customer resource unique id

 Headers
 
         Authorization: Bearer {accesstoken}
         cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526
		
 Response 200 (application/json)
```json
	{  
		"status":"SUCCESS",
		"data":{  
		"customer":{  
			"id":"20053224845678",
			"firstName":"Asd",
			"middleName":"",
			"lastName":"Asd",
			"title":"Mr",
			"emailReminderOpt":true,
			"smsReminderOpt":true,
			"letterReminderOpt":true,
			"phoneReminderOpt":true,
			"emailAddress":"setupdddata20@bg.com",
			"phoneNumber":{  
			"number":"07404669698",
			"type":null
			},
			"roleProfile":"RP02",
			"businessName":"St Edwards Church"
			}
			},
		"errors":{}
	}		
```
### Error Scenarios

#### Get customers [GET/customers] - Sap - Customer details not found

 Headers
 
         Authorization: Bearer {accesstoken}
         cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526
	 
 Response 200 (application/json)
```json
    {  
        "status":"SUCCESS",
        "data":{ },
        "errors":{}
    }
 ```   


#### Get customers [GET/customers/{id}] - Sap - Customer details not found
 Parameters
	
	id - 	customer resource unique id
	
 Headers
 
         Authorization: Bearer {accesstoken}
         cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526
	 
 Response 404 (application/json)
```json
    {  
        "status":"FAILURE",
        "data":{ },
        "errors":{  
            "code":"Failure",
            "message":"error.customer.not.found"
         }
    }
 ```   
#### Get customers [GET/customers/{id}] - Sap down

 Parameters
 
	id - 	customer resource unique id
	
 Headers
 
         Authorization: Bearer {accesstoken}
         cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526	
			
 Response 500 (application/json)
	
```json	
        {  
          "status":"FAILURE",
          "data":{},
          "errors":{  
            "code":"Server Failure",
            "message":"error.sap.pi.operation.failure"
          }
        }
```	


#### Get customers [GET/customers] - Sap down

 Headers
 
         Authorization: Bearer {accesstoken}
         cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526	
			
 Response 500 (application/json)
	
```json	
        {  
          "status":"FAILURE",
          "data":{},
          "errors":{  
            "code":"Server Failure",
            "message":"error.sap.pi.operation.failure"
          }
        }
```	


			
#### Put customers [PUT/customers/{id}]  - Successfully updated

 Parameters
 
	id - 	customer resource unique id

 Request  (application/json) :
```json	
	{
		"customer":{  
			"id":"20053224845678",
			"emailReminderOpt": true,
			"smsReminderOpt": true,
			"letterReminderOpt": true,
			"phoneReminderOpt": true,
			"emailAddress":"setupdddata20@bg.com",
			"phoneNumber": {
				"number": "07404669698",
				"type": null
				}

			}

	}
```
Headers
 
         Authorization: Bearer {accesstoken}
         cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526
Response 200 (application/json)
```json
	
	{  
		"status":"SUCCESS",
		"data":{ 
			"customer":{  
				"id":"20053224845678",
				"emailReminderOpt": true,
				"smsReminderOpt": true,
				"letterReminderOpt": true,
				"phoneReminderOpt": true,
				"emailAddress":"setupdddata20@bg.com",
				"phoneNumber": {
					"number": "07404669698",
					"type": null
					}

				}
			},
		"errors":{}
	}
```
### Error Scenarios
#### Put customers [PUT/customer/{id}] - Sap Error Scenarios

 Parameters
 
	id - 	customer resource unique id

 Request  (application/json) :
```json	
	{
		"customer":{  
				"id":"20053224845678",
				"emailReminderOpt": true,
				"smsReminderOpt": true,
				"letterReminderOpt": true,
				"phoneReminderOpt": true,
				"emailAddress":"setupdddata20@bg.com",
				"phoneNumber": {
					"number": "07404669698",
					"type": null
						}

		}
	}
```
Headers
 
         Authorization: Bearer {accesstoken}
         cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526
	 
Response 404 (application/json)
	
```json
		{  
			  "status":"FAILURE",
			  "data":{ },
			  "errors":{ 
			      "code":"Failure",
			      "message":"error.customer.updation.failure"
			  }
		}				
```
#### Put customers [PUT/customer/{id}] - Sap down

Parameters

	id - 	customer resource unique id

Request  (application/json) :
```json	
	{
		"customer":{  
				"id":"20053224845678",
				"emailReminderOpt": true,
				"smsReminderOpt": true,
				"letterReminderOpt": true,
				"phoneReminderOpt": true,
				"emailAddress":"setupdddata20@bg.com",
				"phoneNumber": {
					"number": "07404669698",
					"type": null
						}

			}

	}
						
```	
Headers
 
         Authorization: Bearer {accesstoken}
         cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526
	 
Response 500 (application/json)
	
```json	
            {  
                  "status":"FAILURE",
                  "data":{},
                  "errors":{ 
                          "code":"Server Failure",
                          "message":"error.sap.pi.operation.failure"
                  }
            }			
									
```			

#### Post customers [POST/customers/resetpassword/{id}]  - Successfully updated

 Parameters
 	
	id - 	customer resource unique id
	

 Request  (application/json) :
```json	
    {
        "customer":{  
            "id":"20053224845678",
            "emailAddress":"setupdddata20@bg.com",
            "password":"password12"           
        }

    }
```
Headers
 
         Authorization: Bearer {accesstoken}
         cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526
Response 200 (application/json)
```json
	
    {  
        "status":"SUCCESS",
        "data":{ 
            "customer":{  
			    "id":"20053224845678",
			    "emailAddress":"setupdddata20@bg.com",
			    "password":"password12"  

                 	}
               },
        "errors":{}
    }
```




### Error Scenarios
#### Post customers [POST/customers/resetpassword/{id}] - DB Error Scenarios

 Parameters
 
	id - 	customer resource unique id

 Request  (application/json) :
```json	
            {
              "customer":{  
                  "id":"20053224845678",
                  "emailAddress":"setupdddata20@bg.com",
                  "password":"password12"  
              
              }
            }
```
Headers
 
         Authorization: Bearer {accesstoken}
         cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526
	 
Response 404 (application/json)
	
```json
        {  
          "status":"FAILURE",
          "data":{ },
          "errors":{ 
              "code":"Failure",
              "message":"error.customer.password.updation.failure"
          }
        }				
```
#### POST customers [POST/customers/resetpassword/{id}] - DB down

Parameters

	id - 	customer resource unique id

Request  (application/json) :
```json	
           {
              "customer":{  
                  "id":"20053224845678",
                  "emailAddress":"setupdddata20@bg.com",
                  "password":"password12"  
              
              }
            }
						
```	
Headers
 
         Authorization: Bearer {accesstoken}
         cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526
	 
Response 500 (application/json)
	
```json	
            {  
                  "status":"FAILURE",
                  "data":{},
                  "errors":{ 
                          "code":"DB Failure",
                          "message":"error.db.operation.failure"
                  }
            }			
									
```		
			
