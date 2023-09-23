# User Management API Documentation

This Django project provides a User Management API with endpoints for user registration, authentication, and user CRUD operations. The project utilizes Django Rest Framework (DRF) for building the API.

## API Endpoints

### User Registration

- **Endpoint**: `/api/users/`
- **HTTP Method**: POST
- **Description**: Register a new user.
- **Required Data**: User details (email, password, first name, last name).

### User List

- **Endpoint**: `/api/users/`
- **HTTP Method**: GET
- **Description**: Retrieve a list of all users.

### User Detail

- **Endpoint**: `/api/users/<id>/`
- **HTTP Method**: GET
- **Description**: Retrieve details of a specific user by their ID.

### User Update

- **Endpoint**: `/api/users/<id>/`
- **HTTP Method**: PUT
- **Description**: Update the details of a specific user by their ID.
- **Required Data**: User details (email, password, first name, last name).

### User Deletion

- **Endpoint**: `/api/users/<id>/`
- **HTTP Method**: DELETE
- **Description**: Delete a specific user by their ID.

### JWT Token Obtain

- **Endpoint**: `/api/token/`
- **HTTP Method**: POST
- **Description**: Obtain a JSON Web Token (JWT) by providing valid user credentials (email and password) in the request body.

### JWT Token Refresh

- **Endpoint**: `/api/token/refresh/`
- **HTTP Method**: POST
- **Description**: Refresh an existing JWT token to obtain a new one. This endpoint requires a valid refresh token.

## Usage

1. **User Registration**:
   - Send a POST request to `/api/users/` with user details (email, password, first name, last name) to register a new user.

2. **User Authentication**:
   - Obtain a JWT token by sending a POST request to `/api/token/` with valid user credentials (email and password) in the request body.
   - Include the obtained access token in the `Authorization` header of subsequent requests with the prefix "Bearer."

3. **Accessing User Resources**:
   - Secure your endpoints by adding `authentication_classes` and `permission_classes` to views that require authentication and authorization. Use `JWTAuthentication` and `IsAuthenticated` as appropriate.
   - Make GET, PUT, and DELETE requests to user-specific endpoints `/api/users/<id>/` to retrieve, update, or delete user information.

4. **JWT Token Refresh**:
   - Use the `/api/token/refresh/` endpoint to refresh an existing JWT token, which is useful for extending the token's validity.

## Configuration

Ensure that your project's settings (`settings.py`) have the correct JWT authentication settings, and that you've included the JWT URLs (`/api/token/` and `/api/token/refresh/`) as mentioned in the project setup documentation.

## Security

- Protect your access tokens and refresh tokens as they grant access to authenticated API endpoints.
- Always use HTTPS to secure data transmission.
- Implement additional security measures and validation for production use, such as rate limiting, input validation, and error handling.


