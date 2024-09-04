# API Test: Verify Status after put method

## Request

URL: {{baseURI}}/{{objectParameter}}/{{objectID}}

Method: PUT

## Authorization

Type: Inherit from parent


## Variables

|Variable Name  |	Value                               |
|---------------|---------------------------------------|
|baseUrl	    |https://api.restful-api.dev            |
|objectParameter|objects                                |
|objectID       |ff80818191a25dfc0191a39dbe580307       |

## Body

{
 
   "name": "Apple MacBook Pro 16",
   
   "data": {
   
      "year": 2024,
      
      "price": 3000,
      
      "CPU model": "Intel Core i9",
      
      "Hard disk size": "1 TB",
      
      "color": "silver"
   
   }

}


## Tests
### // Verify status code is 200

`pm.test("Status code is 200", function () {`

 `   pm.response.to.have.status(200);`

`});`

