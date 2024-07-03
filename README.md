# generic-oas-backend
A small application with focus on testing and development of PoCs

## Version information

Actual Version: 1.3

## Introduction

The application contains services to manage incoming requests. The requests are stored as strings in the Xyna database and can be read from there.
When a JSON representation of Xyna datatypes is used, those objects can be serialized and de-serialized with the standard JSON services, that are present in the JSON application of the Xnya Factory

## Services

The application contains the following services:

1. Store Request: saves the resource to the database
2. Delete Request: deletes the resource identified by "id"
3. Get All Requests With Filter: delivers a list of all matching resources. The filter consists of "providerAppName" and "providerAppVersion".
4. Get Request By Id: delivers exactly one resource identified by "id" (primary key)


## Persistence

The data is stored in the Xyna Storable "Resource_Storable", which has the following attributes

### Resource Storable

| Attibute           | Datatype | Comment                                               |
| ---                | ---      | ---                                                   |
| id                 | String   | Primary Key                                           |
| resource           | String   | Request or serialized object                          |
| providerAppName    | String   | Name of the calling application                       |
| providerAppVersion | String   | Version of the calling application                    |
| objectType         | String   | Information of the object type, e.g the Xyna datatype |
| saveTime           | Long     | Save-Time of the entry in milliseconds                |
