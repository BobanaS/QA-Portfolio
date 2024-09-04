# API Test: Verify Status and object with ID has been deleted

## Request

URL: {{baseURI}}/{{objectParameter}}/{{objectID}}

Method: DELETE

## Authorization

Type: Inherit from parent


## Variables

|Variable Name  |	Value                               |
|---------------|-------------------------------------|
|baseUrl	      |https://api.restful-api.dev          |
|objectParameter|objects                              |
|objectID       |ff80818191a25dfc0191a39dbe580307     |

## Body

Empty: This DELETE request does not require a request body.


## Tests
### // Verify status code is 200

```pm.test("Status code is 200", function () {

    pm.response.to.have.status(200);

});```

### // Verify object with ID has been deleted

```pm.test("Object with id has been deleted", function () {

    var jsonData = pm.response.json();

    pm.expect(jsonData.message).to.contains("Object with id");

});```

