# Collabodraw API

The API handles login, user state, creating/removing canvases, and more.

This will eventually be an OpenAPI file, but I'll sketch out my API ideas in here for now.

-----

## Authentication

API calls are authenticated using a cookie. This cookie is obtained by calling the `/login/cookie` endpoint with the uer's username and password.

### GET `/login/cookie`

Logs into the given account and provides an authentication cookie in response.

**Auth:** HTTP Basic with user's `username : password`

Returns 200 if successful, with the `cd.auth` cookie set to authenticate both API requests and Canvas protocol connections, and the following json:

```jsonc
{
  "ok": true
}
```

Returns 401 if unsuccessful, with the following json:

```jsonc
{
  "ok": false,
  "error_message": "Human-readable message stating that the login failed. Display this!"
}
```

-----

## Registration

### POST `/user`

Creates a new user account.

**Auth:** Optional HTTP Basic with guest ID as the `username` and guest token as `password`. If given, owned layers/drawings will be transferred to new account.

**Body:**

```jsonc
{
  ...
}
```

Returns 201 if successful, with the `cd.auth` cookie set to authenticate both API requests and Canvas protocol connections for the new user, and the following json:

```jsonc
{
  "ok": true,
  ...
}
```

Returns 400 if unsuccessful, with the following json:

```jsonc
{
  "ok": false,
  "error_message": "Human-readable message stating why account creation failed. Display this!"
}
```

-----

## Canvases

### POST `/canvas`

Creates a new canvas.

**Auth:** ...tbd once we work out guest vs logged-in handling

**Body:**

```jsonc
{
  ...
}
```

Returns 201 if successful, with the following json:

```jsonc
{
  "ok": true,
  ...
}
```

Returns 400 if unsuccessful, with the following json:

```jsonc
{
  "ok": false,
  "error_message": "Human-readable message stating why canvas creation failed. Display this!"
}
```
