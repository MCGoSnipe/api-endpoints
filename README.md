# ENDPOINTS

## Status
`GET /api/status/name/<NAME>`
or
`GET /api/status/id/<UUID>`

NAME is the profile name, UUID is the UUID of the profile, with or without dashes.
```
{
  "status": "available"
}
```
```
{
  "status": "soon",
  "time": "2011-10-05T14:48:00.000Z"
}
```
```
{
  "status": "taken",
  "namemc": {
    "views": 0,
    "searches": 0,
    "skins": [
      "https://namemc.com/texture/14d2c366f0cd3a95.png"
    ],
    "linked": true,
    "friends": { //only shown if `linked` is true
      "count": 1,
      "list": {
        "MeMyselfAndI": "00000000-0000-0000-0000-000000000000"
      }
    },
    "socials": {}
  },
  "nameHistory": [
    {
      "name": "CoolNameXD",
      "changedToAt": 1
    },
    {
      "name": "Imagine"
    }
  ]
}
```
```
{
 "error": "error here"
}
```
