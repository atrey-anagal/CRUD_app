```markdown
# CRUD Application with Spring Boot

This project demonstrates a simple CRUD (Create, Read, Update, Delete) application using Spring Boot with an H2 in-memory database. It provides RESTful APIs to manage books, including functionalities to retrieve all books, retrieve a book by ID, add a new book, update an existing book, and delete a book.

## Prerequisites

- Java 17
- Maven
- IDE (Eclipse, IntelliJ IDEA, etc.)

## Setup Instructions

1. **Clone the Repository:**
   ```bash
   git clone <repository-url>
   cd CRUDApplication
   ```

2. **Build the Project:**
   ```bash
   mvn clean install
   ```

3. **Run the Application:**
   ```bash
   java -jar target/CRUDApplication-0.0.1-SNAPSHOT.jar
   ```
   Alternatively, you can run it directly from your IDE by running the `CrudApplication` class which contains the main method.

4. **Access H2 Console:**
   Once the application is running, you can access the H2 in-memory database console:
   - URL: [http://localhost:9090/h2](http://localhost:9090/h2)
   - JDBC URL: `jdbc:h2:mem:testdb`
   - Username: `sa`
   - Password: (leave it blank)

## API Endpoints

- **GET /getAllBooks**
  - Retrieves all books from the database.
  - Returns:
    - `200 OK` with a list of books if successful.
    - `204 No Content` if no books are found.

- **GET /getBookById/{id}**
  - Retrieves a book by its ID.
  - Path Variable: `{id}` is the ID of the book.
  - Returns:
    - `200 OK` with the book details if found.
    - `404 Not Found` if the book with the specified ID does not exist.

- **POST /addBook**
  - Adds a new book to the database.
  - Request Body: JSON object representing the book (`title` and `author`).
  - Returns:
    - `200 OK` with the added book details.

- **POST /updateBookById/{id}**
  - Updates an existing book by its ID.
  - Path Variable: `{id}` is the ID of the book to update.
  - Request Body: JSON object containing updated `title` and `author`.
  - Returns:
    - `200 OK` with the updated book details if successful.
    - `404 Not Found` if the book with the specified ID does not exist.

- **DELETE /deleteBookById/{id}**
  - Deletes a book by its ID.
  - Path Variable: `{id}` is the ID of the book to delete.
  - Returns:
    - `200 OK` on successful deletion.

## Technologies Used

- **Spring Boot:** Simplifies the development of Spring applications.
- **Spring Data JPA:** Provides easy integration with JPA repositories.
- **H2 Database:** In-memory database for development and testing.
- **Lombok:** Reduces boilerplate code by providing annotations.

## Project Structure

```
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com.example.CRUDApplication/
│   │   │       ├── controller/
│   │   │       │   └── BookController.java
│   │   │       ├── model/
│   │   │       │   └── Book.java
│   │   │       ├── repo/
│   │   │       │   └── BookRepo.java
│   │   │       └── CrudApplication.java
│   │   └── resources/
│   │       └── application.properties
│   └── test/
│       └── java/
│           └── com.example.CRUDApplication/
│               └── controller/
│                   └── BookControllerTest.java
└── pom.xml
```

## Notes

- The application uses annotations like `@RestController`, `@Entity`, `@Repository`, and `@Autowired` for implementing RESTful services and managing data persistence.
- Tests are included under `src/test` to ensure the correctness of API endpoints.

## Further Improvements

- Implement validation for request payloads (e.g., using `@Valid` and `@NotBlank`).
- Enhance error handling and exception management.
- Add logging and security measures depending on deployment requirements.

This README provides an overview of the CRUDApplication project, demonstrating how to set up, run, and use the application effectively. Adjustments and enhancements can be made based on specific project requirements and deployment environments.
```
