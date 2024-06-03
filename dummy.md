# API Specification

## Introduction
This API allows users to manage their tasks.

## Base URL
`https://api.example.com`

## Authentication
This API requires JWT authentication. Include the token in the Authorization header.

## Endpoints

### Create Task
- **Method**: POST
- **Path**: `/tasks`
- **Parameters**: None
- **Request Body**:
  ```json
  {
      "title": "Task 1",
      "description": "Description of Task 1"
  }
  ```
- **Response**:
  ```json
  {
      "id": 1,
      "title": "Task 1",
      "description": "Description of Task 1",
      "completed": false
  }
  ```

### Get Task
- **Method**: GET
- **Path**: `/tasks/{taskId}`
- **Parameters**:
  - `taskId`: ID of the task
- **Request Body**: None
- **Response**:
  ```json
  {
      "id": 1,
      "title": "Task 1",
      "description": "Description of Task 1",
      "completed": false
  }
  ```

## Error Handling
- 400 Bad Request: Invalid request format.
- 401 Unauthorized: Authentication failed.

## Rate Limiting
This API enforces a rate limit of 100 requests per minute per user.

## Examples
### Create Task Example
#### Request
```http
POST /tasks HTTP/1.1
Host: api.example.com
Authorization: Bearer {token}
Content-Type: application/json

{
    "title": "Task 1",
    "description": "Description of Task 1"
}
```

#### Response
```http
HTTP/1.1 201 Created
Content-Type: application/json

{
    "id": 1,
    "title": "Task 1",
    "description": "Description of Task 1",
    "completed": false
}
```
