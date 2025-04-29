# Airbnb Clone Project

## Overview

The **Airbnb Clone Project** is a comprehensive, real-world application designed to simulate the development of a robust booking platform similar to Airbnb. This project serves as a capstone experience for learners aiming to sharpen their full-stack development skills, with an emphasis on backend systems, database architecture, API design, and security best practices.

Through this project, learners will gain practical experience building scalable web applications, working with development lifecycles, and collaborating within teams using modern DevOps tools and methodologies.

## Project Goals

- Understand and implement full-stack web development using modern tools and frameworks.
- Build a scalable and secure backend infrastructure.
- Design and optimize relational databases for real-world use cases.
- Develop RESTful APIs to support frontend functionality.
- Practice software engineering principles such as CI/CD, containerization, and security.
- Simulate professional workflows including version control, testing, and deployment pipelines.

## Team Roles

The Airbnb Clone Project simulates a real-world software development environment. Each team member may take on one or more of the following roles to ensure the successful delivery of the project:

### 1. Backend Developer
Responsible for building and maintaining the server-side logic, database interactions, APIs, and core application logic using Django. They ensure performance, scalability, and security of the backend infrastructure.

### 2. Database Administrator (DBA)
Designs, implements, and manages the MySQL database schema. They ensure data integrity, optimize queries, manage migrations, backups, and enforce data security and compliance.

### 3. DevOps Engineer
Implements CI/CD pipelines using tools like GitHub Actions, manages Docker containers, and oversees deployment processes. They ensure smooth integration, delivery, and infrastructure automation.

### 4. Security Specialist
Audits the application for vulnerabilities, implements authentication and authorization best practices, and ensures data protection through secure coding standards and encrypted communication.

### 5. QA Engineer / Tester
Designs and runs test plans to identify bugs and performance issues. They ensure code quality and user experience by writing unit, integration, and automated tests.



## Technology Stack
This project leverages a modern technology stack to simulate a real-world, full-stack web application. Below is a breakdown of the tools and technologies used, along with their roles in the project:

- **Backend Framework - Django**: A high-level Python web framework used to build the backend of the application. It provides a clean and pragmatic design for building RESTful APIs and managing complex business logic quickly and securely.

- **Database - MySQL**: A reliable, scalable, and widely-used relational database system. It stores structured application data, such as users, listings, bookings, reviews, and payments.

- **Containerization - Docker**: A containerization platform that allows the development environment, database, and application to run in isolated containers, ensuring consistency across development and production environments.

- **CI/CD - Git & GitHub**: Used for version control and collaborative development. GitHub also serves as the remote repository hosting platform and integrates with CI/CD pipelines.

- **Version Control - GitHub Actions**: A CI/CD tool that automates testing, building, and deployment workflows. It ensures that every code change is automatically tested and deployed in a consistent manner.

- **Other Tools - Postman** *(optional)*: An API testing tool used by developers and QA engineers to manually test endpoints, automate test scripts, and validate API responses.

- **API Design - GraphQL** *(optional enhancement)*: An alternative to REST for building APIs. It can be used to allow clients to request exactly the data they need, improving performance and flexibility.

- **API Design - Django REST Framework** *(optional enhancement)*: An extension to Django that makes it easier to build robust RESTful APIs, with features like authentication, serialization, and request/response handling.


These tools work together to support a secure, efficient, and scalable development process from local development to deployment.


## Database Design

The Airbnb Clone Project involves several interconnected entities that form the foundation of the application’s data model. Below is an overview of the core entities, their key fields, and how they relate to one another.

### 1. Users
Represents individuals who use the platform, either as guests or hosts.

**Key Fields:**
- `id`: Unique identifier for the user
- `username`: Unique display name
- `email`: User's email address
- `password`: Hashed password for authentication
- `is_host`: Boolean to distinguish between guests and hosts

**Relationships:**
- A user can own multiple properties.
- A user can make multiple bookings.
- A user can post multiple reviews.

**API Endpoints:**  
- `/users/`  
- `/users/{user_id}/`

---

### 2. Properties
Represents listings available for rent on the platform.

**Key Fields:**
- `id`: Unique identifier for the property
- `owner_id`: Foreign key to the Users table
- `title`: Short description or title of the property
- `location`: Address or city
- `price_per_night`: Cost per night

**Relationships:**
- A property is owned by one user (host).
- A property can have multiple bookings.
- A property can receive multiple reviews.

**API Endpoints:**  
- `/properties/`  
- `/properties/{property_id}/`

---

### 3. Bookings
Tracks reservation information for guests renting a property.

**Key Fields:**
- `id`: Unique identifier for the booking
- `user_id`: Foreign key to the Users table (guest)
- `property_id`: Foreign key to the Properties table
- `check_in`: Date of arrival
- `check_out`: Date of departure

