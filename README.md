# AirBnB Clone Backend

## :rocket: Objective

The backend for the Airbnb Clone project is designed to provide a robust and 
scalable foundation for managing user interactions, property listings, booking and payments. This backend will support various functionalities required to 
mimic the core features of Airbnb, ensuring a smooth experience for users and 
hosts.

## :trophy: Project Goals

**User Management**: Implement a secure system for user registration, authentication and profile management.

**Property Management**: Develop features for property listing creation, updates and retrieval.

**Booking System**: Create a booking mechanism for users to reserve properties and manage booking details.

**Payment Processing**: Integrate a payment system to handle transactions and record payment details.

**Review System**: Allow users to leave reviews and ratings for properties.

**Data Optimization**: Ensure efficient data retrieval and storage through database optimizations.

## :gear: Technology Stack

**Django**: A high-level Python web framework used for building the RESTful API.

**Django REST Framework**: Provides tools for creating and managing RESTful APIs.

**PostgreSQL**: A powerful relational database used for data storage.

**GraphQL**: Allows for flexible and efficient querying of data.

**Celery**: For handling asynchronous tasks such as sending notifications or processing payments.

**Redis**: Used for caching and session management.

**Docker**: Containerization tool for consistent development and deployment environments.

**CI/CD Pipelines**: Automated pipelines for testing and deploying code changes.

## :busts_in_silhouette: Team Roles and Responsibilities

**Backend Developer**: Implements API endpoints, database schemas, business logic and third-party integration.

**Database Administrator**: Manages database design, indexing and optimizations.

**Devops Engineer**: Handles deployment, monitoring and sclaing of the backend servives.

**QA Engineer**: Ensures the backend functionalities are thoroughly tested and meet the functional and non-functional requirements.

## :memo: Database Design

### Entities

1. **Users**
   * *username* (String)
   * *password* (String)
   * *email* (String)
   * *phone* (String)
   
2. **Properties**
   * *user_id* (Foreign Key, Integer)
   * *location* (Decimal)
   * *number_rooms* (Integer)
   * *amenities* (String)
   * *price_per_night* (Decimal)
   
3. **Bookings**
   * *user_id* (Foreign Key, Integer)
   * *property_id* (Foreign Key, Integer)
   * *check_in_date* (Date)
   * *check_out_date* (Date)
   * *total_price* (Decimal)
   
4. **Payments**
   * *payment_id* (Primary Key, Integer)
   * *booking_id* (Foreign Key, Integer)
   * *amount* (Decimal)
   * *date* (Date)
   * *transaction_id* (string)
   
5. **Reviews**
   * *user_id* (Foreign Key, Integer)
   * *property_id* (Foreign Key, Integer)
   * *rating* (Integer)
   * *comment* (Integer)

### Relations

* **Users** can have multiple **Properties**.
* **Users** can book many **Properties**.
* **Users** can pay for many **Bookings**.
* **Users** can review many **Properties**.

* **Properties** belong to only one **User**.
* **Properties** can have many **Bookings**.
* **Properties** can be reviewed by many **Users**.

* **Bookings** relate to only one **Property**.

* **Payments** can include many **Bookings**.

* **Reviews** relate to only one **Property**.

## :hammer_and_pick: Feature Breakdown

### User Management
* Register users
* Authenticate (log in) users
* Modify users personal infos (profile)

### Property Management
* Register properties
* List properties
* Modify properties details
* Search for properties

### Booking System
* Book properties
* Modify booking details

### Payment Processing
* Pay for bookings
* Record payments

### Review system
* Rate properties
* Comment properties

### Data Optimization
* Build a scalable and fault-tolerant database
* Improve database performance using indexing and caching

## :shield: API Security

**Authentication**: Verify the identity of a user.

**Authorization**: Determine whether an authenticated user has permission to access specific resources or perform certain actions.

**Rate Limiting**: Control the number of requests a user can make to the API within a specified time frame.

Implement these security measures are crucial and will provide a safe and good user experience:

**User Management**: Identify users and let them manage their personal data.

**Property Management**: Allow users that own properties to manage them.

**Booking System**: Allow only users to book properties.

**Payment Processing**: Secure payments by encrypting traffic between users and the API.

**Review System**: Allow users to review properties they booked and paid.

**Data Optimization**: Ensure performance and high availability by limiting access to the database.

## :globe_with_meridians: CI/CD Pipeline

**CI/CD pipelines** are automated workflows that help software development teams integrate code changes, test them, and deploy applications efficiently. They consist of **continuous integration (CI)**, which merges code changes into a shared repository, and **continuous delivery/deployment (CD)**, which automates the release of software to production environments.

Using CI/CD pipelines will speed up development and deployment by frequently integrating code changes, automating the build, test, and deployment processes and enabling easier rollbacks in case of failure or issues in production.

**CI/CD Tools**: Jenkins, GitHub Actions, Travis CI.
