
the original app was written by an intern or whoever the lowest bidder could possibly be.

## retrieve the web api version:
```
GET https://passio3.com/www/goServices.php?goWebVer=1
```

## get every single service and its id:
```
GET https://passiogo.com/mapGetData.php?v=2&sortMode=1&credentials=1
```


## retrieve routes in the system:

```
POST https://passio3.com/www/mapGetData.php?getRoutes=1

data: x-www-form-urlencoded
json={"systemSelected0":"480","amount":1}
```
example reply:
```json
[
    {
        "name": "Charter Route",
        "shortName": "",
        "color": "#bdbdbd",
        "userId": "480",
        "myid": "6039",
        "mapApp": "1",
        "archive": "0",
        "goPrefixRouteName": "1",
        "goShowSchedule": 1,
        "outdated": "1",
        "id": "15390",
        "distance": 6,
        "latitude": "33.753574620",
        "longitude": "-84.385528187",
        "timezone": "America/New_York",
        "fullname": "Georgia State University",
        "nameOrig": "Charter Route",
        "groupId": "535",
        "groupColor": "#bdbdbd",
        "serviceTime": "is not provided: no bus on the route",
        "serviceTimeShort": "No bus in service"
    },
    {
        "name": "Purple Route",
        "shortName": "",
        "color": "#9467bd",
        "userId": "480",
        "myid": "44769",
        "mapApp": "1",
        "archive": "0",
        "goPrefixRouteName": "1",
        "goShowSchedule": 1,
        "outdated": "1",
        "id": "15393",
        "distance": 6,
        "latitude": "33.756749700",
        "longitude": "-84.389320055",
        "timezone": "America/New_York",
        "fullname": "Georgia State University",
        "nameOrig": "Purple Route",
        "groupId": "533",
        "groupColor": "#9467bd",
        "serviceTime": "is not provided: no bus on the route",
        "serviceTimeShort": "No bus in service"
    },
]
```

## get all stops
```
POST https://passio3.com/www/mapGetData.php?getStops=1
data: x-www-form-urlencoded
{"s0":"480","sA":1}
```
- `s0` - index zero of systems
- `sA` - transit systems included in result;

if `s1` is present, `sA` of 1 means only `s0` and `sA` of 2 is both `s0` and `s1`

example reply- shortened:

