# Error Codes

## HTTP Error Codes

The Appraisal.AI API uses the following HTTP error codes:

HTTP Error Code | Meaning
----------------------- | -----------
400 | Bad Request
401 | Unauthorized -- Username/password invalid -- Authentication token missing or invalid
404 | Not Found -- Invalid resource URI
405 | Method Not Allowed
500 | Internal Server Error


## JSON Error Codes

The Appraisal.AI API uses the following error codes in the JSON response data:

Error Code | Description | Corresponding HTTP Error Code
--------------- | --------------- | -------------------------------------------
1 | Missing parameters - Your request is missing a required parameter | 400
2 | Invalid parameters - One of the parameters in your request is invalid | 400
3 | Improperly formatted date - Date should be ISO 8601 format YYYY-MM-DD | 400
4 | Property not found | 200
5 | No valuation for this property | 200
6 | Invalid user credentials | 401
7 | Invalid token - Please re-authenticate | 401
8 | Usage limit exceeded | 403