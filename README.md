# Drone and Photography/Videography Services Web Application
![download](https://github.com/user-attachments/assets/2412a487-6ff4-4838-aa99-886429d9e2ae)
## Introduction

This project aims to develop a web application that facilitates the hiring of drone and photography/videography services. It works similarly to Upwork, allowing clients to find and hire professionals, while service providers can showcase their work and secure jobs. The platform also integrates blockchain technology to manage secure escrow transactions and ensures compliance with international regulations. Additionally, the platform will scale across multiple countries and provide recommendations based on geographical location and reviews.

## Features


### Core Features
- **User Roles & Authentication**: 
  - Role-based access control for Clients, Service Providers, and Admins.
  - Secure user registration and authentication using JWT tokens.

- **Service Listings & Search**:
  - Service providers can create listings for their drone or photography services.
  - Clients can search and filter providers based on location, ratings, and reviews.

- **Booking & Payment**:
  - Clients can book services, and payments will be managed via blockchain escrow to ensure safe transactions.
  - Integration with both cryptocurrency (e.g., Ethereum) and traditional payment gateways (Stripe/PayPal).

- **Reviews & Ratings**:
  - Clients can leave reviews and ratings after service completion.
  - Service providers can display their portfolios and feedback.

- **Admin Panel**:
  - Admins can manage users, service listings, payments, and compliance with international tax and data protection regulations.

### Additional Features
- **Geographical Recommendations**: Services will be recommended based on the client's geographical location.
- **Compliance Features**: The app will comply with international tax regulations, data protection (e.g., GDPR), and other legal requirements.
- **Scalability**: The platform will be designed to scale across multiple countries, with support for multiple currencies and languages.
- **Caching with Redis**: To enhance performance, frequently accessed data will be cached using Redis.
- **Metrics and Monitoring**: Metrics collection and monitoring will be implemented to track system performance and usage statistics.
- **Data Export**: Users can export booking, payment, and service data into Excel format for statistical analysis, as well as PDF format for reporting and documentation.

## Technology Stack

### Frontend:
- **Framework**: React.js or Vue.js
- **Mobile App**: React Native
- **State Management**: Redux or Vuex
- **UI Framework**: Tailwind CSS or Bootstrap

### Backend:
- **Framework**: Node.js (Express) or Django (Python)
- **API**: RESTful API or GraphQL
- **Authentication**: JWT for token-based authentication
- **Caching**: Redis for caching frequently accessed data.

### Blockchain & Payments:
- **Blockchain Network**: Ethereum or Hyperledger for managing secure escrow transactions.
- **Smart Contracts**: To handle payment transactions between clients and providers.
- **Traditional Payment Gateways**: Stripe and PayPal for fiat currency payments.

### Databases:
- **Primary DB**: MongoDB or PostgreSQL
- **Redis**: For caching and improving performance.
- **Blockchain Integration**: For escrow and secure payments.

### Metrics and Monitoring:
- **Prometheus & Grafana**: For monitoring system metrics such as API response times, CPU/memory usage, and user activity.
- **Log Aggregation**: ELK Stack (Elasticsearch, Logstash, Kibana) for error tracking and analysis.

### Data Export:
- **Excel Export**: Export system data to Excel format using `pandas` or `xlsxwriter` (Python) or `exceljs` (Node.js).
- **PDF Export**: Generate PDF reports using `pdfkit` (Python) or `pdfmake` (Node.js).

### DevOps:
- **Containerization**: Docker and Kubernetes
- **CI/CD**: GitHub Actions or Jenkins for automated deployment
- **Cloud Hosting**: AWS, GCP, or Azure with load balancing and auto-scaling
- **Monitoring**: Prometheus, Grafana, and ELK Stack

## API Endpoints

| **Endpoint**             | **Method** | **Description**                                      | **Authentication**  |
|--------------------------|------------|------------------------------------------------------|---------------------|
| `/api/auth/register`      | POST       | Registers a new user                                 | No                  |
| `/api/auth/login`         | POST       | Logs in a user and returns a JWT                     | No                  |
| `/api/services`           | GET        | Fetches all available drone/photography services      | No                  |
| `/api/services`           | POST       | Adds a new service (service provider only)            | Yes (Provider)      |
| `/api/services/{id}`      | GET        | Fetches details of a specific service                 | No                  |
| `/api/bookings`           | POST       | Books a service and initiates escrow payment          | Yes (Client)        |
| `/api/bookings/{id}`      | GET        | Fetches booking details for a specific service        | Yes (Client/Provider)|
| `/api/reviews`            | POST       | Posts a review for a completed service                | Yes (Client)        |
| `/api/profile`            | GET        | Fetches the user profile                              | Yes (User)          |
| `/api/profile`            | PUT/PATCH  | Updates user profile (service provider or client)     | Yes (User)          |
| `/api/admin/users`        | GET        | Fetches all registered users (admin only)             | Yes (Admin)         |
| `/api/admin/reports`      | GET        | Retrieves financial and compliance reports (admin)    | Yes (Admin)         |
| `/api/export/excel`       | GET        | Exports data to Excel format for statistical analysis | Yes (User/Admin)    |
| `/api/export/pdf`         | GET        | Exports data to PDF format for reporting              | Yes (User/Admin)    |
| `/api/metrics`            | GET        | Fetches system metrics and performance statistics     | Yes (Admin)         |

## Project Milestones

### Milestone 1: Requirements Gathering and Planning
- Deliverables: Requirements document, feasibility study, scope, and timeline.

### Milestone 2: System Design
- Deliverables: Architecture design, technology stack selection, database schema, and API design.

### Milestone 3: Frontend Development
- Deliverables: Wireframes, responsive UI components, and API integration.

### Milestone 4: Backend Development
- Deliverables: REST/GraphQL APIs, blockchain integration, distributed database setup, Redis caching.

### Milestone 5: Payment and Compliance Integration
- Deliverables: Payment gateway integration, tax calculation, and data protection mechanisms.

### Milestone 6: Data Export and Metrics Integration
- Deliverables: Excel/PDF export functionality, system metrics collection, and monitoring setup.

### Milestone 7: Testing
- Deliverables: Unit testing, integration testing, system testing, and user acceptance testing.

### Milestone 8: Deployment
- Deliverables: Cloud infrastructure setup, CI/CD pipeline, load balancing, and monitoring setup.

### Milestone 9: Monitoring and Maintenance
- Deliverables: Monitoring tools, logging, and ongoing maintenance.

## Getting Started

### Prerequisites
- **Node.js** (v14.x or later)
- **MongoDB** or **PostgreSQL** database setup
- **Redis** for caching
- **Docker** (for containerization)
- **Ethereum/Hyperledger** blockchain environment

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/ngemuantony/drone-photography-services.git
   cd drone-photography-services
2. Install dependencies:
   ```bash
   npm install
3. Set up environment variables:
   Create a .env file with the following details:
    ```bash
    DATABASE_URI=mongodb://localhost:27017/yourdb
    REDIS_URI=redis://localhost:6379
    JWT_SECRET=your_jwt_secret
    PAYMENT_GATEWAY_KEY=your_payment_gateway_key
4. Start the development server:
   ```bash
   npm run dev
