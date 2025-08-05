# Pinstack — Microservice Social Network 🖼️

**Pinstack** is a microservice-based social network built with **Go**, focusing on clean architecture, modularity, scalability, and production-level patterns like gRPC, Kafka, Redis, and Docker.

---

## 🧩 Microservices Architecture

| Service                                   | Status      | Description                                                                                       |
|--------------------------------------------|-------------|---------------------------------------------------------------------------------------------------|
| [**User Service**](https://github.com/Soloda1/pinstack-user-service)            | ✅ Ready    | Manages users: CRUD, communicates via gRPC.                                                       |
| [**Auth Service**](https://github.com/Soloda1/pinstack-auth-service)            | ✅ Ready    | Authentication and authorization, JWT and refresh tokens.                                         |
| [**Post Service**](https://github.com/Soloda1/pinstack-post-service)            | ✅ Ready    | Post management, relation to tags and users.                                                      |
| [**Relation Service**](https://github.com/Soloda1/pinstack-relation-service)    | ✅ Ready    | Following/follower relationships.                                                                 |
| [**Notification Service**](https://github.com/Soloda1/pinstack-notification-service) | ✅ Ready    | Event notifications via Kafka.                                                            |
| [**Chat Service**](#)                      | 🔜 Planned  | Implements real-time communication via WebSocket.                                                              |
| [**Activity Service**](#)                  | 🔜 Planned  | Handles likes, reposts, comments, views — all types of user activity in one service.              |
| [**System-tests Service**](https://github.com/Soloda1/pinstack-system-tests)                | ✅ Ready  | Automated tests: runs requests against all public API endpoints defined in Swagger.     |
| [**Logging/Monitoring Service**](https://github.com/Soloda1/pinstack-monitoring-service)        | ✅ Ready   | Centralized logging and monitoring (Prometheus, ELK, etc.).                           |

---

## 🔌 Infrastructure & Interfaces

| Component                 | Status      | Description                                                                                       |
|---------------------------|-------------|---------------------------------------------------------------------------------------------------|
| [**API Gateway**](https://github.com/Soloda1/pinstack-api-gateway)           | ✅ Ready (base) | Unified entry point: validation, routing HTTP → gRPC. Will evolve.                           |
| [**Proto Definitions**](https://github.com/Soloda1/pinstack-proto-definitions)     | ✅ Ready (base) | Shared `.proto` contracts, used across services.                                               |
| [**Infra Deployments**](https://github.com/Soloda1/pinstack-infra-deployments)     | ✅ Ready (base) | Docker Compose: PostgreSQL, Redis, Kafka, etc. Extensible setup.                               |

---

## 🗂 Project Repositories

- [`pinstack-post-service`](https://github.com/Soloda1/pinstack-post-service)
- [`pinstack-user-service`](https://github.com/Soloda1/pinstack-user-service)
- [`pinstack-auth-service`](https://github.com/Soloda1/pinstack-auth-service)
- [`pinstack-proto-definitions`](https://github.com/Soloda1/pinstack-proto-definitions)
- [`pinstack-infra-deployments`](https://github.com/Soloda1/pinstack-infra-deployments)
- [`pinstack-api-gateway`](https://github.com/Soloda1/pinstack-api-gateway)
- [`pinstack-relation-service`](https://github.com/Soloda1/pinstack-relation-service)
- [`pinstack-notification-service`](https://github.com/Soloda1/pinstack-notification-service)
- [`pinstack-monitoring-service`](https://github.com/Soloda1/pinstack-monitoring-service)
- [`pinstack-system-tests`](https://github.com/Soloda1/pinstack-system-tests)

---

## ⚙️ Technologies

- **Go** — core language for services
- **gRPC / Protobuf** — service-to-service communication
- **PostgreSQL** — main database
- **Redis** — caching & sessions
- **Kafka** — event-driven architecture
- **Docker / Compose** — containerized deployment
- **Swagger** — documentation

---

## 🚀 CI/CD Pipeline

The entire **Pinstack** project uses a modern CI/CD approach with **GitHub Actions** for automated testing and **Makefile** for local development.

### Test Automation 🔄

**Each microservice** has its own CI pipeline that includes:

- **Unit Tests** — unit tests with code coverage
- **Integration Tests** — integration tests with necessary infrastructure
- **Auto Cleanup** — automatic Docker resource cleanup
- **Linting & Formatting** — code quality checks

### Makefile Commands for Development 📋

Each service includes convenient development commands:

```bash
# Code checks and tests
make fmt                    # Code formatting
make lint                   # Code linting
make test-unit              # Unit tests
make test-integration       # Integration tests
make ci-local              # Full CI process locally

# Infrastructure management
make start-infrastructure   # Start necessary Docker containers
make stop-infrastructure    # Stop containers
make clean                  # Full cleanup
```

### CI/CD System Features 🔧

- **Isolated infrastructure**: each service is tested only with necessary dependencies
- **Full integration in Gateway**: API Gateway tests the entire system as a whole
- **Automatic cleanup**: all Docker resources are cleaned up automatically
- **Fast development**: local commands for rapid testing
- **Code quality**: automatic formatting checks and linting

---

> 🇷🇺 [читать на русском](README.ru.md)

> 🚧 This project is in active development. Repositories, services, and structure are constantly evolving.
