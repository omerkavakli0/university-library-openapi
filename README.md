# University Library OpenAPI

This repository contains the OpenAPI specification for the **University Library OpenAPI**, an online library system for the university. The API provides CRUD operations for managing books, students, and loan transactions.

## OpenAPI Specification

- **Version**: 3.0.4
- **File**: [`openapi.yaml`](./openapi.yaml)
- **Base URLs**:
  - Local: `http://localhost:3000`
  - Production: `https://api.university-library.com`

## Features

- **Books**: Manage books in the library.
- **Students**: Manage student records.
- **Loans**: Handle book loan transactions.

## Security

The API uses an API key for authentication. Include the `X-API-Key` header in your requests.

```http
X-API-Key: YOUR_API_KEY
```

## Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/omerkavakli0/university-library-openapi.git
   ```
2. Navigate to the directory:
   ```bash
   cd university-library-openapi
   ```
3. Open the `openapi.yaml` file to view the API specification.

## Documentation

You can use tools like [Swagger UI](https://swagger.io/tools/swagger-ui/) to render the OpenAPI specification.