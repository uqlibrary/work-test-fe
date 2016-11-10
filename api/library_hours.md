# REST API: Library Hours

## Resource URI

    https://app.library.uq.edu.au/api/library_hours/{mode}

## Resource Properties

If mode = day

| Property      | Description
| ------------- | -----------
| code          | Library code
| name          | Library name.
| abbr          | Library abbreviation.
| url           | Library url.
| open          | Library open time.
| close         | Library close time.
| notes         | Notes.


If mode = week

| Property      | Description
| ------------- | -----------
| code          | Library code
| name          | Library name.
| abbr          | Library abbreviation.
| url           | Library url.
| DD-MM-YYYY    | Object containing information for specific day

Day object format:

| Property      | Description
| ------------- | -----------
| dow           | Day of week abbreviation (Mon-Sun)
| open          | Library open time.
| close         | Library close time.



## HTTP GET

Returns an array of library hours in selected view mode {code}.

An optional query parameter can be added for JSONP requests
([read more](https://github.com/uqlibrary/uqlapp/blob/master/docs/api/jsonp-callback.md)):

    https://app.library.uq.edu.au/api/library_hours/{mode}?callback=aCallbackFn

Example usage:

```
curl \
  -H "Content-Type: application/json" \
  https://app.library.uq.edu.au/api/library_hours/day
```

If the request is successful a HTTP 200 response is returned with the following response body:

```json
[
  {
    "code": "arm",
    "name": "Architecture / Music Library",
    "abbr": "Arch Music",
    "url": "http://www.library.uq.edu.au/locations/architecture-music-library",
    "open": "09:00:00",
    "close": "17:00:00",
    "rev": "0"
  },
  {
    "code": "bio",
    "name": "Biological Sciences Library",
    "abbr": "Biol Sci",
    "url": "http://www.library.uq.edu.au/locations/biological-sciences-library",
    "open": "00:00:00",
    "close": "24:00:00",
    "rev": "0",
    "notes": "Walk in access from 7am to 8pm. Entry after 8pm UQ ID card necessary."
  }
]
```


```
curl \
  -H "Content-Type: application/json" \
  https://app.library.uq.edu.au/api/library_hours/week
```

If the request is successful a HTTP 200 response is returned with the following response body:

```json
[
    {
        "code": "arm",
        "name": "Architecture / Music Library",
        "abbr": "Arch Music",
        "url": "http://www.library.uq.edu.au/locations/architecture-music-library",
        "2015-01-23": {
            "dow": "Fri",
            "open": "09:00:00",
            "close": "17:00:00",
            "rev": "0"
        },
        "2015-01-24": {
            "dow": "Sat",
            "open": "00:00:00",
            "close": "00:00:00",
            "rev": "0"
        },
        "2015-01-25": {
            "dow": "Sun",
            "open": "00:00:00",
            "close": "00:00:00",
            "rev": "0"
        },
        "2015-01-26": {
            "dow": "Mon",
            "open": "00:00:00",
            "close": "00:00:00",
            "rev": "0"
        },
        "2015-01-27": {
            "dow": "Tue",
            "open": "09:00:00",
            "close": "17:00:00",
            "rev": "0"
        },
        "2015-01-28": {
            "dow": "Wed",
            "open": "09:00:00",
            "close": "17:00:00",
            "rev": "0"
        },
        "2015-01-29": {
            "dow": "Thu",
            "open": "09:00:00",
            "close": "17:00:00",
            "rev": "0"
        },
        "notes": "[Mon 26 Jan] Australia Day Public Holiday"
    },
    {
        "code": "bio",
        "name": "Biological Sciences Library",
        "abbr": "Biol Sci",
        "url": "http://www.library.uq.edu.au/locations/biological-sciences-library",
        "2015-01-23": {
            "dow": "Fri",
            "open": "00:00:00",
            "close": "24:00:00",
            "rev": "0"
        },
        "2015-01-24": {
            "dow": "Sat",
            "open": "00:00:00",
            "close": "24:00:00",
            "rev": "0"
        },
        "2015-01-25": {
            "dow": "Sun",
            "open": "00:00:00",
            "close": "24:00:00",
            "rev": "0"
        },
        "2015-01-26": {
            "dow": "Mon",
            "open": "00:00:00",
            "close": "24:00:00",
            "rev": "0"
        },
        "2015-01-27": {
            "dow": "Tue",
            "open": "00:00:00",
            "close": "24:00:00",
            "rev": "0"
        },
        "2015-01-28": {
            "dow": "Wed",
            "open": "00:00:00",
            "close": "24:00:00",
            "rev": "0"
        },
        "2015-01-29": {
            "dow": "Thu",
            "open": "00:00:00",
            "close": "24:00:00",
            "rev": "0"
        },
        "notes": "Walk in access from 7am to 8pm. Entry after 8pm UQ ID card necessary."
    }
]
```