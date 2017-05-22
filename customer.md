## Customer (/customer) - Get and Put Operations only.
Customer endspoint helps you to manage customer details. Request and Response format will be only in JSON format.

### Customer 
Customer resource represents following details

| Property | Type | As request | As response | Description |
| :-------------------- | :---------- | :-------------------- | :-------------------- | ------------------------------------------------------------ |
| id | String | `Optional` | `Returned always` | Its helps to identify customer resource. Value is combination of bpcp and unique id. |
| title | String | `Optional` | `Returned always` | Its helps to identify customer title value. |
| firstName | String  | `Optional` | `Returned always` | Its helps to identify customer first name value. |
| middleName | String | `Optional` | `Returned always` | Its helps to identify customer middle name value. |
| lastName | String | `Optional` | `Returned always` | Its helps to identify customer last name value. |
| emailRemainder | String | `Optional` | `Returned always` | Its helps to identify customer Email Remainder status . Value will be either 'Y' or 'N'. |
| smsRemainder|  String | `Optional` | `Returned always` | Its helps to identify customer SMS Remainder status. Value will be either 'Y' or 'N'. |
| phoneRemainder | String | `Optional` | `Returned always` | Its helps to identify customer Phone Remainder status.  Value will be either 'Y' or 'N'. |
| letterRemainder | String | `Optional` | `Returned always` | Its helps to identify customer Letter Remainder status. Value will be either 'Y' or 'N'. |
| phoneNumber | String| `Optional` | `Returned always` | Its helps to identify customer phone number value. |
| emailID | String | `Optional` | `Returned always` | Its helps to identify customer email value. |
| totalAccounts | String | `Optional` | `Returned always` | Its helps to identify customer total no. of accounts count value. |
| roleProfileID | String | `Optional` | `Returned always` | Its helps to identify customer role profile id value. |
| businessName | String | `Optional` | `Returned always` | Its helps to identify customer business name value. |
| password | String | `Optional` | `Not Required` | Its helps to identify customer password value. |


### Use cases

## Get customer [GET/customer/{id}] - Customer details found
## Parameters
	id - 	customer resource unique id

## Headers
 
         Authorization: Bearer {accesstoken}
         cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526
		
## Response 200 (application/json)
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
              "bpContactPersonNumber":"2005322484",
              "emailRemainder":"Y",
              "smsRemainder":"Y",
              "letterRemainder":"Y",
              "phoneRemainder":"Y",
              "emailID":"setupdddata20@bg.com",
              "phoneNumber":"",
              "totalAccounts":1,
              "roleProfileID":"RP02",
              "businessName":"St Edwards Church"
            }
          },
          "errors":{}
        }			
```

## Get customer [GET/customer/{id}] - Sap - Customer details not found
## Parameters
	id - 	customer resource unique id
## Headers
 
         Authorization: Bearer {accesstoken}
         cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526
	 
## Response 500 (application/json)
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
## Get customer [GET/customer/{id}] - Sap down
### Parameters
	id - 	customer resource unique id
	
## Headers
 
         Authorization: Bearer {accesstoken}
         cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526	
			
### Response 500 (application/json)
	
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

			
## Put customer [PUT/customer/]  - Successfully updated

## Request  (application/json) :
```json	
    {
        "customer":{  
            "id":"20053224845678",
            "emailRemainder":"Y",
            "smsRemainder":"Y",
            "letterRemainder":"Y",
            "phoneRemainder":"Y",
            "emailID":"setupdddata20@bg.com",
            "phoneNumber":"07288878888",
            "password":"password12"
        }

    }
```
## Headers
 
         Authorization: Bearer {accesstoken}
         cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526
## Response 200 (application/json)
```json
	
    {  
        "status":"SUCCESS",
        "data":{ 
            "customer":{  
                "id":"20053224845678",
                "emailRemainder":"Y",
                "smsRemainder":"Y",
                "letterRemainder":"Y",
                "phoneRemainder":"Y",
                "emailID":"setupdddata20@bg.com",
                "phoneNumber":"07288878888"

                 }
               },
        "errors":{}
    }
```
## Put customer [PUT/customer/] - Sap Error Scenarios


## Request  (application/json) :
```json	
            {
              "customer":{  
                  "id":"20053224845678",
                  "emailRemainder":"Y",
                  "smsRemainder":"Y",
                  "letterRemainder":"Y",
                  "phoneRemainder":"Y",
                  "emailID":"setupdddata20@bg.com",
                  "phoneNumber":"07288878888",
                  "password":"password12"
              }
            }
```
## Headers
 
         Authorization: Bearer {accesstoken}
         cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526
	 
## Response 500 (application/json)
	
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
## Put customer [PUT/customer/] - Sap down

## Request  (application/json) :
```json	
            {
              "customer":{  
                    "id":"20053224845678",
                    "emailRemainder":"Y",
                    "smsRemainder":"Y",
                    "letterRemainder":"Y",
                    "phoneRemainder":"Y",
                    "emailID":"setupdddata20@bg.com",
                    "phoneNumber":"07288878888",
                    "password":"password12"
               }

          }
						
```	
## Headers
 
         Authorization: Bearer {accesstoken}
         cid: 05e230bf-a9cf-4b31-bc54-d3a995f62526
	 
## Response 500 (application/json)
	
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
