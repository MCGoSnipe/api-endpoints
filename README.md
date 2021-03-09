# ENDPOINTS

## Authentication

Redirect users to [here](https://login.live.com/oauth20_authorize.srf?client_id=9abe16f4-930f-4033-b593-6e934115122f&response_type=code&redirect_uri=https%3A%2F%2Fapi.gosnipe.tech%2Fapi%2Fauthenticate&scope=XboxLive.signin%20XboxLive.offline_access) to authenticate.

Same response as refresh endpoint (shown below).
### Refresh

`GET /api/refresh?code=<refresh token>`
One of the 2 responses below:
```
{"error": null, "access_token": "JWT for Minecraft API", "refresh_token": "Refresh token for use with this API"}
{"error": "error descriptor here", "access_token": null, "refresh_token": null} // access token and refresh token arent provided if code isn't passed
```

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
