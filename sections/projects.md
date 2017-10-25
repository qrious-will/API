# Projects

## Get projects

* `GET /projects` - Returns all projects.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|
|stage | String (PLANNING, RUNNING, HALTED, DONE)|
|status | String (GREEN, YELLOW, RED)|
|status_description | String|
|description | String|
|color | String|
|estimation_units | String (HOURS, POINTS)|
|billable | Boolean|
|use_sprints | Boolean|
|sprint_length | Integer|
|start_date | Date|
|end_date | Date|
|card_levels | Integer (1 or 2)|
|client | Integer, ID of client|
|rate_card | Integer, ID of rate card|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
[
   {
      "id":1,
      "name":"Website project",
      "stage":"PLANNING",
      "status": "GREEN",
      "status_description": "",
      "description": "",
      "color": "#FF7C75",
      "estimation_units": "HOURS",
      "billable": true,
      "use_sprints": true,
      "sprint_length": 14,
      "start_date": "2017-01-01",
      "end_date": "2018-01-01",
      "card_levels": 1,
      "client": 1,
      "rate_card": 1,
      "created_by":1,
      "updated_by":1,
      "created_at":"2017-01-14T18:46:561Z",
      "updated_at":"2017-01-14T18:47:581Z"
   }, ...
]
```

## Get project

* `GET /projects/{projectId}` - Returns a specific project.

|Response fields | Description/format|
|------------ | -------------|
|id | Integer|
|name | String|
|stage | String (PLANNING, RUNNING, HALTED, DONE)|
|status | String (GREEN, YELLOW, RED)|
|status_description | String|
|description | String|
|color | String|
|estimation_units | String (HOURS, POINTS)|
|billable | Boolean|
|use_sprints | Boolean|
|sprint_length | Integer|
|start_date | Date|
|end_date | Date|
|card_levels | Integer (1 or 2)|
|client | Integer, ID of client|
|rate_card | Integer, ID of rate card|
|created_by | Integer, ID of person|
|updated_by | Integer, ID of person|
|created_at | Date|
|updated_at | Date|

### Sample JSON response
```javascript
{
   "id":1,
   "name":"Website project",
   "stage":"PLANNING",
   "status": "GREEN",
   "status_description": "",
   "description": "",
   "color": "#FF7C75",
   "estimation_units": "HOURS",
   "billable": true,
   "use_sprints": true,
   "sprint_length": 14,
   "start_date": "2017-01-01",
   "end_date": "2018-01-01",
   "card_levels": 1,
   "client": 1,
   "rate_card": 1,
   "created_by":1,
   "updated_by":1,
   "created_at":"2017-01-14T18:46:561Z",
   "updated_at":"2017-01-14T18:47:581Z"
}
```

## Create project

* `POST /projects` - Creates a new project. Returns the same object as getting a single project.

|Request fields | Description/format|
|------------ | -------------|
|name | (Required) String|
|stage | String (PLANNING, RUNNING, HALTED, DONE) (Defaults to PLANNING)|
|status | String (GREEN, YELLOW, RED) (Defaults to GREEN)|
|status_description | String|
|description | String|
|estimation_units | (Required) String (HOURS, POINTS)|
|billable | (Required) Boolean|
|use_sprints | (Required) Boolean|
|sprint_length | Integer (Defaults to 14)|
|start_date | Date|
|end_date | Date|
|card_levels | Integer (1 or 2) (Defaults to 1)|
|client | Integer, ID of client|
|rate_card | Integer, ID of rate card|

### Sample JSON request
POST https://api.forecast.it/api/v1/projects

```javascript
{
   "name":"Website project",
   "stage":"PLANNING",
   "status":"GREEN",
   "estimation_units":"HOURS",
   "billable":true,
   "use_sprints":true,
   "sprint_length":14
}
```

## Update project

* `PUT /projects/{projectId}` - Updates a project. Returns the same object as getting a single project.

|Request fields | Description/format|
|------------ | -------------|
|name | String|
|stage | String (PLANNING, RUNNING, HALTED, DONE)|
|status | String (GREEN, YELLOW, RED)|
|status_description | String|
|description | String|
|estimation_units | String (HOURS, POINTS)|
|billable | Boolean|
|use_sprints | Boolean|
|sprint_length | Integer|
|start_date | Date|
|end_date | Date|
|card_levels | Integer (1 or 2)|
|client | Integer, ID of client|
|rate_card | Integer, ID of rate card|

### Sample JSON request
PUT https://api.forecast.it/api/v1/projects/1

```javascript
{
   "stage":"RUNNING",
}
```

## Delete project

* `DELETE /projects/{projectId}` - Deletes a project.

### Sample JSON request
DELETE https://api.forecast.it/api/v1/projects/1