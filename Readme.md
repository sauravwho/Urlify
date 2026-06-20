# Urlify

Urlify is a Spring Boot application designed to provide URL shortening services. It allows users to convert long, unwieldy URLs into concise, shareable short links. The application features a RESTful API for managing URLs and integrates with a PostgreSQL database for persistence.

## Features

*   **URL Shortening**: Convert long URLs into short, unique codes.
*   **RESTful API**: Expose endpoints for creating, retrieving, and managing short URLs.
*   **Data Persistence**: Store URL mappings in a PostgreSQL database using Spring Data JPA.
*   **Input Validation**: Ensure data integrity with robust validation for incoming requests.
*   **API Documentation**: Automatically generated interactive API documentation using Springdoc OpenAPI (Swagger UI).

## Technologies Used

*   **Spring Boot**: Framework for building stand-alone, production-grade Spring applications.
*   **Spring WebMVC**: For building the RESTful web services.
*   **Spring Data JPA**: For easy interaction with the PostgreSQL database.
*   **PostgreSQL**: Relational database for storing URL mappings.
*   **Springdoc OpenAPI UI**: For generating and serving OpenAPI documentation (Swagger UI).
*   **Lombok**: To reduce boilerplate code (e.g., getters, setters, constructors).
*   **Maven**: Build automation tool.
*   **Java 25**: Programming language version.

## Getting Started

### Prerequisites

*   Java Development Kit (JDK) 25
*   Maven
*   PostgreSQL database instance

### Installation

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/sauravwho/Urlify.git
    cd Urlify
    ```
2.  **Configure PostgreSQL:**
    *   Create a PostgreSQL database (e.g., `urlify_db`).
    *   Update the `src/main/resources/application.properties` (or `application.yml`) file with your PostgreSQL database credentials and connection details.

    ```properties
    # Example application.properties
    spring.datasource.url=jdbc:postgresql://localhost:5432/urlify_db
    spring.datasource.username=your_username
    spring.datasource.password=your_password
    spring.jpa.hibernate.ddl-auto=update
    spring.jpa.show-sql=true
    ```

3.  **Build the project:**
    ```bash
    mvn clean install
    ```

### Running the Application

You can run the application using Maven:

```bash
mvn spring-boot:run
```

Alternatively, you can run the generated JAR file:

```bash
java -jar target/Urlify-0.0.1-SNAPSHOT.jar
```

The application will start on `http://localhost:8080` by default.

## Usage

Once the application is running, you can interact with its RESTful API.

### API Endpoints

*   **Create Short URL**: `POST /api/v1/shorten`
    *   Request Body: `{"longUrl": "https://example.com/very/long/url"}`
    *   Response: `{"shortUrl": "http://localhost:8080/abcde"}`
*   **Redirect to Long URL**: `GET /{shortCode}`
    *   Example: `GET /abcde` will redirect to `https://example.com/very/long/url`

### API Documentation (Swagger UI)

Access the interactive API documentation at:
`http://localhost:8080/swagger-ui.html`

This interface allows you to explore the available endpoints, their parameters, and test them directly from your browser.
