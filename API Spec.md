# API Spec

## API User Domain

### Login API

Request :

- Method : POST
- Endpoint : `/v1/login`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- Body:

```json
{
  "phone": "string, required",
  "password": "string, required",
}
```

Response :

```json
{
  "status": "boolean",
  "message": "string",
  "data": {
    "id": "integer",
    "access_token": "string"
  },
  "meta": "object",
  "error": "array"
}
```

### Get User Profile

Request :

- Method : GET
- Endpoint : `/me`
- Header :
  - Content-Type: application/json
  - Accept: application/json
  - Bearer: "bearer access token"

Response :

```json
{
  "status": "boolean",
  "message": "string",
  "data": {
    "id": "integer",
    "name": "string",
    "email": "string",
    "phone": "string",
    "is_super_admin": "boolean",
    "status": "boolean"
  },
  "meta": "object",
  "error": "array"
}
```
## API Table Domain

### API Get Category

Request :

- Method : GET
- Endpoint : `/v1/category`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- Query Param :
  - query : optional
  - limit : required
  - page : required


Response :

```json
{
  "status": "boolean",
  "message": "string",
  "data": [
      {
        "id": "integer", 
        "name": "string",
        "created_at": "string",
        "updated_at": "string"
      }
  ],
  "meta": {
    "pagination": {
      "hasMorePages": "boolean",
      "next_cursor": "string",
      "next_page_url": "string",
      "prev_cursor": "string",
      "prev_page_url": "string"
    },
  "error": "array"
}
```

### API Get Category By ID

Request :

- Method : GET
- Endpoint : `/v1/category/:category_id`
- Header :
  - Content-Type: application/json
  - Accept: application/json


Response :

```json
{
  "status": "boolean",
  "message": "string",
  "data": {
    "id": "integer", 
    "name": "string",
    "created_at": "string",
    "updated_at": "string"
  },
  "meta": "object",
  "error": "array"
}
```
