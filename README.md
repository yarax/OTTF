# Open Time Tracking Format

## What is it

Open Time Tracking Format (OTTF) - is an open format for describing working activity. 
There are plenty of tools, which allow you to track your working time. Sometimes you need to track your time multiple times or the way you can do it takes too much effort. Our goal is to provide one common format for all of the time tracking tools, in order to migrate data between them easily and with no extra effort.

## Why

https://yarax.medium.com/one-common-format-for-all-the-time-tracking-tools-cc5ba7fa37f1

## Example

```
{
  "meta": {
    "author": {
      "name": "Roman Krivtsov"
    }
  },
  "timeTracking":
    [
      {
        "taskName": "Implement unit tests for MDP-232",
        "taskId: "MDP-459",
        "spentTime": "4h",
        "timeRange": {
          "from": "2023-06-13T12:00:00+05:30",
          "till": "2023-06-13T16:00:00+05:30"
        },
        "description": "wrote tests and fixed bugs"
      }
    ]
}
```

## Format description

### Root object

| Field Name    | Type                       | Description         |Required|
| ------------- |:--------------------------:| -------------------:|-------:|
| meta          | [Meta Object](#meta-object)| The meta information about the data|yes|
| timeTracking  | List of [Time Tracking Object](#Time Tracking Object)| Object containing information about working time|yes|                             


## Meta Object

| Field Name    | Type                       | Description         |Required|
| ------------- |:--------------------------:| -------------------:|-------:|
| author          | [Author Object](#author-object)| The meta information about the creator of the data|yes|

## Author Object

| Field Name    | Type                       | Description         |Required|
| ------------- |:--------------------------:| -------------------:|-------:|
| name          | String| First and last name of the user|yes|


## Time Tracking Object

| Field Name    | Type                       | Description         |Required|
| ------------- |:--------------------------:| -------------------:|-------:|
| taskName          | String| Title of the task|yes|
| taskId  | String| Unique task identifier| no|
| spentTime  | String| Spent time. Possible options: 2h, 25m| yes|
| description  | String| Description of the work | no|
| timeRange          | [Time Range Object](#time-range-object)| From/till time range|no|


## Time Range Object

| Field Name    | Type                       | Description         |Required|
| ------------- |:--------------------------:| -------------------:|-------:|
| from          | String| YYYY-MM-DD'T'HH:mm:ss'Z' Timestamp in ISO 8601 format, e.g 2018-06-13T12:11:13+05:30 |yes|
| till          | String| YYYY-MM-DD'T'HH:mm:ss'Z' Timestamp in ISO 8601 format, e.g 2018-06-13T12:11:13+05:30 |yes|