```json
{
    "stops": {
        "ID15397": {
            "routeId": "44770",
            "stopId": "15397",
            "position": "3",
            "name": "Student Center East",
            "latitude": 33.753031097,
            "longitude": -84.384821767,
            "id": "15397",
            "userId": "480",
            "radius": 46,
            "routeName": "Green Route",
            "routeShortname": "",
            "routeGroupId": 0
        },
        "ID15390": {
            "routeId": "44775",
            "stopId": "15390",
            "position": "3",
            "name": "Sparks Hall",
            "latitude": 33.75357462,
            "longitude": -84.385528187,
            "id": "15390",
            "userId": "480",
            "radius": 45,
            "routeName": "Blue Route",
            "routeShortname": null,
            "routeGroupId": 0
        },
        "ID15393": {
            "routeId": "44769",
            "stopId": "15393",
            "position": "3",
            "name": "Rialto Center",
            "latitude": 33.7567497,
            "longitude": -84.389320055,
            "id": "15393",
            "userId": "480",
            "radius": 50,
            "routeName": "Purple Route",
            "routeShortname": "",
            "routeGroupId": 0
        },
        "ID154947": {
            "routeId": "44772",
            "stopId": "154947",
            "position": "3",
            "name": "75 Piedmont",
            "latitude": 33.75659368,
            "longitude": -84.382142356,
            "id": "154947",
            "userId": "480",
            "radius": 50,
            "routeName": "Yellow Route",
            "routeShortname": null,
            "routeGroupId": 0
        },
        "ID154948": {
            "routeId": "44772",
            "stopId": "154948",
            "position": "4",
            "name": "Piedmont North",
            "latitude": 33.758535893,
            "longitude": -84.382136813,
            "id": "154948",
            "userId": "480",
            "radius": 50,
            "routeName": "Yellow Route",
            "routeShortname": null,
            "routeGroupId": 0
        },
        "ID154951": {
            "routeId": "44771",
            "stopId": "154951",
            "position": "2",
            "name": "Petit Science",
            "latitude": 33.751285,
            "longitude": -84.385499,
            "id": "154951",
            "userId": "480",
            "radius": 50,
            "routeName": "Orange Route",
            "routeShortname": null,
            "routeGroupId": 0
        }
    },
    "routes": {
        "6039": [
            "Charter Route",
            "#bdbdbd",
            [
                "1",
                "15397",
                0
            ],
            [
                "2",
                "15390",
                0
            ]
        ],
        "44769": [
            "Purple Route",
            "#9467bd",
            [
                "3",
                "15393",
                0
            ],
            [
                "4",
                "15397",
                0
            ],
            [
                "5",
                "154947",
                0
            ],
            [
                "7",
                "154948",
                0
            ]
        ],
        "44773": [
            "Blue Route",
            "#1f77b4",
            [
                "2",
                "15389",
                0
            ],
            [
                "3",
                "15390",
                0
            ],
            [
                "5",
                "154949",
                0
            ]
        ],
        "44774": [
            "Blue Route",
            "#1f77b4",
            [
                "2",
                "15389",
                0
            ],
            [
                "3",
                "15390",
                0
            ]
        ],
        "44775": [
            "Blue Route",
            "#1f77b4",
            [
                "2",
                "15389",
                0
            ],
            [
                "3",
                "15390",
                0
            ]
        ]
    },
    "routePoints": {
        "6039": [
            {
                "lat": "33.753031097",
                "lng": "-84.384821767"
            },
            {
                "lat": "33.753085301",
                "lng": "-84.384754291"
            },
            { ... }
        ]
    },
    "groupRoutes": {
        "480": {
            "6039": {
                "id": "535",
                "name": "Charter Route",
                "color": "#bdbdbd",
                "mapApp": "0",
                "userId": "480",
                "routeGroupId": "535"
            },
            "44769": {
                "id": "533",
                "name": "Purple Route",
                "color": "#9467bd",
                "mapApp": "0",
                "userId": "480",
                "routeGroupId": "533"
            },
            "44770": {
                "id": "532",
                "name": "Green Route",
                "color": "#2ca02c",
                "mapApp": "0",
                "userId": "480",
                "routeGroupId": "532"
            },
        }
    },
    "routeShortNames": {
        "6039": "",
        "44769": "",
        "44770": "",
        "44771": null,
        "44772": null,
        "44773": null,
        "44774": null,
        "44775": null,
        "1160": null,
        "4918": null,
        "4919": null,
        "4920": "",
        "4921": "",
        "4922": "",
        "4923": "",
        "4924": "",
        "7488": null,
        "7489": "",
        "12755": null,
        "14623": null,
        "21554": null,
        "44740": null,
        "44741": null
    },
    "routeSchedules": {
        "6039": "1",
        "44769": "1",
        "44770": "1",
        "44771": "1",
        "44772": "1",
        "44773": "1",
        "44774": "1",
        "44775": "1",
        "1160": "1",
        "4918": "1",
        "4919": "1",
        "4920": "1",
        "4921": "1",
        "4922": "1",
        "4923": "1",
        "4924": "1",
        "7488": "1",
        "7489": "1",
        "12755": "1",
        "14623": "1",
        "21554": "1",
        "44740": "1",
        "44741": "1"
    },
    "routesRR": [],
    "excludedRoutesID": [
        -1,
        6039,
        44769,
        44770,
        44773
    ],
    "stopsRR": []
}
```

## get position of all buses

```
POST https://passio3.com/www/mapGetData.php?getBuses=1
data: x-www-form-urlencoded
{"s0":"480","sA":1}
```

**TODO: make this request at an hour when buses are running**

example reply:
```json
{
    "buses": {
        "-1": [
            {
                "-1": []
            }
        ]
    },
    "excludedRoutes": [
        -1,
        6039,
        44769,
        44770,
        44773
    ],
    "time": {
        "480": "11:26 PM"
    }
}
```

## Get ETA for bus

```
GET https://passio3.com/www/mapGetData.php?eta=3&stopIds=15397&routeId=44770&position=3
```

- `eta` - TBD
- `stopIds` - id of bus stop
- `routeId` - id of bus route
- `position` - OPTIONAL? route version of stop? TBD

```json
{
    "ETAs": {
        "0000": [
            {
                "secondsSpent": 86400,
                "order": 86400,
                "eta": "no vehicles",
                "routeId": 44770,
                "goShowSchedule": 0,
                "busName": ""
            }
        ]
    },
    "originalRouteIds": [
        44770
    ],
    "time": "2023-09-03 11:43:47 PM",
    "mt": 0.007662057876586914
}
```


---
get issued a session token:
```
GET https://gsu.passiogo.com/goServices.php?register=1&deviceId=0&token=1&platform=web&buildNo=107&oldToken=
```

the page replies with a `Set-Cookie` Header containing something along the lines of the following:
```
tt=e722203b5df6ca; expires=Mon, 11-Sep-2023 00:24:50 GMT; Max-Age=604800
```
