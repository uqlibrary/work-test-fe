# REST API: Computer Availability

## Resource URI

    https://app.library.uq.edu.au/api/computer_availability

## Resource Properties

| Property       | Description
| -------------- | -----------
| library        | The name of the library.
| buildingCode   | The building code to be used to call uqlsm map api
| buildingNumber | The building number if the building is on a UQ campus, otherwise 'null'.
| availability   | A map of computer availability in this library. The key is a level (or area) in the building, and the values are the current Available/Occupied counts

## HTTP GET

Returns the computer availability in libraries.

An optional query parameter can be added for JSONP requests
([read more](https://github.com/uqlibrary/uqlapp/blob/master/docs/api/jsonp-callback.md)):

    https://app.library.uq.edu.au/api/computer_availability?callback=aCallbackFn

Example usage:

```
curl \
  -H "Content-Type: application/json" \
  https://app.library.uq.edu.au/api/computer_availability
```

If the request is successful a HTTP 200 response is returned with the following response body:

```json
[
  {
    "library":"Architecture &amp; Music Library",
    "availability": {
      "Level 3": {
        "roomCode":"Lvl3",
        "Available":17,
        "Occupied":29
      }
    },
    "buildingCode":"Armus",
    "buildingNumber":51
  },
  {
    "library":"Biological Sciences Library",
    "availability":{
      "Level 1":{
        "roomCode":"Lvl1",
        "Available":4,
        "Occupied":27
      },
      "Level 2":{
        "roomCode":"Lvl2",
        "Available":7,
        "Occupied":83
      },
      "Level 3":{
        "roomCode":"Lvl3",
        "Available":4,
        "Occupied":31
      },
      "Level 4":{
        "roomCode":"Lvl4",
        "Available":9,
        "Occupied":36
      }
    },
    "buildingCode":"BSL",
    "buildingNumber":94
  },
  {
    "library":"D.H. Engineering &amp; Sciences Library",
    "availability":{
      "Level 1":{
        "roomCode":"Lvl1",
        "Available":4,
        "Occupied":14
      },
      "Level 2":{
        "roomCode":"Lvl2",
        "Available":23,
        "Occupied":35
      },
      "Level 3":{
        "roomCode":"Lvl3",
        "Available":8,
        "Occupied":21
      },
      "Level 4":{
        "Occupied":2,
        "roomCode":"Lvl4",
        "Available":0
      }
    },
    "buildingCode":"DHESL",
    "buildingNumber":50
  },
  {
    "library":"Duhig Building",
    "availability":{
      "Level 1":{
        "roomCode":"Lvl1",
        "Available":14,"Occupied":17
      },
      "Level 2":{
        "roomCode":"Lvl2",
        "Available":7,
        "Occupied":100
      },
      "Level 4":{
        "roomCode":"Lvl4",
        "Available":2,
        "Occupied":12
      },
      "Level 5":{
        "roomCode":"Lvl5",
          "Available":4,
        "Occupied":25
      }
    },
    "buildingCode":"Duhig",
    "buildingNumber":2
  },
  {
    "library":"Graduate Economics &amp; Business Library",
    "availability":{
      "Level 2":{
        "roomCode":"Lvl2",
        "Available":10,
        "Occupied":25
      }
    },
    "buildingCode":"Ecob",
    "buildingNumber":39
  },
  {
    "library":"Gatton Campus Library",
    "availability":{
      "Level 1":{
        "roomCode":"Lvl1",
        "Available":45,
        "Occupied":18},
      "Level 2":{
        "roomCode":"Lvl2",
        "Available":11,
        "Occupied":7
      }
    },
    "buildingCode":"Gatton",
    "buildingNumber":8102
  },
  {
    "library":"Herston Health Sciences Library",
    "availability":{
      "Level 6":{
        "roomCode":"Lvl6",
        "Available":28,
        "Occupied":15
      }
    },
    "buildingCode":"HSL",
    "buildingNumber":null
  },
  {
    "library":"Mater Hospital Library",
    "availability":{
      "Level 1":{
        "roomCode":"Lvl1",
        "Available":23,
        "Occupied":4
      }
    },
    "buildingCode":"Mater",
    "buildingNumber":null
  },
  {
    "library":"PACE Health Sciences Library",
    "availability":{
      "Level 6":{
        "roomCode":"Lvl6",
        "Available":39,
        "Occupied":26
      }
    },
    "buildingCode":"PACE",
    "buildingNumber":null
  },
  {
    "library":"Social Sciences &amp; Humanities Library",
    "availability":{
      "Level 1 Entry":{
         "roomCode":"Link",
         "Available":6,
         "Occupied":52
    },
      "Level 2":{
      "roomCode":"Lvl2",
        "Available":1,
        "Occupied":24
      },
      "Level 3":{
        "roomCode":"Lvl3",
        "Available":4,
        "Occupied":28
      },
      "Level 4":{
        "Occupied":15,
        "roomCode":"Lvl4",
        "Available":0
      }
    },
    "buildingCode":"SSAH",
    "buildingNumber":12
  }
]
```