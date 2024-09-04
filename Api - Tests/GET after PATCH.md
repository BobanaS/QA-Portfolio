# API Test: Verify partially update after PATCH method

## Request

URL: {{baseURI}}/{{objectParameter}}/{{objectID}}
Method: GET

## Authorization

Type: Inherit from parent


## Variables

|Variable Name  |	Value                               |
|---------------|-------------------------------------|
|baseUrl	      |https://api.restful-api.dev          |
|objectParameter|objects                              |
|objectID       |ff80818191a25dfc0191a39dbe580307     |

## Body

Empty: This GET request does not require a request body.


## Tests
### // Verify object partallz update

`pm.test("Name is Apple MacBook Pro 16 (Updated Bobana", function () {`
 `   var jsonData = pm.response.json();`
  `  pm.expect(jsonData.name).to.eql("Apple MacBook Pro 16 (Updated Bobana)");`
`});`
