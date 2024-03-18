# User Management System API

## Overview

This project implements a RESTful API for a basic user management system. It allows for operations such as adding new users, updating user information, retrieving users by their ID, and listing all users. The system utilizes a PostgreSQL database to store user data.

## Prerequisites

Before running the application, ensure you have the following installed:

- Go (version 1.15 or newer)
- PostgreSQL (version 12 or newer)

## Getting Started

### Database Setup

1. Install PostgreSQL and start the PostgreSQL service.
2. Create a new database named `web3`:
    ```bash
    createdb web3
    ```
3. Connect to the `web3` database using `psql` or another PostgreSQL client:
    ```bash
    psql -d web3
    ```
4. Create the `users` table:
    ```sql
    CREATE TABLE users (
        id SERIAL PRIMARY KEY,
        name VARCHAR(50),
        email VARCHAR(50) UNIQUE NOT NULL,
        age INT
    );
    ```

### Application Setup

1. Clone the repository to your local machine:
    ```bash
    git clone https://github.com/<your-username>/user-management-api.git
    ```
2. Navigate to the project directory:
    ```bash
    cd user-management-api
    ```
3. Install the required Go dependencies:
    ```bash
    go mod tidy
    ```
4. Update the database connection settings in the `main.go` file to match your PostgreSQL credentials.

### Running the Application

1. Start the server:
    ```bash
    go run main.go
    ```
    The server will start listening on port 8080.

## API Endpoints

- **Add a New User**
  - `POST /users`
  - Body: `{ "name": "John Doe", "email": "john.doe@example.com", "age": 30 }`

- **Retrieve a User by ID**
  - `GET /users/:id`
  
- **Update User Information by ID**
  - `PUT /users/:id`
  - Body: `{ "name": "Jane Doe", "email": "jane.doe@example.com", "age": 31 }`

- **List All Users**
  - `GET /users`

## Testing

Ensure you have a suite of unit tests for the API endpoints. Test the logic, input validation, and error handling. Run the tests using the following command:

```bash
go test ./...
```

## Contributions

Contributions are welcome! Please fork the repository and submit a pull request with your proposed changes.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
