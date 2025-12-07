# Product CRUD API

A Spring Boot REST API for managing products with full CRUD operations.

## Quick Start

### Prerequisites
- JDK 17+
- Gradle

### Build & Run
```bash
# Build
gradlew build

# Run
./gradlew bootRun
```

The API will start at `http://localhost:8080`

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/products/` | Get all products |
| GET | `/api/products/{id}` | Get product by ID |
| POST | `/api/products/` | Create new product |
| PUT | `/api/products/{id}` | Update product |
| DELETE | `/api/products/{id}` | Delete product |
| GET | `/api/products/search?name={name}` | Search by name |

## Example Request

**Create Product (POST)**
```bash
curl -X POST http://localhost:8080/api/products/ \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Laptop",
    "description": "dell",
    "price": 35000,
    "quantity": 10
  }'
```

## Response Format

```json
{
  "id": 1,
  "name": "Laptop",
  "description": "dell",
  "price": 35000,
  "quantity": 10
}
```

## API Documentation

- **Swagger UI**: `http://localhost:8080/swagger-ui.html`
- **OpenAPI Spec**: `http://localhost:8080/v3/api-docs`

## Database

- **Type**: H2 (Embedded In-Memory)
- **ORM**: Hibernate/JPA
- **Auto Schema**: Created on startup

## Tech Stack

- Spring Boot 3.2.0
- Spring Data JPA
- H2 Database
- Lombok
- Springdoc OpenAPI

## Common Issues

| Issue | Solution |
|-------|----------|
| ProductDTO fields null | Ensure @Data, @NoArgsConstructor annotations are present |
| Port 8080 in use | Change `server.port` in `application.properties` |
| Required field null | Provide `name`, `price`, `quantity` in request |

---

For full documentation, see Swagger UI at `http://localhost:8080/swagger-ui.html`

