# Open Tracking Time Format

## What is it

Open Tracking Time Format (OTTF) - is an open format for describing working activity. 
There are plenty of tools, which allow you to track your working time. Sometimes you need to track your time multiple times or the way you can do it takes too much effort. Our goal is to provide one common format for all of the time tracking tools, in order to migrate data between them easily and with no extra effort.

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
          "from": "08:00",
          "till": "12:00"
        },
        "description": "wrote tests and fixed bugs"
      }
    ]
}
```

## Format description

### Root object

| Field Name    | Type                       | Description         |
| ------------- |:--------------------------:| -------------------:|
| meta          | [Meta Object](#Meta Object)| The meta information about the data|
| timeTracking  | [Time Tracking Object](#Time Tracking Object)| Object containing information about working time|                             


