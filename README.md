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
| [**Notification Service**](https://github.com/Soloda1/pinstack-notification-service) | ✅ Ready    | Event notifications via Kafka + Redis.                                                            |
| [**Feed Service**](#)                      | 🔜 Planned  | Aggregates feed from followed users.                                                              |
| [**Activity Service**](#)                  | 🔜 Planned  | Handles likes, reposts, comments, views — all types of user activity in one service.              |
| [**e2e-tests Service**](#)                 | 🔜 Planned  | Automated end-to-end tests: runs requests against all public API endpoints defined in Swagger.     |
| [**Logging/Monitoring Service**](#)        | 🔜 Planned  | Centralized logging and monitoring (Prometheus, Grafana, Kibana, etc.).                           |

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

> 🇷🇺 [читать на русском](README.ru.md)

> 🚧 This project is in active development. Repositories, services, and structure are constantly evolving.
