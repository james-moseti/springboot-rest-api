# Spring Boot REST API

A simple backend project demonstrating how to build REST APIs with Spring Boot, connect to a PostgreSQL database using Docker, and manage data with Spring Data JPA.

## Features

- REST API endpoints for Software Engineer management
- PostgreSQL database integration
- Docker containerization
- Spring Data JPA for data persistence
- Maven build system

## Prerequisites

- Java 17 or higher
- Docker and Docker Compose
- Maven (or use included wrapper)

## Quick Start

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd springboot-rest-api
   ```

2. **Start PostgreSQL with Docker**
   ```bash
   docker-compose up -d
   ```

3. **Run the application**
   ```bash
   ./mvnw spring-boot:run
   ```

4. **Test the API**
   ```bash
   curl http://localhost:8080/api/software-engineers
   ```

## API Endpoints

- `GET /api/software-engineers` - Get all software engineers
- `GET /api/software-engineers/{id}` - Get engineer by ID
- `POST /api/software-engineers` - Create new engineer
- `PUT /api/software-engineers/{id}` - Update engineer
- `DELETE /api/software-engineers/{id}` - Delete engineer

## Database Configuration

The application connects to PostgreSQL running in Docker. Database configuration is in `application.properties`:

- **Database**: `software_engineers_db`
- **Username**: `admin`
- **Password**: `password`
- **Port**: `5432`

## Project Structure

```
src/
├── main/java/com/jmcoding/
│   ├── Application.java                 # Main application class
│   ├── SoftwareEngineer.java           # Entity model
│   ├── SoftwareEngineerController.java # REST controller
│   ├── SoftwareEngineerRepository.java # Data repository
│   └── SoftwareEngineerService.java    # Business logic
└── resources/
    └── application.properties          # App configuration
```

## Testing

Run tests with Maven:
```bash
./mvnw test
```

HTTP requests are available in `requests.http` for testing endpoints.