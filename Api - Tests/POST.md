# API Test: Verify Status after patch method

## Request

URL: {{baseURI}}/{{objectParameter}}

Method: POST

## Authorization

Type: Inherit from parent


## Variables

|Variable Name  |	Value                               |
|---------------|---------------------------------------|
|baseUrl	    |https://api.restful-api.dev            |
|objectParameter|objects                                |


## Body

{
 
   "name": "Apple MacBook Pro 16",
   
   "data": {
   
      "year": 2019,
      
      "price": 1849.99,
      
      "CPU model": "Intel Core i9",
      
      "Hard disk size": "1 TB"
   
   }

}


## Tests
### // Verify status code is 200
`pm.environment.set("objectID", pm.response.json().id );'
`pm.test("Status code is 200", function () {`

 `   pm.response.to.have.status(200);`

`});`

