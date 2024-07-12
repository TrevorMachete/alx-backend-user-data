# 0x01. Basic Authentication

## Introduction

This project is about implementing Basic Authentication on a simple API. The API has one model: User. Users are stored via serialization/deserialization in files.

## Getting Started

1. Download and start your project from the provided archive.zip.

## Setup and Start Server

Instructions for setting up and starting the server will be provided.

## Features

### Error Handlers

1. **Unauthorized Error Handler (401)**: An error handler for HTTP status code 401 has been added. The response is a JSON: `{"error": "Unauthorized"}`. This error handler can be tested by making a GET request to `/api/v1/unauthorized`, which raises a 401 error.

2. **Forbidden Error Handler (403)**: An error handler for HTTP status code 403 will be added.

### Authentication

An `Auth` class has been created to manage the API authentication.

### Routes

A method `require_auth(self, path: str, excluded_paths: List[str]) -> bool:` has been added in `Auth` that returns True if the path is not in the list of strings `excluded_paths`.

### Request Validation

All requests are validated to secure the API.

### Basic Authentication

A `BasicAuth` class has been created that inherits from `Auth`. This class will be used instead of `Auth` depending on the value of the environment variable `AUTH_TYPE`. If `AUTH_TYPE` is equal to `basic_auth`, `BasicAuth` will be used.

### Base64 Decoding

Methods have been added to the `BasicAuth` class to handle Base64 decoding of the Authorization header, extracting user credentials from the decoded Base64 string, and returning the User instance based on his email and password.

### Current User

The method `current_user(self, request=None) -> TypeVar('User')` has been added in the `BasicAuth` class that overloads `Auth` and retrieves the User instance for a request.

### Passwords with ":" 

The method `extract_user_credentials(self, decoded_base64_authorization_header)` has been improved to allow passwords with ":".

### Require Auth with Stars

The method `require_auth(self, path, excluded_paths)` has been improved by allowing "*" at the end of excluded paths.

## Conclusion

With these features, we have all the pieces for having a complete Basic authentication.
