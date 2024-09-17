# Contributing to Drone and Photography/Videography Services Web Application

Thank you for your interest in contributing to the Drone and Photography/Videography Services Web Application! We appreciate your involvement in improving the platform. This document outlines the contribution guidelines, including how to set up the project locally, how to work on a feature, and the process for submitting a pull request.

## Table of Contents

1. [Getting Started](#getting-started)
2. [Branching Model](#branching-model)
3. [Code Guidelines](#code-guidelines)
4. [Commit Messages](#commit-messages)
5. [Creating a Pull Request](#creating-a-pull-request)
6. [Code Review Process](#code-review-process)
7. [Community Code of Conduct](#community-code-of-conduct)
8. [License](#license)

## Getting Started

### Fork the Repository
1. Fork this repository to your own GitHub account by clicking the "Fork" button at the top of this repository's page.
2. Clone the forked repository to your local machine:
   ```bash
   git clone https://github.com/ngemuantony/drone-photography-services.git
   cd drone-photography-services

## Setting Up the Environment
### Install all necessary dependencies:
  ```bash
    npm install
### Set up your environment variables by creating a .env file in the root directory:
```bash
  DATABASE_URI=mongodb://localhost:27017/yourdb
  REDIS_URI=redis://localhost:6379
  JWT_SECRET=your_jwt_secret
  PAYMENT_GATEWAY_KEY=your_payment_gateway_key
  Start the development server:

```bash
  npm run dev
### Ensure that Redis is running locally or that you are using a cloud-based Redis service:

```bash
  redis-server

