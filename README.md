# Insurance Policy Manager

A Spring Boot application for managing insurance policies.

## Requirements

- Java 17
- Maven 3.x
- Docker and Docker Compose (for containerized setup)

## Running Locally

### 1. Clone the repository

```bash
git clone <repository-url>
cd insurance-policy-manager
```

### 2. Build the application

```bash
mvn clean install
```

### 3. Run the application

```bash
mvn spring-boot:run
```

The application will start with an H2 in-memory database in development mode.

- Application will be available at: http://localhost:8080
- H2 Console: http://localhost:8080/h2-console
  - JDBC URL: `jdbc:h2:mem:insurance_db`
  - Username: `sa`
  - Password: (empty)

## Running with Docker

### 1. Build and run using Docker Compose

```bash
docker-compose up -d
```

This will:

- Build the application container
- Start a PostgreSQL database
- Configure the application to use PostgreSQL
- Make the application available at http://localhost:8081

### 2. Stop the Docker containers

```bash
docker-compose down
```

To remove volumes as well:

```bash
docker-compose down -v
```

## Docker Configuration

The application uses:

- Spring Boot with port 8081 in Docker environment
- PostgreSQL database:
  - Database: `insurance_db`
  - Username: `admin`
  - Password: `secret`
  - Port: 5432

## API Documentation

Swagger UI is available at:

- Local: http://localhost:8080/swagger-ui.html
- Docker: http://localhost:8081/swagger-ui.html
