# REST API: Library Hours V2

## Resource URI

    https://app.library.uq.edu.au/api/v2/library_hours/{mode}

## Parameters

| Parameter  | Required | Default | Description
| ---------  | -------- | ------- | -----------
| iid        | Optional | 3633    | Institution id
| lid        | Optional | 0       | Entity id
| weeks      | Optional | 1       | Number of weeks of data, works on week mode only

## Resource Properties

If mode = day

| Property      | Description
| ------------- | -----------
| lid           | Library id.
| name          | Library name.
| category      | Entity category: library or department.
| day           | Day of the week.
| desc          | Library description.
| url           | Library url.
| contact       | Library contact info.
| fn            | Footnotes.
| lat           | Library latitude.
| long          | Library longitude.
| abbr          | Library abbreviation
| times         | Library additional notes.
| departments   | Library departments, e.g. AskUs Service Point, Study Area

Department Object:

| Property      | Description
| ------------- | -----------
| lid           | Department id.
| name          | Department name.
| category      | Entity category: library or department.
| day           | Day of the week.
| desc          | Department description.
| url           | Department url.
| contact       | Department contact info.
| fn            | Footnotes.
| lat           | Department latitude.
| long          | Department longitude.
| parent_lid    | Library id where the department belongs.
| rendered      | Library open and close time, e.g. 8am - 6pm or 24 Hours
| open          | Library open time, e.g. 08:00:00
| close         | Library close time, e.g. 18:00:00
| times         | Library current opening status and official hours

Times object:

| Property       | Description
| -------------  | -----------
| currently_open | Library current opening status , e.g. false, true
| status         | Library status on that day, e.g. open, close
| hours          | Library open and close time, e.g. 8am, 6pm

If mode = week

| Property      | Description
| ------------- | -----------
| lid           | Library id.
| name          | Library name.
| category      | Entity category: library or department.
| day           | Day of the week.
| desc          | Library description.
| url           | Library url.
| contact       | Library contact info.
| fn            | Footnotes.
| lat           | Library latitude.
| long          | Library longitude.
| abbr          | Library abbreviation
| weeks         | Additional notes on each day of the week
| departments   | Library departments, e.g. AskUs Service Point, Study Area

Department object:

| Property      | Description
| ------------- | -----------
| lid           | Department id.
| name          | Department name.
| category      | Entity category: library or department.
| day           | Day of the week.
| url           | Department url.
| desc          | Department description.
| parent_lid    | Library id where the department belongs.
| weeks         | Department opening hours and opening status through out the week, first day in a week is Monday

Week object:

| Property         | Description
| ---------------  | -----------
| {Day of the week}| Monday to Sunday
| date             | Date e.g. 2016-8-22
| times            | Department currently opening status and official hours
| rendered         | Department open and close time, e.g. 8am - 6pm or 24 Hours
| open             | Department open time, e.g. 08:00:00
| close            | Department close time, e.g. 18:00:00


## HTTP GET

Returns an array of library hours in selected view mode {code}.

