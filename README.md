# 🏥 MedTrack – Web-Based Health Tracking System

MedTrack is a web-based health management application designed to enable users to securely, systematically, and efficiently manage their personal health information. The project was developed using Spring Boot and designed in accordance with layered architecture principles, relational database design practices, and role-based access control mechanisms.

This project was developed collaboratively by a two-member team and implemented by considering all technical and architectural requirements specified in the course guidelines. The system was further improved and restructured based on the feedback received for the midterm project.

---

## 📌 Project Features

* User registration, authentication, and authorization system
* Role-based endpoint security
* Management of health records, prescriptions, medications, and user roles
* Relational database model and EER diagram
* RESTful controller architecture
* Global exception handling
* API endpoints testable through Postman

---

## 🗄️ Database Design and Relationships

The project is built on a relational database consisting of at least five tables, including a join table implementing a many-to-many relationship.

### Relationship Types and Annotations Used

The following JPA/Hibernate annotations are each used at least once within the project:

* `@OneToOne`
* `@OneToMany`
* `@ManyToOne`
* `@ManyToMany`
* `@JoinColumn`
* `@JoinTable`

### EER Diagram

The EER diagram showing the tables and their relationships is included in the `/docs` directory together with the project source code.

The diagram was generated using MySQL Workbench reverse engineering tools and manually verified.

---

## 🔁 Relationship Ownership (Owning Side / Inverse Side)

For bidirectional relationships, the owning side and inverse side have been explicitly defined.

Documentation regarding relationship ownership is provided in:

```text
/docs/RELATIONSHIPS.md
```

For inverse-side entities, the necessary operations to break owning-side relationships during DELETE operations have been implemented and documented.

---

## 🔗 Cascade and Fetch Configurations

* At least one relationship is configured with `CascadeType.ALL`.
* At least one relationship uses cascade operations excluding DELETE.
* Relationships with custom `FetchType.EAGER` and `FetchType.LAZY` configurations have been implemented.
* Both unidirectional and bidirectional relationships are used throughout the application.

---

## 🌐 Controller and REST API Structure

Endpoints supporting the following HTTP methods have been implemented for each table/entity:

* GET
* POST
* PUT
* PATCH
* DELETE

Controller classes are organized into separate files and endpoints according to user roles and responsibilities.

The Postman collections required for testing the endpoints are located in the:

```text
/postman
```

directory.

---

## 🔐 Security (Spring Security)

The project uses Spring Security for authentication and endpoint protection.

### Security Features

* At least 3 roles
* At least 3 users
* Each user is assigned at least one role
* User passwords are stored in the database using BCrypt hashing

The default Spring Security tables:

```text
users
authorities
```

have **not** been used.

Instead, custom tables such as:

```text
members
roles
```

have been implemented.

Role-based and HTTP method-based endpoint access rules have been documented in tabular form.

At least one access rule has been defined for each HTTP method.

---

## ⚠️ Global Exception Handling

The project includes at least one Global Exception Handling mechanism consisting of:

* Custom exception classes extending `RuntimeException`
* Custom error response classes
* REST services configured to throw exceptions when necessary
* `@ControllerAdvice`
* `@ExceptionHandler`

---

## 🧩 Annotations Used

The following annotations are each used at least once within the project:

```java
@Value
@RestController
@RequestMapping
@GetMapping
@PostMapping
@PutMapping
@PatchMapping
@DeleteMapping
@Autowired
@Qualifier
@Primary
@Lazy
@PostConstruct
@PreDestroy
@Configuration
@Bean
@Entity
@Table
@Id
@Column
@GeneratedValue
@Repository
@Service
@Transactional
@PathVariable
@ControllerAdvice
@ExceptionHandler
```

---

## ⚙️ Technical Details

* The project was developed without using Spring Data JPA and Spring Data REST.
* Compatible with relational database management systems such as MySQL.
* Includes an example of retrieving query results using TypedQuery.
* The `server.port` property is configured to use a port other than the default `8080`.
* Basic username-password authentication (`user / password`) is enabled.
* Spring Boot Actuator is integrated.

### Actuator Endpoints

```text
/actuator/health
/actuator/info
```

These endpoints return project-related information.

---

## 📁 Project Structure

The source code is organized according to layered architecture principles:

```text
controller/
service/
repository/
entity/
config/
exception/
docs/
postman/
```

---

## 👥 Contributors

This project was developed collaboratively by:

* dilaydeveci00
* edaakkus

---

## ✅ Conclusion

The MedTrack project was designed and implemented to fully satisfy all requirements specified in the project proposal and course guidelines. It provides a comprehensive example of software architecture, security, relational database design, and RESTful service development using Spring Boot.

---

## 📄 License

This project was developed for educational purposes.
