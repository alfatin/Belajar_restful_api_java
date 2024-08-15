# User Api Spec

## Register

Endpoint : POST /api/users

Request Body :
```json
{
  "username" : "alfatin",
  "password" : "qwerty",
  "name" : "Al Fatin Fernanda"
}
```
Respond Body (success) :
```json
{
  "data" : "ok"
}
```
Respond Body (failed) :
```json
{
  "message" : "errors"
}
```

## Login

Endpoint : POST /api/auth/login

Request Body :
```json
{
  "username" : "alfatin",
  "password" : "qwerty"
}
```
Respond Body (success) :
```json
{
  "data" : {
    "token" : "token",
    "expiredAt" : "12313214124312"
  }
}
```
Respond Body (failed) (401) :
```json
{
  "message" : "user or password wrong"
}
```

## Get User

Endpoint : GET /api/Users/current

Request Header :
- X-API-TOKEN : Token (Mandatory)

Respond Body (success) :
```json
{
  "data" : {
    "username" : "alfatin",
    "name" : "Al Fatin Fernanda"
  }
}
```

Respond Body (failed) (401) :
```json
{
  "message" : "unauthorized"
}
```

## Update User

Endpoint : PATCH /api/Users/current

Request Header :
- X-API-TOKEN : Token (Mandatory)

Request Body :
```json
{
  "name" : "alfatin",
  "password" : "new password"
}
```

Respond Body (success) :
```json
{
  "data" : {
    "username" : "alfatin",
    "name" : "Al Fatin Fernanda"
  }
}
```

Respond Body (failed) (401) :
```json
{
  "message" : "unauthorized"
}
```

## Logout

Endpoint : DELETE /api/auth/logout

Request Header :
- X-API-TOKEN : Token (Mandatory)

Respond Body (success) :
```json
{
  "data" : "ok"
}
```