An optional query parameter can be added for JSONP requests
([read more](https://github.com/uqlibrary/uqlapp/blob/master/docs/api/jsonp-callback.md)):

    https://app.library.uq.edu.au/api/v2/library_hours/{mode}?callback=aCallbackFn

Example usage:

```
curl \
  -H "Content-Type: application/json" \
  https://app.library.uq.edu.au/api/v2/library_hours/day
```

If the request is successful a HTTP 200 response is returned with the following response body ([Complete Api Response](https://sirius.library.uq.edu.au/libshare/ISRS/All_Teams/API/library_hours/library_hours_v2_day.json)):

```json
{
  "locations": [
    {
      "lid": 3823,
      "name": "Architecture & Music Library",
      "category": "library",
      "day": "Tuesday",
      "desc": "",
      "url": "https://web.library.uq.edu.au/locations-hours/architecture-music-library",
      "contact": "",
      "fn": "",
      "lat": "",
      "long": "",
      "color": "#1C6DBD",
      "times": {
        "currently_open": false,
        "status": "text",
        "text": " "
      },
      "rendered": " ",
      "abbr": "Arch Music",
      "departments": [
        {
          "lid": 3828,
          "name": "AskUs Service Point",
          "category": "department",
          "day": "Tuesday",
          "desc": "",
          "url": "",
          "contact": "",
          "lat": "",
          "long": "",
          "color": "#000000",
          "parent_lid": 3823,
          "times": {
            "currently_open": true,
            "status": "open",
            "hours": [
              {
                "from": "8am",
                "to": "6pm"
              }
            ]
          },
          "rendered": "8am - 6pm",
          "open": "08:00:00",
          "close": "18:00:00"
        }
      ]
    }
  ]
}
```


```
curl \
  -H "Content-Type: application/json" \
  https://app.library.uq.edu.au/api/v2/library_hours/week
```

If the request is successful a HTTP 200 response is returned with the following response body ([Complete Api Response](https://sirius.library.uq.edu.au/libshare/ISRS/All_Teams/API/library_hours/library_hours_v2_week.json)):

```json
{
  "locations": [
    {
      "lid": 3823,
      "name": "Architecture & Music Library",
      "category": "library",
      "desc": "",
      "url": "https://web.library.uq.edu.au/locations-hours/architecture-music-library",
      "contact": "",
      "fn": "",
      "lat": "",
      "long": "",
      "color": "#1C6DBD",
      "weeks": [
        {
          "Monday": {
            "times": {
              "currently_open": false,
              "status": "text",
              "text": " "
            },
            "date": "2016-08-22",
            "rendered": " "
          },
          "Tuesday": {
            "times": {
              "currently_open": false,
              "status": "text",
              "text": " "
            },
            "date": "2016-08-23",
            "rendered": " "
          },
          "Wednesday": {
            "times": {
              "currently_open": false,
              "status": "text",
              "text": " "
            },
            "date": "2016-08-24",
            "rendered": " "
          },
          "Thursday": {
            "times": {
              "currently_open": false,
              "status": "text",
              "text": " "
            },
            "date": "2016-08-25",
            "rendered": " "
          },
          "Friday": {
            "times": {
              "currently_open": false,
              "status": "text",
              "text": " "
            },
            "date": "2016-08-26",
            "rendered": " "
          },
          "Saturday": {
            "times": {
              "currently_open": false,
              "status": "text",
              "text": " "
            },
            "date": "2016-08-27",
            "rendered": " "
          },
          "Sunday": {
            "times": {
              "currently_open": false,
              "status": "text",
              "text": " "
            },
            "date": "2016-08-28",
            "rendered": " "
          }
        }
      ],
      "abbr": "Arch Music",
      "departments": [
        {
          "lid": 3828,
          "name": "AskUs Service Point",
          "category": "department",
          "parent_lid": 3823,
          "desc": "",
          "url": "",
          "contact": "",
          "lat": "",
          "long": "",
          "color": "#000000",
          "weeks": [
            {
              "Monday": {
                "times": {
                  "currently_open": false,
                  "status": "open",
                  "hours": [
                    {
                      "from": "8am",
                      "to": "6pm"
                    }
                  ]
                },
                "date": "2016-08-22",
                "rendered": "8am - 6pm",
                "open": "08:00:00",
                "close": "18:00:00"
              },
              "Tuesday": {
                "times": {
                  "currently_open": true,
                  "status": "open",
                  "hours": [
                    {
                      "from": "8am",
                      "to": "6pm"
                    }
                  ]
                },
                "date": "2016-08-23",
                "rendered": "8am - 6pm",
                "open": "08:00:00",
                "close": "18:00:00"
              },
              "Wednesday": {
                "times": {
                  "currently_open": false,
                  "status": "open",
                  "hours": [
                    {
                      "from": "8am",
                      "to": "6pm"
                    }
                  ]
                },
                "date": "2016-08-24",
                "rendered": "8am - 6pm",
                "open": "08:00:00",
                "close": "18:00:00"
              },
              "Thursday": {
                "times": {
                  "currently_open": false,
                  "status": "open",
                  "hours": [
                    {
                      "from": "8am",
                      "to": "6pm"
                    }
                  ]
                },
                "date": "2016-08-25",
                "rendered": "8am - 6pm",
                "open": "08:00:00",
                "close": "18:00:00"
              },
              "Friday": {
                "times": {
                  "currently_open": false,
                  "status": "open",
                  "hours": [
                    {
                      "from": "8am",
                      "to": "5pm"
                    }
                  ]
                },
                "date": "2016-08-26",
                "rendered": "8am - 5pm",
                "open": "08:00:00",
                "close": "17:00:00"
              },
              "Saturday": {
                "times": {
                  "currently_open": false,
                  "status": "open",
                  "hours": [
                    {
                      "from": "1pm",
                      "to": "5pm"
                    }
                  ]
                },
                "date": "2016-08-27",
                "rendered": "1pm - 5pm",
                "open": "13:00:00",
                "close": "17:00:00"
              },
              "Sunday": {
                "times": {
                  "currently_open": false,
                  "status": "closed"
                },
                "date": "2016-08-28",
                "rendered": "Closed"
              }
            }
          ]
        }
      ]
    }
  ]
}
```
