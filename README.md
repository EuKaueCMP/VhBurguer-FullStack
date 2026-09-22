# VhBurguer

VhBurguer is a full-stack web application developed to manage the digital catalog of a burger restaurant.

The project provides a public-facing menu and an administrative interface for managing products, categories, promotions, users, and product change history.

The application was developed using a layered backend architecture inspired by Domain-Driven Design concepts, with separation between domains, repositories, DTOs, services, business rules, and controllers.

## About the Project

The main goal of VhBurguer is to provide a centralized system for managing a restaurant's product catalog.

The application separates the public menu from administrative operations. Customers can access the available products, while authenticated users can manage products, categories, and promotions through the administrative interface.

The backend exposes a REST API responsible for authentication, business rules, persistence, product management, category management, promotions, and change history.

The frontend consumes this API through Axios and provides the web interface using Next.js, React, and TypeScript.

## Main Features

### Public Menu

The public interface provides:

- Restaurant homepage
- Product listing
- Product information
- Product categories
- Product images
- Product prices
- Restaurant units
- Promotional content

The product listing is loaded dynamically from the backend API.

### Authentication

The administrative area uses JWT-based authentication.

The login process is:

1. User enters email and password.
2. Frontend sends the credentials to the API.
3. API validates the user.
4. API generates a JWT.
5. Frontend stores the token using `react-secure-storage`.
6. Axios automatically attaches the token to subsequent requests.

Authenticated requests use:

```text
Authorization: Bearer <JWT>