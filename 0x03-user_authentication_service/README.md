# 0x03. User Authentication Service

This project involves creating a user authentication service using SQLAlchemy, Flask, and other technologies. The service includes various functionalities such as user registration, login, session management, password reset, and more.

## Tasks

### 0. User Model

Create a SQLAlchemy model named `User` for a database table named `users`. The model will have the following attributes:

- `id`: the integer primary key
- `email`: a non-nullable string
- `hashed_password`: a non-nullable string
- `session_id`: a nullable string
- `reset_token`: a nullable string

### 1. Create User

Complete the `DB` class to implement the `add_user` method.

### 2. Find User

Implement the `DB.find_user_by` method. This method takes in arbitrary keyword arguments and returns the first row found in the users table as filtered by the method’s input arguments. No validation of input arguments required at this point.

### 3. Update User

Implement the `DB.update_user` method that takes as argument a required `user_id` integer and arbitrary keyword arguments, and returns None.

### 4. Hash Password

Define a `_hash_password` method that takes in a password string arguments and returns bytes.

### 5. Register User

Implement the `Auth.register_user` in the `Auth` class.

### 6. Basic Flask App

Set up a basic Flask app.

### 7. Register User

Implement the end-point to register a user. Define a `users` function that implements the `POST /users` route.

### 8. Credentials Validation

Implement the `Auth.valid_login` method. It should expect `email` and `password` required arguments and return a boolean.

### 9. Generate UUIDs

Implement a `_generate_uuid` function in the `auth` module. The function should return a string representation of a new UUID.

### 10. Get Session ID

Implement the `Auth.create_session` method. It takes an `email` string argument and returns the session ID as a string.

### 11. Log In

Implement a `login` function to respond to the `POST /sessions` route.

### 12. Find User by Session ID

Implement the `Auth.get_user_from_session_id` method. It takes a single `session_id` string argument and returns the corresponding `User` or `None`.

### 13. Destroy Session

Implement `Auth.destroy_session`. The method takes a single `user_id` integer argument and returns None.

### 14. Log Out

Implement a `logout` function to respond to the `DELETE /sessions` route.

### 15. User Profile

Implement a `profile` function to respond to the `GET /profile` route.

### 16. Generate Reset Password Token

Implement the `Auth.get_reset_password_token` method. It take an `email` string argument and returns a string.

### 17. Get Reset Password Token

Implement a `get_reset_password_token` function to respond to the `POST /reset_password` route.

### 18. Update Password

Implement the `Auth.update_password` method. It takes `reset_token` string argument and a `password` string argument and returns None.

### 19. Update Password End-Point

Implement the `update_password` function in the `app` module to respond to the `PUT /reset_password` route.

### 20. End-to-End Integration Test

Start your app. Open a new terminal window.

Create a new module called `main.py`. Create one function for each of the following tasks. Use the `requests` module to query your web server for the corresponding end-point. Use `assert` to validate the response’s expected status code and payload (if any) for each task.
