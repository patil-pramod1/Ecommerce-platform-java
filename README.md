# E-Commerce Platform — Java

A full-stack e-commerce web application built with Java, JSP, Servlets, MySQL, and a Maven-based WAR project. The application is structured around DAO and service layers and includes core shopping workflows such as product management, cart operations, orders, reviews, wishlists, seller functionality, email utilities, and Razorpay payment integration.

## Overview

This project demonstrates a traditional Java web application with server-side rendering and a relational database backend. The main application lives under `E-commerce website/Shopping-cart` and is packaged as a WAR for deployment to a compatible Java application server.

## Features

- Product browsing and product details
- Shopping cart management
- Order creation and order-related operations
- Wishlist support
- Product reviews
- Seller-related operations and product management
- User account/data access
- MySQL-backed persistence using JDBC
- Razorpay payment integration
- Email functionality
- JSP/JSTL-based server-side web views

## Tech Stack

| Layer | Technology |
| --- | --- |
| Language | Java 22 |
| Build | Maven |
| Packaging | WAR |
| Web | Jakarta Servlets, JSP, JSTL |
| Backend Architecture | DAO + Service/Implementation layers |
| Database | MySQL |
| Payments | Razorpay Java SDK |
| JSON | Jakarta JSON |
| Email | Apache Commons Email / Jakarta Mail |
| Web Technologies | HTML, CSS, JavaScript |

The Maven configuration currently targets Java 22 and includes Jakarta EE, Servlet, MySQL Connector/J, Razorpay, JSON, mail, and JSTL dependencies.

## Project Structure

```text
Ecommerce-platform-java/
├── E-commerce website/
│   └── Shopping-cart/
│       ├── pom.xml
│       └── src/
│           └── main/
│               ├── java/
│               │   └── com/shoppingcart/
│               │       ├── connection/
│               │       ├── dao/
│               │       ├── service/
│               │       ├── servlet/
│               │       └── usermodel/
│               └── webapp/
└── Servers/
```

The DAO layer contains persistence-focused components for products, carts, orders, users, sellers, reviews, and wishlists, while the service layer provides application-level operations.

## Getting Started

### Prerequisites

- JDK 22
- Maven 3.8+
- MySQL 8+
- A Jakarta EE-compatible application server/runtime capable of deploying a WAR

### 1. Clone the repository

```bash
git clone https://github.com/patil-pramod1/Ecommerce-platform-java.git
cd Ecommerce-platform-java
```

### 2. Configure MySQL

Create the database used by the application and update the database connection settings in the project's connection/configuration code.

> Do not commit real database credentials, email passwords, or payment credentials to Git.

### 3. Configure third-party integrations

Add the required credentials/configuration for Razorpay, your email service, and MySQL. Use environment variables or an external configuration mechanism for production credentials.

### 4. Build the WAR

```bash
cd "E-commerce website/Shopping-cart"
mvn clean package
```

The generated WAR will be available under `target/`.

### 5. Deploy

Deploy the generated WAR file to a Jakarta EE-compatible server and start the application.

## Architecture

```text
JSP / Web UI
      ↓
Servlet Controllers
      ↓
Service Layer
      ↓
DAO Layer
      ↓
MySQL
```

This separation keeps database access, business operations, and web concerns organized and easier to maintain.

## Database

The application uses MySQL with JDBC-based data access. DAO components execute SQL using prepared statements and map database records into Java model objects.

## Payments & Email

Razorpay is included for payment processing, while email-related dependencies support application email functionality. Keep external credentials outside source control.

## Development Notes

The repository contains an Eclipse/Maven-style Java web project. IDE metadata is present alongside the Maven build configuration, so the project can be imported into Eclipse or built from the command line with Maven.

## Roadmap

- Environment-based configuration management
- Automated tests for DAO and service layers
- Centralized exception handling and validation
- Improved authentication/authorization
- API-first endpoints for modern frontends
- Dockerized local development
- CI/CD with automated build and test checks

## Contributing

1. Fork the repository.
2. Create a feature branch.
3. Make your changes.
4. Run the Maven build/tests.
5. Open a pull request with a clear description.

## License

No license is currently specified for this repository. Add a `LICENSE` file if you intend to publish the project for reuse.
