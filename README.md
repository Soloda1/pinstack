# Pinstack — Microservice Social Network 🖼️

**Pinstack** is a microservice-based social network built with **Go**, focusing on clean architecture, modularity, scalability, and production-level patterns like gRPC, Kafka, Redis, and Docker.

---

## 🧩 Microservices Architecture

| Service                 | Status         | Description |
|-------------------------|----------------|-------------|
| **User Service**        | ✅ Ready        | Manages users: CRUD, communicates via gRPC. |
| **Auth Service**        | ✅ Ready        | Authentication and authorization, JWT and refresh tokens. |
| **Post Service**        | ✅ Ready        | Post management, relation to tags and users. |
| **Relation Service**    | 🚧 In progress  | Following/follower relationships. |
| **Notification Service**| 🚧 In progress  | Event notifications via Kafka + Redis. |
| **Feed Service**        | 🔜 Planned      | Aggregates feed from followed users. |
| **Search Service**      | 🔜 Planned      | Full-text search across users, tags, posts. |

---

## 🔌 Infrastructure & Interfaces

| Component               | Status         | Description |
|--------------------------|----------------|-------------|
| **API Gateway**          | ✅ Ready (base) | Unified entry point: validation, routing HTTP → gRPC. Will evolve. |
| **Proto Definitions**    | ✅ Ready (base) | Shared `.proto` contracts, used across services. |
| **Infra Deployments**    | ✅ Ready (base) | Docker Compose: PostgreSQL, Redis, Kafka, etc. Extensible setup. |

---

## 🗂 Project Repositories

- [`pinstack-post-service`](https://github.com/Soloda1/pinstack-post-service)
- [`pinstack-user-service`](https://github.com/Soloda1/pinstack-user-service)
- [`pinstack-auth-service`](https://github.com/Soloda1/pinstack-auth-service)
- [`pinstack-proto-definitions`](https://github.com/Soloda1/pinstack-proto-definitions)
- [`pinstack-infra-deployments`](https://github.com/Soloda1/pinstack-infra-deployments)
- [`pinstack-api-gateway`](https://github.com/Soloda1/pinstack-api-gateway)
- [`pinstack-relation-service`](https://github.com/Soloda1/pinstack-relation-service)

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

> 🇷🇺 [Читать на русском](README.ru.md)

> 🚧 This project is in active development. Repositories, services, and structure are constantly evolving.
