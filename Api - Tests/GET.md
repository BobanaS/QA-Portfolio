# API Test: Verify Status and response time of All Posts

## Request

URL: {{baseURI}}/{{objectParameter}}
Method: GET

## Authorization

Type: Inherit from parent


## Variables

|Variable Name  |	Value                               |
|---------------|-------------------------------------|
|baseUrl	      |https://api.restful-api.dev          |
|objectParameter|objects                              |

##Body

Empty: This GET request does not require a request body.


## Tests
// Verify status code is 200
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

// Verify response time is less than 1000ms
pm.test("Verify response time is less than 1000ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(1000);
});