**Relationships:**
- A booking is made by one user for one property.
- A booking can have one associated payment.

**API Endpoints:**  
- `/bookings/`  
- `/bookings/{booking_id}/`

---

### 4. Payments
Records payment transactions related to bookings.

**Key Fields:**
- `id`: Unique identifier for the payment
- `booking_id`: Foreign key to the Bookings table
- `amount`: Total paid
- `status`: e.g., pending, completed, failed
- `payment_method`: e.g., credit card, PayPal

**Relationships:**
- A payment is linked to one booking.

**API Endpoint:**  
- `/payments/`

---

### 5. Reviews
Stores feedback from users about properties.

**Key Fields:**
- `id`: Unique identifier for the review
- `user_id`: Foreign key to the Users table
- `property_id`: Foreign key to the Properties table
- `rating`: Numerical rating (e.g., 1–5)
- `comment`: Written feedback

**Relationships:**
- A review is written by one user for one property.

**API Endpoints:**  
- `/reviews/`  
- `/reviews/{review_id}/`

---

### Entity Relationships Summary

- **User ⟶ Properties**: One-to-Many (a user can own many properties)
- **User ⟶ Bookings**: One-to-Many (a user can make many bookings)
- **User ⟶ Reviews**: One-to-Many (a user can write many reviews)
- **Property ⟶ Bookings**: One-to-Many (a property can be booked many times)
- **Property ⟶ Reviews**: One-to-Many (a property can have many reviews)
- **Booking ⟶ Payment**: One-to-One (a booking has one payment)

This relational model ensures efficient data retrieval, integrity, and scalability.

## Feature Breakdown

The Airbnb Clone Project is designed to simulate core functionalities of a property rental platform. Below are the key features included in the application:

### 1. User Management
Users can register, log in, manage their profiles, and choose to act as hosts or guests. This ensures user-specific functionality and secure access to platform resources.

### 2. Property Management
Hosts can create, update, and delete property listings. Each property contains essential information such as location, price, and description, making it easy for guests to find suitable accommodations.

### 3. Booking System
Guests can browse available properties and book their stays based on availability. The system manages check-in and check-out details, ensuring a smooth reservation process.

### 4. Payment Processing
Secure payment functionality allows users to complete transactions for their bookings. This feature ensures accountability and financial tracking between hosts and guests.

### 5. Review System
After their stay, guests can leave ratings and comments on properties. This adds transparency and builds trust within the platform.

---

## API Security

Securing the backend APIs is a top priority for the project to protect sensitive user data and maintain platform integrity. The following security measures will be implemented:

- **Authentication**: Only verified users can access protected endpoints using secure token-based systems (e.g., JWT).
- **Authorization**: Role-based access control will ensure users only perform actions they’re permitted to (e.g., only hosts can manage listings).
- **Rate Limiting**: Limits the number of requests per user/IP to prevent abuse and denial-of-service attacks.
- **Input Validation and Sanitization**: Protects against common web attacks such as SQL injection and XSS.
- **HTTPS Enforcement**: Ensures encrypted data transmission between clients and the server.

**Why It Matters:**
- Protects personal and financial user information.
- Secures the booking and payment processes from fraud.
- Prevents unauthorized access to resources.

---

## CI/CD Pipeline

**CI/CD (Continuous Integration and Continuous Deployment)** pipelines automate the testing, building, and deployment of the application, ensuring faster and more reliable software delivery.

**Key Benefits:**
- Automatically tests code for bugs before merging into main branches.
- Speeds up deployment cycles with minimal human intervention.
- Reduces manual errors and improves collaboration.

**Tools Used:**
- **GitHub Actions**: Automates testing and deployment workflows.
- **Docker**: Provides a consistent development and production environment through containerization.
- **PostgreSQL/MySQL containers**: Simulated DB environments for integration tests.

This pipeline supports a smooth and efficient development lifecycle for the Airbnb Clone Project.


## Requirements

To successfully complete the project tasks, learners must:

- Have a [GitHub](https://github.com/Kaywuyep/airbnb-clone-project.git) account to create and manage repositories.
- Be familiar with Markdown syntax for creating and editing `README.md` files.
- Possess prior experience with backend frameworks like **Django** and database systems such as **MySQL**.
- Understand the software development lifecycle practices, including:
  - Application security
  - Continuous Integration/Deployment (CI/CD)
  - Database design and migrations
- Be comfortable using modern tools such as:
  - **Docker**
  - **GitHub Actions** or similar CI/CD platforms

## Getting Started

1. Clone this repository.
2. Set up your virtual environment and install dependencies.
3. Configure your local `.env` file with the necessary environment variables.
4. Run initial migrations and start the development server.

```bash
git clone https://github.com/Kaywuyep/airbnb-clone-project.git
cd airbnb-clone
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver

