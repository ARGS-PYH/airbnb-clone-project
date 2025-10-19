# 🏡 Airbnb Clone Project

## 📖 Project Overview
The **Airbnb Clone Project** is a backend-focused web application that replicates key functionalities of Airbnb, including property listings, bookings, payments, and user management. The goal of this project is to build a scalable and secure API-based system using modern web technologies.  

This project is part of an ALX software engineering module focused on backend design, database architecture, and DevOps practices.

---

## 🧰 Technology Stack

| Technology | Description |
|-------------|--------------|
| **Django** | A high-level Python web framework that simplifies backend development by providing built-in tools for routing, ORM, authentication, and security. It serves as the backbone of the application. |
| **Django REST Framework (DRF)** | A powerful and flexible toolkit for building RESTful APIs in Django. It simplifies serialization, authentication, and API endpoint creation. |
| **PostgreSQL** | A robust open-source relational database used to store structured data such as users, properties, bookings, and payments. |
| **GraphQL** | A query language and runtime for APIs that allows clients to request exactly the data they need, improving performance and efficiency. |
| **Celery** | A distributed task queue used for handling asynchronous operations like sending email notifications or processing background tasks. |
| **Redis** | An in-memory data store used for caching and message brokering to enhance speed and performance. |
| **Docker** | A containerization platform that ensures consistent environments across development, testing, and deployment. |
| **GitHub Actions (CI/CD)** | Automates testing, building, and deployment processes to ensure continuous integration and delivery. |

---

## 🗃️ Database Design

### Key Entities and Relationships

| Entity | Key Fields | Description |
|---------|-------------|-------------|
| **User** | `id`, `name`, `email`, `password`, `role (host/guest)` | Represents the users of the platform. A user can list properties (as a host) or make bookings (as a guest). |
| **Property** | `id`, `title`, `description`, `price_per_night`, `location`, `host_id` | Represents a rental property listed by a host. Each property is owned by one user (host). |
| **Booking** | `id`, `property_id`, `guest_id`, `check_in`, `check_out`, `total_price`, `status` | Represents a reservation made by a guest for a specific property. Each booking belongs to one user (guest) and one property. |
| **Payment** | `id`, `booking_id`, `amount`, `payment_method`, `payment_status`, `timestamp` | Records payment transactions related to bookings. Each payment is linked to a booking. |
| **Review** | `id`, `user_id`, `property_id`, `rating`, `comment`, `created_at` | Allows users to review properties after a booking. A property can have multiple reviews. |

### Relationships
- A **User** can have multiple **Properties**.
- A **Property** can have multiple **Bookings** and **Reviews**.
- A **Booking** belongs to one **Property** and one **User** (guest).
- A **Payment** is linked to a **Booking**.
- A **Review** is linked to both a **User** and a **Property**.

---

## ⚙️ Feature Breakdown

| Feature | Description |
|----------|--------------|
| **User Management** | Handles user registration, authentication, and profile management. Supports roles for hosts and guests. |
| **Property Management** | Enables hosts to create, update, and manage property listings with details such as title, price, and location. |
| **Booking System** | Allows guests to view available properties, check availability, and make bookings. Ensures booking validation and prevents double bookings. |
| **Payment Processing** | Manages secure payment transactions for bookings. Integrates payment gateways and records payment history. |
| **Review and Rating System** | Lets guests leave reviews and ratings for properties they’ve stayed in. Helps maintain transparency and trust on the platform. |
| **Search and Filter** | Allows users to search and filter properties by price, location, or amenities for better user experience. |
| **Admin Dashboard (Optional)** | Provides administrative control for managing users, properties, and transactions. |

---

## 🔒 API Security

### Key Security Measures
| Security Feature | Description | Importance |
|------------------|-------------|-------------|
| **Authentication** | Uses JWT (JSON Web Token) or session-based authentication to verify user identity. | Prevents unauthorized access to APIs. |
| **Authorization** | Ensures users only access resources and actions permitted to their role (host or guest). | Protects sensitive actions and data. |
| **Data Validation & Sanitization** | Validates user inputs and sanitizes data before saving to the database. | Prevents injection attacks and ensures data integrity. |
| **Rate Limiting** | Limits the number of API requests per user or IP within a certain timeframe. | Protects against abuse and denial-of-service (DoS) attacks. |
| **Encryption** | Uses HTTPS and encrypts sensitive data (e.g., passwords, payment info). | Protects user data during transmission. |

**Why Security Matters:**  
Securing backend APIs is essential for protecting user data, preventing fraudulent transactions, and ensuring trust within the platform. For a system that handles personal and financial information, robust API security is non-negotiable.

---

## 🚀 CI/CD Pipeline

### What is CI/CD?
**Continuous Integration (CI)** is the practice of frequently merging code changes into a shared repository, where automated tests ensure stability.  
**Continuous Deployment/Delivery (CD)** automates the release process, ensuring new changes are safely and quickly deployed to production.

### Importance for the Project
- Reduces bugs by automatically testing each new code commit.  
- Ensures consistent, reliable deployments.  
- Encourages collaboration among developers.  
- Speeds up feature delivery and updates.

### Tools Used
| Tool | Purpose |
|------|----------|
| **GitHub Actions** | Automates testing, building, and deployment workflows directly from the repository. |
| **Docker** | Ensures consistency between development and production environments. |
| **Celery + Redis** | Manages background tasks efficiently during deployment. |
| **PostgreSQL** | Provides a reliable database service for continuous integration testing. |

---

## 🧩 Author
**Name:** Damilare Aderinwale Animasaun  
**GitHub:** [@DreAnimasaun](https://github.com/DreAnimasaun)  
**Program:** ALX Software Engineering – Backend Specialization  

---

## 📝 License
This project is created for educational purposes under the ALX Software Engineering program. It may be reused or modified for learning and demonstration purposes.