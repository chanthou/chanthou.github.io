URL: http://dev.idcrm.com/antar-dev/login
Method: Post

**Request login**

```
#!json

{
email: "dev@idcrm.com",
password: "123456"
}
```

** Sucess Response**

```
#!json

{"token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiIxIiwiaXNzIjoiaHR0cDpcL1wvZGV2LmlkY3JtLmNvbVwvYW50YXItZGV2XC9sb2dpbiIsImlhdCI6MTQ1MTM4MzQzMSwiZXhwIjoxNDUyNTkzMDMxLCJuYmYiOjE0NTEzODM0MzEsImp0aSI6ImI2YzgwZGRlZTBlNzI3N2U0YThkYzhiZDdhYzNiNGEwIn0.ujAd9isvRSBr_wKFPp5Y2ayR0T0o8L2e8bKAaOVnqlA"}
```

** Fail Response **

```
#!json

{
  "error": "token_invalid"
}
```