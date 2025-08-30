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

**_Django_**: A high-level Python web framework used for building the RESTful API.

**_Django REST Framework_**: Provides tools for creating and managing RESTful APIs.

**_PostgreSQL_**: A powerful relational database used for data storage.

**_GraphQL_**: Allows for flexible and efficient querying of data.

**_Celery_**: For handling asynchronous tasks such as sending notifications or processing payments.

**_Redis_**: Used for caching and session management.

**_Docker_**: Containerization tool for consistent development and deployment environments.

**_CI/CD Pipelines_**: Automated pipelines for testing and deploying code changes.

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

1. User Management

- Manages user registration and access and authorization.

2. Property Management

- Manages the properties, it provides handlers for property listing, deletion, update etc

3. Booking System

- This sytem will be responsible for booking giving the users routes to book hotel

4. Payment System

- For making making payment and also retriving payment and accessing payment history

5. Review and Ratings

- For customer review of service provided and service ratings

6. Database Optimization

- Saving all data.

7. User Authentication

- This feature helps in protecting the app, it ensures that app is only registered users have access and restrict users access.

## API Security

For securing an application certain measures are taken

- Athentication
  Before the user is logged in the server checks if the user email address and password in the database is same as the email address and password that the user entered and the an acceess and refresh token is then asigned which would be used for request assess.

- Authorization
  This restricts the access of the user. user can only access certain routes.

- Rate Limiter
  This limits the amount of request a user can make over a given time.

- Data protection
  This include encryption of sensitive data and input validation and sanitization
  and avoid sensitive data exposure.

- CORS (Cross-Origin Resource Sharing)
  Restrict origins that can access your API.

- Framework & Middleware Security
- Helmet (Express.js)
- Adds security headers like CSP, HSTS, X-Frame-Options.
- CSRF protection
- Use CSRF tokens for forms.
- Error handling
- Don’t leak stack traces in production (attackers can use them).

## CI/CD Pipeline

Tools that could be used for CI/CD Pipeline

- Github Actions
- Docker
- Jenkins
- Circle CLI

## UI/UX Design Planning.
- Create intuitive booking flow
- Maintain visual consistency
- Ensure fast loading times
- Prioritize mobile responsiveness

## Project Roles and Responsibilities

1. Project Manager: Incharge of the entire project
2. Frontend Developers: Builds the user interface
3. Backend Developers: Responsible for server side logic
4. Designers: Designs the user interface
5. QA/Testers: Test the software to find bugs 
6. DevOps Engineers: Deployment of the server
7. Product Owner: Owner of the app.
8. Scrum Master: 
