apiCredito - Fullstack Application with Spring Boot and Angular
Welcome to apiCredito, a fullstack application designed to manage credit-related operations. This project combines a robust backend built with Spring Boot and a responsive frontend developed with Angular, containerized using Docker for seamless deployment. The application includes a PostgreSQL database, a RESTful API, and a mobile-compatible frontend.

Overview
Backend: Built with Spring Boot, the API provides endpoints to manage credit operations. It includes unit tests for the controller layer using an in-memory H2 database and comprehensive exception handling.
Frontend: Developed with Angular, the frontend is optimized for desktop and mobile devices. It can be served locally with ng serve and accessed at http://localhost:4200.
Docker: The application uses Docker Compose to orchestrate three containers: PostgreSQL (database), Spring Boot API, and Angular frontend, initialized with preloaded database records.
Features
RESTful API with endpoints for credit management.
Exception handling for robust error management.
Controller layer tests using H2 database.
Mobile-compatible Angular frontend.
Dockerized deployment with PostgreSQL, API, and frontend containers.
Prerequisites
Docker and Docker Compose installed.
Node.js and npm installed for frontend development.
Maven installed for backend build.
Java 17 (or compatible version) for Spring Boot.
Endpoints
Test the API using curl with the following endpoints:

Get Credit by ID: http://localhost:8080/api/creditos/7891011
bash

Collapse

Wrap

Run

Copy
curl http://localhost:8080/api/creditos/7891011
Get Credit Details: http://localhost:8080/api/creditos/credito/123456
bash

Collapse

Wrap

Run

Copy
curl http://localhost:8080/api/creditos/credito/123456
Getting Started
1. Clone the Repository
bash

Collapse

Wrap

Run

Copy
git clone https://github.com/adesdsilva/apiCredito.git
cd apiCredito
2. Build and Run with Docker
The docker-compose.yml file in the repository configures three containers:

postgres: PostgreSQL database with preloaded records.
api: Spring Boot backend.
frontend: Angular frontend.
Run the following commands to build and start the containers:

bash

Collapse

Wrap

Run

Copy
docker-compose build
docker-compose up -d
The API will be available at http://localhost:8080.
The frontend will be available at http://localhost:4200 (served by the Angular container).
3. Stop and Remove Containers
To stop and remove the containers:

bash

Collapse

Wrap

Run

Copy
docker-compose down
4. Backend Development (Optional)
To build and run the backend locally without Docker:

Navigate to the backend directory:
bash

Collapse

Wrap

Run

Copy
cd backend
Build the project with Maven:
bash

Collapse

Wrap

Run

Copy
mvn clean install
Run the application:
bash

Collapse

Wrap

Run

Copy
mvn spring-boot:run
5. Frontend Development (Optional)
To develop the frontend locally without Docker:

Navigate to the frontend directory:
bash

Collapse

Wrap

Run

Copy
cd frontend
Install dependencies:
bash

Collapse

Wrap

Run

Copy
npm install
Start the development server:
bash

Collapse

Wrap

Run

Copy
ng serve
Access the frontend at http://localhost:4200.
6. Running Tests
Backend Tests: The API includes controller tests using H2. Run them with:
bash

Collapse

Wrap

Run

Copy
cd backend
mvn test
Frontend Tests: No frontend tests are currently implemented.
Project Structure
backend/: Contains the Spring Boot application with:
REST controllers with exception handling.
H2-based unit tests for the controller layer.
Configuration for PostgreSQL in Docker.
frontend/: Contains the Angular application with:
Mobile-responsive design.
Components for credit management UI.
docker-compose.yml: Defines the three-container setup (PostgreSQL, API, frontend).
Additional Details
Backend
Framework: Spring Boot 3.5.0 (or latest compatible version).
Database: PostgreSQL, initialized with sample credit records.
Features: RESTful API with endpoints for credit operations, exception handling (e.g., custom exception classes), and H2 for testing.
Build Tool: Maven.
Frontend
Framework: Angular (latest stable version).
Compatibility: Optimized for mobile devices using responsive design techniques (e.g., CSS media queries, flexbox).
Build Tool: npm.
Development Server: ng serve for hot-reloading during development.
Docker Configuration
Containers:
postgres: Runs the PostgreSQL database with preloaded data.
api: Hosts the Spring Boot application, connected to PostgreSQL.
frontend: Serves the Angular app, built and served via a lightweight web server (e.g., Nginx).
Initialization: The docker-compose.yml ensures the database is populated with initial records on startup.
