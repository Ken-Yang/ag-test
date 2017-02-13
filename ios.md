# Description
Please integrate with RESTful API using swift or Obj-C and implement the following features：

1. Login
2. Logout
3. Get member list
4. Create a member
5. Hamburger Menu (put the above feature (2,3,4) into this menu）
6. Auto extend token: the token will be revoked after 1 hour, please design a mechanism to auto extend/get token and make user feel nothing happened.


# API Doc
* Login
* Get Member List
* Create Member


## 1. Login APIs

#### Request

```
POST http://52.197.192.141:3443

{
 "name" : "ken",
 "pwd" : "hello"
 }
```

#### Response

```json
{
  "token": {
    "name": "ken",
    "iat": 1482748545,
    "exp": 1482766545,
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoia2VuIiwiaWF0IjoxNDgyNzQ4NTQ1LCJleHAiOjE0ODI3NjY1NDV9.BxQ5Ex7hhzXTMhb3EPl-9MdjFVy1ZCKLrGb19beaFns"
  }
}
```

&nbsp;



## 2. Get Member List

#### Request

```
Header
  Authorization: <TOKEN>

GET http://52.197.192.141:3443/member
```

#### Response

```json
{
  "data": [
    {
      "ID": 1,
      "name": "ken"
    },
    {
      "ID": 2,
      "name": "ken"
    },
    {
      "ID": 3,
      "name": "ken2"
    },
    {
      "ID": 4,
      "name": "ken3"
    }
  ]
}
```

&nbsp;


## 3. Create Member

#### Request

```
Header
  Authorization: <TOKEN>

POST http://52.197.192.141:3443/member

{
   "name" : "XXXXXXX"
}
```

#### Response

```json
{
  "code": "success"
}
```

&nbsp;


