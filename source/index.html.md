---
title: API Reference

language_tabs:
  - python
  - shell

toc_footers:
  - <a href='http://appraisal.ai/'>Sign Up for API access</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Appraisal.AI API. You can use our API to retreive housing valuations.

We have provided examples using Python and CURL. You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

> To authorize, use this code:

```python
import requests # The requests library: http://docs.python-requests.org

login_endpoint = 'https://housing2.rationalinsights.com:5000/get_auth_token'

login_request = requests.get(login_endpoint, auth=(username, password))

print login_request.json()
```

```shell
curl "https://housing2.rationalinsights.com:5000/get_auth_token"
  -u "username:password"
```

> The above command returns JSON structured like this:

```json
{
  "token": "eyJhbGciOiJIUzI1NiIsImV4cCI6MTQ5OTM2MTIxMSwiaWF0IjoxNDk5MzYxMDkxfQ.eyJ1c"
}
```
This endpoint requires a username and password and returns json containing a token that can be used to make requests to other endpoints for a limited amount of time. You can register for a username/password [here](http://appraisal.ai).

<aside class="info">
Make sure to replace <code>username</code> and <code>password</code> with your username and password.
</aside>

# Valuations

## Get Valuation

> To get a housing valuation, use this code:

```python
import requests # The requests library: http://docs.python-requests.org

valuation_endpoint = 'https://housing2.rationalinsights.com:5000/api/v1/getValuation'

data = {'address': '31724 Old Adams Road NE', 'city': 'Allegany', 'state': 'MD', 'zip': '33480'}

valuation_request = requests.post(valuation_endpoint, json=data, auth=(token, ''))

print valuation_request.json()
```

```shell
curl "https://housing2.rationalinsights.com:5000/api/v1/getValuation"
  -u "token:unused"
  -X POST
  -H "Content-Type: application/json"
  -d '{"address": "31724 Old Adams Road NE", "city": "Allegany", "state": "MD", "zip": "33480"}'
```

> The above command returns JSON structured like this:

```json
{
  "date": "2017-07-13T00:00:00",
  "valuation": 59000
}
```

This endpoint retrieves a specific valuation.

### HTTP Request

`POST https://housing2.rationalinsights.com:5000/api/v1/getValuation`

### Parameters

Parameter | Type | Required 
--------- | ---- | --------
address | json string | yes
city | json string | yes
state | json string | yes
zip | json string | yes

<aside class="info">
Make sure to replace <code>token</code> with the token you received from the authorization endpoint.
</aside>
