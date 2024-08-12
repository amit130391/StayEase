# StayEase
A RESTful API service using Spring Boot to streamline the room booking process for a hotel management aggregator application.

## Postman Collection

You can import the Postman collection for this project using the following link:

[Postman Collection](https://elements.getpostman.com/redirect?entityId=30015848-f1213d2f-037b-4ecb-8d1a-25bb4925831c&entityType=collection)

## Table of Contents
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Contact](#contact)

## Features
- **User Registration and Login**
  - Users can register by providing their email, password, first name, and last name.
  - Passwords are securely stored using BCrypt encryption.
  - Role-based access control with `CUSTOMER`, `HOTEL MANAGER`, and `ADMIN` roles.
  - JWT tokens are used for session management.

- **Hotel Management**
  - Administrators can create and delete hotels.
  - Hotel Managers can update hotel details.
  - Customers can view available hotels.

- **Booking Management**
  - Customers can book rooms in a hotel (one room per request).
  - Hotel Managers can cancel bookings.
  - Room availability is automatically updated based on bookings and cancellations.

## Technologies Used
- **Java 17**
- **Spring Boot 3.x**
  - Spring Security (for authentication and authorization)
  - Spring Data JPA (for database interactions)
  - Spring Web (for building RESTful APIs)
- **MySQL** (for data persistence)
- **JWT** (for secure token-based authentication)
- **JUnit 5** (for testing)


## Installation
### Prerequisites
- Java Development Kit (JDK) 17 or higher
- MySql
- Gradle
- Git

### Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/amit130391/StayEase.git
   cd StayEase
2. Configure MySql:
   Ensure MySql is running on your local machine and update the connection details in application.properties if using a remote MySql instance.
3. Build and run the application:
   ./gradlew clean build
   ./gradlew bootRun

## Usage
1. The application runs on http://localhost:8080.
2. Use the API endpoints to manage user,hotels and booking service.
3. Use Postman or any other API client to interact with the endpoints.

## API Endpoints
### User Endpoints
1. GET /admin/users - Retrieve a list of all user, only admin can view all the users.
2. GET user/me - Retrieve the details of an authenticated user.
3. POST /register - Registers a new user.
### Book Endpoints
1. GET /books - Retrieve a list of all books.
2. POST /admin/book - Save a new book in the DB. Only admin can save a new book.
3. PUT /admin/book/{bookId}?status={Status} - Updates the given book. Only admin is allowed to update.
4. DELETE /book/{bookId} - Deletes a book with the given ID.
### Rental Endpoints
1. POST /user/me/books/{bookId}/rent - Rent a book with the given Id for the authenticated user. Shows required error if the book is already rented or is unvailable or user has already rented 2 books. 
2. POST /user/me/books/{bookId}/return - Return a book with the given Id for the authenticated user. Shows required error if the book is not rented by the user or if there is no such book.
   
## Contact
If you have any questions or suggestions, feel free to contact me:

    Name: Amit Sharma
    Email: amit130391@gmail.com
    GitHub: amit130391 
