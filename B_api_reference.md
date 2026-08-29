# Exercise B: API Reference Entry

# Create a New Task

## Overview

The **Create a New Task** endpoint allows an authenticated user to create a new task inside a specific project in a project management application.

The user must provide a task title, assignee, due date, and priority. A description can optionally be included.

---

## HTTP Method

```text
POST
```

## Endpoint

```text
/api/v1/projects/{projectId}/tasks
```

## Description

Creates a new task in the specified project and returns the newly created task.

---

## Path Parameters

| Parameter   | Type   | Required | Description                                                      |
| ----------- | ------ | -------- | ---------------------------------------------------------------- |
| `projectId` | string | Yes      | Unique identifier of the project where the task will be created. |

---

## Query Parameters

This endpoint does not require any query parameters.

---

## Request Headers

| Header          | Required | Description                                          |
| --------------- | -------- | ---------------------------------------------------- |
| `Authorization` | Yes      | Authentication token in the format `Bearer <token>`. |
| `Content-Type`  | Yes      | Must be `application/json`.                          |
| `Accept`        | Yes      | Specifies that the client expects a JSON response.   |

---

## Request Body

The request body must be a JSON object containing the following fields:

| Field         | Type   | Required | Description                                                          |
| ------------- | ------ | -------- | -------------------------------------------------------------------- |
| `title`       | string | Yes      | The name of the task.                                                |
| `description` | string | No       | Additional information about the task.                               |
| `assigneeId`  | string | Yes      | Unique ID of the user assigned to the task.                          |
| `dueDate`     | string | Yes      | Date when the task should be completed, using `YYYY-MM-DD` format.   |
| `priority`    | string | Yes      | Priority of the task. Allowed values are `low`, `medium`, or `high`. |

---

## Example Request

```http
POST /api/v1/projects/proj_1001/tasks
Authorization: Bearer eyJhbGciOiJIUzI1NiIs...
Content-Type: application/json
Accept: application/json
```

### Example Request Body

```json
{
  "title": "Complete project documentation",
  "description": "Prepare and review the technical documentation for the project.",
  "assigneeId": "user_2045",
  "dueDate": "2026-09-15",
  "priority": "high"
}
```

---

## HTTP Response Codes

| Status Code                 | Meaning                 | Description                                                                     |
| --------------------------- | ----------------------- | ------------------------------------------------------------------------------- |
| `201 Created`               | Task created            | The task was successfully created.                                              |
| `400 Bad Request`           | Invalid request         | One or more request fields are missing or contain invalid data.                 |
| `401 Unauthorized`          | Authentication required | The authentication token is missing or invalid.                                 |
| `403 Forbidden`             | Access denied           | The authenticated user does not have permission to create tasks in the project. |
| `404 Not Found`             | Project not found       | The specified project does not exist.                                           |
| `409 Conflict`              | Conflict                | The request conflicts with the current project or task data.                    |
| `422 Unprocessable Entity`  | Validation error        | The request format is valid, but one or more values fail validation.            |
| `500 Internal Server Error` | Server error            | An unexpected error occurred on the server.                                     |

---

## Successful Response

A successful request returns HTTP status `201 Created`.

### Example Response Body

```json
{
  "success": true,
  "message": "Task created successfully",
  "data": {
    "id": "task_7832",
    "projectId": "proj_1001",
    "title": "Complete project documentation",
    "description": "Prepare and review the technical documentation for the project.",
    "assigneeId": "user_2045",
    "dueDate": "2026-09-15",
    "priority": "high",
    "status": "todo",
    "createdAt": "2026-08-29T12:30:00Z",
    "updatedAt": "2026-08-29T12:30:00Z"
  }
}
```

## Response Fields

| Field              | Type    | Description                                     |
| ------------------ | ------- | ----------------------------------------------- |
| `success`          | boolean | Indicates whether the operation was successful. |
| `message`          | string  | Describes the result of the operation.          |
| `data.id`          | string  | Unique ID of the newly created task.            |
| `data.projectId`   | string  | ID of the project containing the task.          |
| `data.title`       | string  | Title of the task.                              |
| `data.description` | string  | Description of the task.                        |
| `data.assigneeId`  | string  | ID of the assigned user.                        |
| `data.dueDate`     | string  | Task due date.                                  |
| `data.priority`    | string  | Task priority: `low`, `medium`, or `high`.      |
| `data.status`      | string  | Current task status.                            |
| `data.createdAt`   | string  | Date and time when the task was created.        |
| `data.updatedAt`   | string  | Date and time when the task was last updated.   |

## Summary

The `POST /api/v1/projects/{projectId}/tasks` endpoint creates a new task in a project. The client must authenticate the request and provide the task title, assignee, due date, and priority. The description is optional. A successful request returns the newly created task and its details.
