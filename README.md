# Nimap_Java_CRUDApplication

This project is a Spring Boot application for managing **Categories** and **Products** with CRUD operations, pagination, and a one-to-many relationship.

## 1. Spring Boot Setup
- Use **Spring Initializr** or your preferred IDE to create a new Spring Boot project.
- Add the following dependencies:
  - Spring Web
  - Spring Data JPA
  - Database driver (H2, MySQL, or PostgreSQL)

## 2. REST Controllers
- Create REST controllers for handling CRUD operations for both **Categories** and **Products**.
- Use annotations:
  - `@GetMapping`
  - `@PostMapping`
  - `@PutMapping`
  - `@DeleteMapping`

## 3. Database Configuration (RDB)
- Configure database connection in `application.properties` or `application.yml`.
- Use an RDBMS like:
  - MySQL
  - PostgreSQL
  - H2 (for development/testing)

## 4. Annotation-Based Configuration
- Use annotation-based configuration instead of XML.
- Common annotations:
  - `@Entity`
  - `@Table`
  - `@Column`
  - `@OneToMany`

## 5. Category CRUD Operations
Implement the following APIs:

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET    | `/api/categories?page=3` | Retrieve all categories (with pagination) |
| POST   | `/api/categories` | Create a new category |
| GET    | `/api/categories/{id}` | Retrieve a category by ID |
| PUT    | `/api/categories/{id}` | Update a category by ID |
| DELETE | `/api/categories/{id}` | Delete a category by ID |

## 6. Product CRUD Operations
Implement the following APIs:

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET    | `/api/products?page=2` | Retrieve all products (with pagination) |
| POST   | `/api/products` | Create a new product |
| GET    | `/api/products/{id}` | Retrieve a product by ID |
| PUT    | `/api/products/{id}` | Update a product by ID |
| DELETE | `/api/products/{id}` | Delete a product by ID |

## 7. One-to-Many Relationship
- Define a **One-to-Many** relationship between **Categories** and **Products**.
- Use `@OneToMany` in the `Category` entity.

## 8. Server-Side Pagination
- Implement pagination using query parameters:
  - `page`
  - `size`
  - `sort`
- In repository, use:
  ```java
  findAll(Pageable pageable)
