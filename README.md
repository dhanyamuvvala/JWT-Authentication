# DEMO-JWT

A Spring Boot-based authentication service implementing JSON Web Token (JWT) for secure user authentication and authorization.

---

## Overview

This project demonstrates a stateless authentication mechanism using JWT integrated with Spring Security. It enables secure login functionality and protects REST APIs by validating tokens on each request.

---

## Tech Stack

- Java
- Spring Boot
- Spring Security
- JWT (JSON Web Token)
- Maven
- Hibernate (JPA)
- MySQL / H2

---

## Architecture

The application follows a layered architecture:

- **Controller Layer**: Handles HTTP requests and responses  
- **Service Layer**: Contains business logic  
- **Repository Layer**: Interacts with the database  
- **Security Layer**: Manages authentication and JWT validation  

---

## Project Structure


src/main/java/com/AML3B/DEMO_JWT

├── config # Security configuration
├── controller # REST controllers
├── model # Entity classes
├── repository # Data access layer
├── service # Business logic
└── DemoJwtApplication.java


---

## Configuration

Update database configuration in `application.properties`:


spring.datasource.url=jdbc:mysql://localhost:3306/<database_name>
spring.datasource.username=<username>
spring.datasource.password=<password>


---

## Running the Application

Using Maven:


mvn spring-boot:run


Or run `DemoJwtApplication.java` directly from your IDE.

The application will start on:


http://localhost:8080


---

## Authentication Flow

1. User sends login request with credentials  
2. Server validates credentials using Spring Security  
3. JWT token is generated and returned  
4. Client includes token in Authorization header  
5. Server validates token for protected endpoints  

---

<img width="1101" height="703" alt="Screenshot 2026-04-16 144804" src="https://github.com/user-attachments/assets/b05ac481-5101-4f15-ac47-7837ae1f60d8" />
<img width="1101" height="758" alt="Screenshot 2026-04-16 145021" src="https://github.com/user-attachments/assets/7c6b5fb2-8b3e-47a4-933e-066c59375a2f" />
<img width="527" height="222" alt="Screenshot 2026-04-16 145113" src="https://github.com/user-attachments/assets/daa0004d-7fbf-4517-959c-ea37ffe84864" />
<img width="1919" height="979" alt="Screenshot 2026-04-16 145208" src="https://github.com/user-attachments/assets/51cf85ad-ff43-4642-bb88-3373909c4b0d" />


## API Endpoint

### Login


POST /login


#### Request Body
```json
{
  "username": "user1",
  "password": "pass123"
}
Response
{
  "token": "<jwt_token>"
}




