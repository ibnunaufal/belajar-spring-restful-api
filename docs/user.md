# User Api Specs

## Register User
Endpoint: POST ``/api/users``

Req Body
```json
{
  "username" : "bob99",
  "password" : "adadong",
  "name" : "Bob"
}
```

Resp Body Success
```json
{
  "data": "ok"
}
```

Resp Body Failed
```json
{
  "error": "error reason"
}
```


## Login User
Endpoint: POST ``/api/auth/login``

Req Body
```json
{
  "username" : "bob99",
  "password" : "adadong"
}
```

Resp Body Success
```json
{
  "data": {
    "token": "ISI TOKEN",
    "expiredAt": 123123 // millis
  }
}
```

Resp Body Failed
```json
{
  "error": "error reason"
}
```



## Update User
Endpoint: PATCH ``/api/users/current``

``~ PUT buat nimpa, jadi seluruh content harus dikirim semua ``

``~ PATCH buat ngganti yg mau diganti aja, ngga semua dikirim ``

Req Header:
- X-API-TOKEN: Token (mandatory)

Resp Body Success
```json
{
  "password" : "bob99",
  "name" : "Bob"
}
```

Resp Body Success
```json
{
  "username" : "bob99",
  "name" : "Bob"
}
```

Resp Body Failed 401
```json
{
  "error": "Unauthorized"
}
```


## Get User
Endpoint: GET ``/api/users/current``

Req Header:
- X-API-TOKEN: Token (mandatory)

Resp Body Success
```json
{
  "username" : "bob99",
  "name" : "Bob"
}
```

Resp Body Failed 401
```json
{
  "error": "Unauthorized"
}
```

## Logout User
Endpoint: DELETE ``/api/auth/logout``

Req Header:
- X-API-TOKEN: Token (mandatory)
  Resp Body Success
```json
{
  "data" : "ok"
}
```