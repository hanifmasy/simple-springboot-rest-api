
### Spring Boot Employee Management Application

This project is a simple Spring Boot application for managing employee records. It provides RESTful endpoints to perform CRUD operations on employee entities.

### Dependencies

- Java JDK and JRE v17
- Spring Boot 3.2.0
- Spring Data JPA
- Lombok
- PostgreSQL Database

### Gradle Configuration

Ensure your `build.gradle` file contains the following configuration:

```gradle
plugins {
    id 'org.springframework.boot' version '3.2.0'
    id 'io.spring.dependency-management' version '1.1.4'
    id 'java'
}

group = 'com.example'
version = '0.0.1-SNAPSHOT'
sourceCompatibility = '17'

repositories {
    mavenCentral()
}

dependencies {
    implementation 'org.springframework.boot:spring-boot-starter-data-jpa'
    implementation 'org.springframework.boot:spring-boot-starter-web'
    runtimeOnly 'org.postgresql:postgresql'
    testImplementation 'org.springframework.boot:spring-boot-starter-test'
}

test {
    useJUnitPlatform()
}
```

### Endpoints

- **GET /employee/v1/**
  - Fetches all employees from the database.

- **GET /employee/v1/{id}**
  - Fetches an employee by ID from the database.

- **POST /employee/v1/**
  - Saves a new employee entity to the database.

- **PUT /employee/v1/**
  - Updates an existing employee entity in the database.

- **DELETE /employee/v1/{id}**
  - Deletes an employee by ID from the database.

### How to Run

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/hanifmasy/simple-springboot-rest-api
   ```

2. **Navigate to Project Directory**:
   ```bash
   cd simple-springboot-rest-api
   ```

3. **Configure Database**:
   Update the `application.properties` file with your PostgreSQL database information:

   ```properties
   spring.datasource.url=jdbc:postgresql://localhost:5432/your_dbname
   spring.datasource.username=your_username
   spring.datasource.password=your_password
   spring.jpa.hibernate.ddl-auto=update
   spring.jpa.show-sql=true
   spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.PostgreSQLDialect
   ```

4. **Build the Project**:
   ```bash
   ./gradlew build
   ```

5. **Run the Application**:
   ```bash
   java -jar build/libs/simple-springboot-rest-api-0.0.1-SNAPSHOT.jar
   ```

### Project Structure

- `src/main/java/com/example/springboot/controller`: Contains REST controller classes.
- `src/main/java/com/example/springboot/entity`: Contains entity classes.
- `src/main/java/com/example/springboot/service`: Contains service classes.
