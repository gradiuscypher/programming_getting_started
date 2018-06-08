# Working with APIs and Python `requests`

In this example, we'll work with some API examples that will show us how to use the Python library `requests` along with 3rd party APIs to get the information we're looking for.

## General Concepts

### Python Requests
`requests` is the library we're going to be using to make requests to various APIs via Python. Using requests is straight forward:

```python
# import the requests library for use
import requests

# perform a GET request to threatcrowd.org for some information
result = requests.get('https://www.threatcrowd.org/searchApi/v2/domain/report/?domain=riotgames.com')

# get the resulting HTTP status code, hopefully some 200 status
result_status = result.status_code

# get the JSON value that was sent to us
result_json = result.json()
```

## Threatgrid API
TODO

## Shodan API
TODO

## Riot API
TODO