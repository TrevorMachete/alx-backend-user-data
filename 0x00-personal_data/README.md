# 0x00. Personal Data

This project focuses on handling personal data securely. It includes several tasks related to logging, data filtering, database connections, password encryption, and validation.

## Tasks

### 0. Regex-ing (Filtering Log Messages)

Implement a function called `filter_datum` that obfuscates sensitive information in log messages. The function should take a log message as input and return the obfuscated version. You can use regular expressions to achieve this.

### 1. Log Formatter

Copy the following code into `filtered_logger.py`. This code sets up a logger named "user_data" and configures it to log messages up to the `logging.INFO` level. The logger should not propagate messages to other loggers. It also uses a `StreamHandler` with a custom `RedactingFormatter` to hide sensitive fields.

### 2. Create Logger

Use the `user_data.csv` file for this task. Implement a function called `get_logger` that takes no arguments and returns a `logging.Logger` object. The logger should be named "user_data" and configured as described in Task 1.

### 3. Connect to Secure Database

Database credentials should never be stored in code or checked into version control. Consider storing them as environment variables on the application server. Make sure to handle database connections securely.

### 4. Read and Filter Data

Implement a `main` function that reads data from the `user_data.csv` file, filters it using the `filter_datum` function, and logs the filtered data using the logger created in Task 2.

### 5. Encrypting Passwords

User passwords should never be stored in plain text in a database. Implement a `hash_password` function that takes a string argument (the password) and returns a salted, hashed password (as a byte string). Use the `bcrypt` package for secure password hashing.

### 6. Check Valid Password

Implement an `is_valid` function that expects two arguments: `hashed_password` (a bytes type) and `password` (a string type). Use `bcrypt` to validate that the provided password matches the hashed password.

---