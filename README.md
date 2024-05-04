# LMS-Adult API Documentation

# Introduction
The LMS adult  API provides access to detailed information about learning management systems for organizations and users. This documentation is intended for developers, testers, project managers, and stakeholders interested in obtaining comprehensive descriptions of how LMS works 

## Base URL
https://api.LMS-Adult.com/v1

# Endpoints

## Retrieve All Users
Retrieve a list of all users/students available in the database.
- URL: `/users`
- Method: `GET`
- Parameters: None
- Response:
  - 200 OK: Returns a JSON array of users objects, each containing the following fields:

    - `id` (integer): Unique identifier for the user.
    - `name` (string): Name of the user
    - `hobbies` (array):An array of hobbies

  -  Example:

    ````json
    [
      {
        "id": 1,
        "name": "MaryJane Okafor",
        "hobbies": ['running','dancing', 'swimming', 'basketball'] 
    },
    {
        "id": 2,
        "name": "Collins Smith",
        "hobbies": ['running','dancing', 'swimming', 'basketball'],
      },
      
    ]
## Retrieve Users by ID
Retrieve detailed information about a specific user based on its unique identifier.

- URL: `/user/{id}`
- Method: `GET`
- Parameters:
  - `{id}` (integer): The unique identifier of the user
- Response:
  - 200 OK: Returns a JSON object with the details of the specified user
  - 404 Not Found: If the user with the specified ID does not exist.
  - Example:
    ```json
    {
      "id": 1,
      "name": "Ella Onukwube",
      "hobbies": ['running','dancing', 'swimming', 'basketball']
    }
## Retrieve User by Username
Retrieve detailed information about a specific user based on its unique identifier.

- URL: `/user/{Username}`
- Method: `GET`
- Parameters:
  - `{username}` (string): The unique identifier for the description  of the user.
- Response:
  - 200 OK: Returns a JSON object with the details of the specified user.
  - 404 Not Found: If the user with the specified Username does not exist.
  - Example:
    ````json
    {
      "id": 1,
      "Username": "ICE",
      "name": "Kizito Okolo",
      "hobbies":  ['running','dancing', 'swimming', 'basketball']
    }
## Update User by Id/Username
Update information about a specific user based on its unique identifier.

- URL: `/user/{Username}/{id}`
- Method: `PATCH`
- Parameters:
  - `{username}` (string): The unique identifier for the description of the user.
  -  `{id}` (integer): The unique identifier of the user.
- Response:
  - 200 OK: Returns a JSON object with the details of the specified user.
  - 404 Not Found: If the user with the specified Username does not exist.
  - Example:
    ````json
    {
      "id": 1,
      "Username": "Kelly",
      "name": "Ugwu Kelechi.",
      "Hobbies": ['running','dancing', 'swimming', 'basketball']
    }
## Delete User by Username/ID
Update information about a specific user based on its unique identifier.

- URL: `/user/{Username}/{id}`
- Method: `DELETE`
- Parameters:
  - `{username}` (string): The unique identifier for the description  of the user.
  -  `{id}` (integer): The unique identifier of the user.
- Response:
  - 200 OK
  - 404 Not Found: If the user with the specified Username or Id does not exist.
  - Example:
   ````json
   [
     {
      "id": 1,
      "Username": "Kelly",
      "name": "Ugwu Kelechi.",
      "Hobbies": ['running','dancing', 'swimming', 'basketball']
    }
   ]
# Usage
To access user data from the API, make HTTP GET requests to the specified endpoints using the provided base URL.

### Example using Node.js

```Typescript
import axios, { AxiosResponse } from 'axios';

// Retrieve all users
axios.get('https://api.LMS-Adult.com/v1/users')
  .then(response => {
    console.log('All Users:', response.data);
  })
  .catch(error => {
    console.error('Error retrieving Users:', error);
  });


// Retrieve Users by ID (e.g., ID = 1)
axios.get('https://api.LMS-Adult.com/v1/user/1')
  .then(response => {
    console.log('User details:', response.data);
  })
  .catch(error => {
    console.error('Error retrieving User details:', error);
  });
```

# Conclusion
The LMS API offers a valuable resource for obtaining detailed information about Learning Management Systems. Developers can utilize this data to integrateLMS information into applications, testers can verify functionality, and stakeholders can make informed decisions regarding LMS.
