# Threat Model

## Executive Summary

## External Dependencies

| ID | Description                                                                                                                                                  |
|----|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 01 | The API will be hosted on a Linux server. It will be developed in C# using the .NET Framework. This server will be subjected to regular security patches.    |
| 02 | The RDMS will be MySQL, hosted on a Linux server. This server will be subjected to regular security patches.                                                 |
| 03 | All connections will be encrypted using TLS.                                                                                                                 |

## Entry Points

| ID  | Name                        | Description                                                                                                                   | Trust Levels |
|-----|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------|--------------|
| 1   | HTTPS API Port              | This port will only be accessible using a communication channel protected with TLS. All other entry points stem from this one |              |
| 1.1 | Main Endpoint               | The default entry point for all users.                                                                                        |              |
| 1.2 | Create account              | A page where unauthenticated users can create an account.                                                                     |              |
| 1.3 | Login                       | Page where users provide login credentials in order to use functionalities which require authentication.                      |              |
| 1.4 | Update Personal Information | Page where authenticated users can change their personal information, like vehicle data, payment methods, etc.                |              |
| 1.5 | Manage Park                 | Page to add, update or delete a park in the system                                                                            |              |
| 1.6 | Manage Park Managers        | Page where administrators can add, delete, or change information of park managers.                                            |              |

## Exit Points

## Assets

| ID  | Name                            | Description                                                                                                              | Trust Levels |
|-----|---------------------------------|--------------------------------------------------------------------------------------------------------------------------|--------------|
| 1   | Users                           | Assets relating to users, park managers and app administrators                                                           |              |
| 1.1 | User login details              | Login details used to authenticate a user in the application                                                             |              |
| 1.2 | Park Manager login details      | Login details used to authenticate a park manager in the application                                                     |              |
| 1.3 | Admin login details             | Login details used to authenticate an admin in the application                                                           |              |
| 1.4 | User payment methods            | Payment methods a user has specified to pay for parking                                                                  |              |
| 1.5 | Car details                     | Information about cars registered by users                                                                               |              |
| 2   | Systems                         | Assets relating to the systems through which the application is made available                                           |              |
| 2.1 | Availability of the API         | The API should be available so that users can use the application to park                                                |              |
| 2.2 | Availability of the Database    | The database server should be available so that the application can perform queries whenever necessary                   |              |
| 3   | API                             | Assets related to the Backend API                                                                                        |              |
| 3.1 | Login Session                   | The login session of a user in the API                                                                                   |              |
| 3.2 | Ability to create an account    | The ability for unregistered users to create an account in the application                                               |              |
| 3.3 | Ability to manage parks         | The ability to manage the parks that exist in the application - create new parks, change existing ones and delete parks. |              |
| 3.4 | Ability to manage park managers | The ability to add, remove, or change park managers.                                                                     |              |
| 3.5 | Ability to manage personal data | The ability to manage the data, such as payment information and car information.                                         |              |

## Trust Levels

| ID | Name                  | Description                                                                         |
|----|-----------------------|-------------------------------------------------------------------------------------|
| 1  | Anonymous user        | A user which has not yet created an account                                         |
| 2  | Authenticated user    | A user which has successfully authenticated in the application                      |
| 3  | Park Manager          | A user that can add, change or delete parks                                         |
| 4  | Administrator         | A user that can add, change or delete park managers                                 |
| 5  | Systems administrator | An administrator that configures the deployment of the application and the database |
