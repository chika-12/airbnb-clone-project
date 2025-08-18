# About The Airbnb cone project.

The Airbnb Clone Project is a comprehensive, real-world application designed to simulate the development of a robust booking platform like Airbnb. It involves a deep dive into full-stack development, focusing on backend systems, database design, API development, and application security. This project enables learners to understand complex architectures, workflows, and collaborative team dynamics while building a scalable web application.

## Team Roles.

### Project Manager

Makes sure a product or its part is delivered on time and within budget. Manages and motivates the software development team.

### Software Developer

Engineers and stabilizes the product. Solves any technical problems emerging during the development lifecycle
Database Administrator:

### Test Automation Engineer

Designs a test automation ecosystem. Writes and maintains test scripts for automated testing.

### Devops Engineer

Facilitates cooperation between development and operations teams. Builds continuous integration and continuous delivery (CI/CD) pipelines for faster delivery.

### Quality Assurance Engineer

Makes sure an application performs according to requirements. Spots functional and non-functional defects

## Technology Stack.

#### Django: A high-level Python web framework used for building the RESTful API.

#### Django REST Framework: Provides tools for creating and managing RESTful APIs.

#### PostgreSQL: A powerful relational database used for data storage.

#### GraphQL: Allows for flexible and efficient querying of data.

#### Celery: For handling asynchronous tasks such as sending notifications or processing payments.

#### Redis: Used for caching and session management.

#### Docker: Containerization tool for consistent development and deployment environments.

#### CI/CD Pipelines: Automated pipelines for testing and deploying code changes.

## Database Design

**Entities**: Users, Properties, Bookings, Reviews and Payment

**Users**:
People who use the system — could be property owners (hosts) or customers (guests).

1. Key Fields:

- user_id (Primary Key, unique ID)
- name (Full name)
- email (Unique for login)
- role (enum: "host" or "guest")

#### Relationships:

- A User can own many Properties (if they are a host).
- A User can make many Bookings (if they are a guest).
- A User can write Reviews for Properties.

**Properties**:
These are listings (apartments, houses, hotels) that users can book.
1.Key Fields:

- property_id (Primary Key)
- title (e.g., "2-Bedroom Apartment in Lagos")
- location (City, State, GPS coordinates)
- price_per_night (numeric)
- owner_id (Foreign Key → Users.user_id)
  Relationships:
- A Property belongs to one User (host).
- A Property can have many Bookings.
- A Property can have many Reviews.

**Bookings**:
Represents when a guest reserves a property for specific dates.

1. Key Fields:

- booking_id (Primary Key)
- user_id (FK → Users.user_id, the guest making booking)
- property_id (FK → Properties.property_id)
- check_in_date
- check_out_date
- status (enum: "pending", "confirmed", "cancelled")
  Relationships:
- A Booking belongs to one User (guest).
- A Booking belongs to one Property.
- A Booking may generate a Payment.

**Reviews**
Feedback from guests about properties.

1. Key Fields:

- review_id (Primary Key)
- user_id (FK → Users.user_id, the reviewer)
- property_id (FK → Properties.property_id)
- rating (1–5 stars)
- comment (text)
  Relationships:
- A Review belongs to one User.
- A Review belongs to one Property.
- A Property can have multiple Reviews.

**Payments**
Tracks money paid by guests for bookings.

1. Key Fields:

- payment_id (Primary Key)
- booking_id (FK → Bookings.booking_id)
- amount (total price)
- payment_date
- status (enum: "paid", "failed", "refunded")
  Relationships:
- A Payment belongs to one Booking.
- A Booking can have one Payment.

## Feature Breakdown

```

```
