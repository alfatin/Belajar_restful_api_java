# Contact API Spec

## Create Contact

Endpoint : POST /api/contacts

Request Header :
- X-API-TOKEN : Token (Mandatory)

Request Body :

```json
{
  "firstName" : "Al Fatin",
  "lastName" : "Fernanda",
  "email": "mail@mail.com",
  "phoneNumber" : "01238412233"
}
```

Response Body (Success):

```json
{
  "id" : "id contact",
  "firstName" : "Al Fatin",
  "lastName" : "Fernanda",
  "email": "mail@mail.com",
  "phoneNumber" : "01238412233"
}
```

Response Body (Failed):

```json
{
  "errors" : "invalid ..."
}
```

## Update Contact

Endpoint : PUT /api/contacts{id contact}

Request Header :
- X-API-TOKEN : Token (Mandatory)

Request Body :
```json
{
  "firstName" : "Al Fatin",
  "lastName" : "Fernanda",
  "email": "mail@mail.com",
  "phoneNumber" : "01238412233"
}
```

Response Body (Success):

```json
{
  "id" : "id contact",
  "firstName" : "Al Fatin",
  "lastName" : "Fernanda",
  "email": "mail@mail.com",
  "phoneNumber" : "01238412233"
}
```

Response Body (Failed {404}):

```json
{
  "errors" : "contact not found"
}
```

## Get Contact

Endpoint : GET /api/contacts

Query Param :
- name : string, contact first name or last name
- phone : string, phone number
- email : string, email user
- page : integer, start from 0
- size : integer, default 10 

Request Header :
- X-API-TOKEN : Token (Mandatory)

Request Body :

Response Body (Success):

```json
{
  "data": [
    {
      "id": "id contact",
      "firstName": "Al Fatin",
      "lastName": "Fernanda",
      "email": "mail@mail.com",
      "phoneNumber": "01238412233"
    },
    {
      "id": "id contact",
      "firstName": "Al Fatin",
      "lastName": "Fernanda",
      "email": "mail@mail.com",
      "phoneNumber": "01238412233"
    },
    {
      "id": "id contact",
      "firstName": "Al Fatin",
      "lastName": "Fernanda",
      "email": "mail@mail.com",
      "phoneNumber": "01238412233"
    }
  ],
  "paging" : {
    "currentPage" : 10,
    "totalPage" : 10,
    "size" : 10
  }
}

```

Response Body (Failed):

## Search Contact

Endpoint :

Request Header :
- X-API-TOKEN : Token (Mandatory)

Request Body :

Response Body (Success):

Response Body (Failed):

## Remove Contact

Endpoint : DELETE /api/contacts{id contact}

Request Header :
- X-API-TOKEN : Token (Mandatory)

Request Body :

Response Body (Success):

```json
{
  "data" : "OK"
}
```

Response Body (Failed):

```json
{
  "errors" : "contact not found"
}
```
