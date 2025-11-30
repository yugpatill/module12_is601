# Module 12 — User & Calculation Routes + Integration Testing

This project implements user authentication and full CRUD operations for calculations using FastAPI, SQLAlchemy, and Pydantic. Integration tests validate all functionality, and GitHub Actions automatically builds, scans, tests, and deploys a Docker image to Docker Hub.

---

## 📘 Reflection

This module helped me understand secure backend development using FastAPI. I learned how to implement user registration and login with hashed passwords, create validated API schemas using Pydantic, and build complete CRUD routes for calculations. I also gained experience writing integration tests that interact with a real Postgres database.

The biggest challenges were fixing package dependency conflicts, configuring GitHub Actions to run tests reliably, and ensuring that Docker images only pushed after tests passed. Setting up Trivy scanning also taught me how vulnerability scanning integrates into CI/CD pipelines. Overall, this module strengthened my skills in API development, testing, and automated deployment.

---

## Docker Hub Repository

Docker Hub- https://hub.docker.com/repository/docker/yugpatil/601_module12/general

---

## Screenshots

Added all screenshots in the root folder named screenshots
https://github.com/yugpatill/module12_is601/tree/main/Screenshots

---
## 🧪 Running Tests Locally

### 1. Create and activate a virtual environment
```bash
python3 -m venv venv
source venv/bin/activate

2. Install dependencies

pip install -r requirements.txt

3. Start Postgres using Docker

docker compose up -d

4. Run the integration tests

pytest

---

## API Endpoints Documentation

This document describes all authentication and calculation endpoints implemented in the FastAPI application for Module 12.

---

## Authentication Endpoints

| Endpoint        | Method | Description                         |
|----------------|--------|-------------------------------------|
| `/auth/register` | POST   | Create a new user account.          |
| `/auth/login`    | POST   | Authenticate and receive a JWT token.|

---

## 8.2 Calculations Endpoints (Require Auth)

| Endpoint               | Method | Description                                                                 |
|-----------------------|--------|-----------------------------------------------------------------------------|
| `/calculations`        | POST   | Create a new calculation (e.g., `{ "type": "addition", "inputs": [1, 2] }`). |
| `/calculations`        | GET    | List all calculations created by the current user.                          |
| `/calculations/{id}`   | GET    | Retrieve a calculation by its UUID.                                        |
| `/calculations/{id}`   | PUT    | Update calculation inputs and recompute the result.                         |
| `/calculations/{id}`   | DELETE | Remove a calculation.                                                      |

---
