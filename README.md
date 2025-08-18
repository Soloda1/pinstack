# Pinstack — Microservice Social Network 🖼️

**Pinstack** is a production-ready microservice-based social network built with **Go**, featuring **hexagonal architecture**, comprehensive **monitoring**, **event-driven design**, and modern **CI/CD** practices.

---

## 🧩 Core Services Architecture

| Service                                   | Status      | Description                                                                                       |
|--------------------------------------------|-------------|---------------------------------------------------------------------------------------------------|
| [**User Service**](https://github.com/Soloda1/pinstack-user-service)            | ✅ Production Ready    | User management with CRUD operations, gRPC communication, and Prometheus metrics.                                                       |
| [**Auth Service**](https://github.com/Soloda1/pinstack-auth-service)            | ✅ Production Ready    | JWT authentication/authorization with refresh tokens, session management, and Redis integration.                                         |
| [**Post Service**](https://github.com/Soloda1/pinstack-post-service)            | ✅ Production Ready    | Post management with Redis caching, media handling, and optimized performance.                                                      |
| [**Relation Service**](https://github.com/Soloda1/pinstack-relation-service)    | ✅ Production Ready    | Follow/unfollow relationships with Kafka event publishing and Redis caching.                                                                 |
| [**Notification Service**](https://github.com/Soloda1/pinstack-notification-service) | ✅ Production Ready    | Event-driven notifications via Kafka consumer/producer with multiple notification types.                                                            |

---

## 🔌 Infrastructure & Platform Services

| Component                 | Status      | Description                                                                                       |
|---------------------------|-------------|---------------------------------------------------------------------------------------------------|
| [**API Gateway**](https://github.com/Soloda1/pinstack-api-gateway)           | ✅ Production Ready | HTTP→gRPC routing, JWT validation, comprehensive Prometheus metrics, rate limiting support.                           |
| [**Proto Definitions**](https://github.com/Soloda1/pinstack-proto-definitions)     | ✅ Ready | Centralized gRPC contracts with automated generation and version management.                                               |
| [**Infra Deployments**](https://github.com/Soloda1/pinstack-infra-deployments)     | ✅ Ready | Docker Compose orchestration for PostgreSQL, Redis, Kafka infrastructure.                               |
| [**System Tests**](https://github.com/Soloda1/pinstack-system-tests)                | ✅ Production Ready  | End-to-end integration testing with automated CI/CD integration.     |
| [**Monitoring Service**](https://github.com/Soloda1/pinstack-monitoring-service)        | ✅ Production Ready   | Complete observability stack: Prometheus, Grafana, Loki, ELK with custom dashboards.                           |

---

## 🏗️ Architecture Principles

### Hexagonal Architecture (Clean Architecture)
All services follow **hexagonal architecture** patterns with clear separation of concerns:

- **Domain Layer**: Core business logic and models
- **Application Layer**: Use cases and service orchestration  
- **Infrastructure Layer**: External dependencies (databases, APIs, messaging)
- **Ports & Adapters**: Interface-driven design for easy testing and flexibility

### Event-Driven Design
- **Kafka Integration**: Asynchronous event processing for scalability
- **Event Sourcing**: State changes broadcast as events
- **Loose Coupling**: Services communicate via events and gRPC

### Comprehensive Observability
- **Prometheus Metrics**: Request counts, latency, error rates, business metrics
- **Structured Logging**: JSON logs with correlation IDs via Loki
- **Distributed Tracing**: Request flow tracking across services
- **Health Checks**: Service availability and dependency monitoring

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

## ⚙️ Technology Stack

### Core Technologies
- **Go** — primary development language with clean architecture patterns
- **gRPC / Protobuf** — high-performance service-to-service communication
- **PostgreSQL** — ACID-compliant primary database with migrations
- **Redis** — caching, session storage, and high-performance data structures
- **Kafka** — event streaming and asynchronous message processing
- **Docker / Compose** — containerized deployment and development environments

### Monitoring & Observability
- **Prometheus** — metrics collection and alerting
- **Grafana** — metrics visualization and dashboards
- **Loki** — centralized log aggregation and querying
- **ELK Stack** — alternative logging with Elasticsearch, Logstash, Kibana
- **Structured Logging** — JSON logs with correlation tracking

### Development & CI/CD
- **GitHub Actions** — automated testing and deployment pipelines
- **Makefile** — standardized development commands across services
- **golangci-lint** — comprehensive code quality and style checking
- **Docker Multi-stage** — optimized container builds
- **Swagger/OpenAPI** — API documentation and validation

---

## 🚀 Production-Ready Features

### Security
- **JWT Authentication** — stateless token-based authentication
- **Refresh Token Rotation** — secure session management
- **Input Validation** — comprehensive request validation
- **Rate Limiting** — API protection and abuse prevention

### Performance
- **Redis Caching** — intelligent caching strategies (cache-aside, write-through)
- **Connection Pooling** — optimized database connections
- **gRPC Streaming** — efficient real-time communication
- **Prometheus Metrics** — performance monitoring and alerting

### Reliability
- **Circuit Breaker Pattern** — fault tolerance and resilience
- **Health Checks** — service availability monitoring
- **Graceful Shutdown** — proper resource cleanup
- **Database Migrations** — versioned schema management
- **Retry Mechanisms** — transient failure handling

### Scalability
- **Microservice Architecture** — independent scaling and deployment
- **Event-Driven Design** — asynchronous processing capabilities
- **Horizontal Scaling** — stateless service design
- **Load Balancing Ready** — multiple instance support

---

## � CI/CD Pipeline

The entire **Pinstack** ecosystem uses modern **GitHub Actions** CI/CD with standardized **Makefile** commands for consistent development experience across all services.

### Automated Testing Pipeline 🔄

**Each microservice** includes comprehensive CI pipeline:

1. **Code Quality Checks**
   - `gofmt` formatting validation
   - `go vet` static analysis
   - `golangci-lint` comprehensive linting
   
2. **Unit Testing**
   - Comprehensive test coverage reporting
   - Mock-based testing with dependency injection
   - Fast feedback loop for developers

3. **Integration Testing**
   - Full Docker infrastructure setup
   - Database migrations and seeding
   - Real service-to-service communication testing
   - Kafka event processing validation

4. **Infrastructure Management**
   - Automatic Docker resource cleanup
   - Network isolation for parallel testing
   - Health check validation

### Standardized Development Commands 📋

**Every service** provides consistent Makefile interface:

```bash
# Code Quality & Testing
make fmt                    # Go formatting (gofmt)
make lint                   # Static analysis (go vet + golangci-lint)
make test-unit              # Unit tests with coverage reporting
make test-integration       # Integration tests with full infrastructure
make test-all               # Complete test suite (fmt + lint + unit + integration)
make ci-local              # Full CI process locally (GitHub Actions simulation)

# Infrastructure Management
make setup-system-tests     # Clone/update test infrastructure repositories
make setup-monitoring       # Clone/update monitoring stack
make start-infrastructure   # Launch complete Docker test environment
make stop-infrastructure    # Stop all containers
make clean-infrastructure   # Complete cleanup (containers + volumes + images)

# Development Environments
make start-dev-full         # Full development stack (services + monitoring + ELK)
make start-dev-light        # Lightweight stack (services + Prometheus only)
make stop-dev-full          # Stop development environment
make clean-dev-full         # Complete development environment cleanup

# Monitoring & Observability
make start-monitoring       # Prometheus + Grafana + Loki + ELK stack
make start-prometheus-stack # Prometheus + Grafana + Loki only
make start-elk-stack        # Elasticsearch + Logstash + Kibana only
make check-monitoring-health # Validate all monitoring services
make logs-[service]         # Service-specific log viewing

# Database & Cache Management
make migrate-up             # Apply database migrations
make migrate-down           # Rollback migrations
make redis-cli              # Redis CLI access
make redis-flush            # Clear Redis data (with confirmation)
```

### Service-Specific Features 🔧

#### API Gateway
- **Full System Integration Testing**: End-to-end tests covering all service interactions
- **Comprehensive Metrics**: HTTP requests, gRPC calls, authentication, proxy metrics
- **Rate Limiting & Circuit Breaker**: Production-ready resilience patterns

#### Individual Services
- **Isolated Testing**: Each service tests only its required dependencies
- **Event Testing**: Kafka consumer/producer validation
- **Cache Testing**: Redis integration and invalidation testing
- **Database Testing**: Migration validation and data integrity

### Monitoring Integration 📊

**Production-ready observability** available for all services:

- **Prometheus**: http://localhost:9090 - metrics and alerting
- **Grafana**: http://localhost:3000 (admin/admin) - dashboards and visualization  
- **Loki**: http://localhost:3100 - centralized log aggregation
- **Kibana**: http://localhost:5601 - ELK stack log analysis
- **PgAdmin**: http://localhost:5050 (admin@admin.com/admin) - database management
- **Kafka UI**: http://localhost:9091 - event stream management

### Quality Assurance Features 🎯

- **Dependency Isolation**: Services start only required infrastructure
- **Parallel Testing**: Network isolation enables concurrent test execution
- **Automatic Cleanup**: Zero manual intervention for resource management
- **Fast Development Cycle**: Local commands mirror CI/CD pipeline exactly
- **Comprehensive Coverage**: Unit, integration, and end-to-end testing

---

## 🚀 Quick Start

### Prerequisites
- **Docker & Docker Compose** — for containerized services
- **Go 1.21+** — for local development
- **Git** — for repository management

### Start Full Development Environment

```bash
# Clone any service repository (they all have similar structure)
git clone https://github.com/Soloda1/pinstack-api-gateway.git
cd pinstack-api-gateway

# Start complete development environment with monitoring
make start-dev-full

# Access services:
# - API Gateway: http://localhost:8080
# - User Service: http://localhost:8081  
# - Auth Service: http://localhost:8082
# - Post Service: http://localhost:8083
# - Notification Service: http://localhost:8084
# - Relation Service: http://localhost:8085
# 
# Monitoring:
# - Prometheus: http://localhost:9090
# - Grafana: http://localhost:3000 (admin/admin)
# - Kibana: http://localhost:5601
# - PgAdmin: http://localhost:5050 (admin@admin.com/admin)
```

### Run Integration Tests

```bash
# Run complete test suite
make test-all

# Run only integration tests with full infrastructure
make test-integration

# Quick test without rebuilding containers
make quick-test
```

### Development Workflow

```bash
# Format and lint code
make fmt lint

# Run unit tests
make test-unit

# Start monitoring only
make start-prometheus-stack

# View service logs
make logs-[service-name]

# Clean everything
make clean-dev-full
```

---

## 📈 Current Metrics & Monitoring

<img width="1594" height="827" alt="Screenshot_20250818_184135" src="https://github.com/user-attachments/assets/e46c532b-bcb2-4b45-9236-2e9781da72a0" />

All services collect comprehensive metrics:

### API Gateway Metrics
- **HTTP Requests**: `pinstack_http_requests_total`, `pinstack_http_request_duration_seconds`
- **gRPC Calls**: `pinstack_grpc_client_requests_total`, `pinstack_grpc_client_request_duration_seconds`
- **Authentication**: `pinstack_authentication_total`, `pinstack_authorization_total`
- **Proxy Metrics**: `pinstack_proxy_requests_total`, `pinstack_proxy_errors_total`

### Service-Specific Metrics
- **Database Operations**: Connection pool usage, query duration, transaction metrics
- **Cache Performance**: Hit/miss ratios, operation latency (Redis)
- **Event Processing**: Kafka consumer lag, message processing rates
- **Business Metrics**: User registrations, post creation rates, relationship changes

### System Metrics
- **Resource Usage**: CPU, memory, disk I/O per service
- **Network**: Inter-service communication latency
- **Health Checks**: Service availability and dependency status

---

## 🔧 Architecture Decisions

### Why Hexagonal Architecture?
- **Testability**: Easy unit testing with mocked dependencies
- **Flexibility**: Swap implementations without changing business logic
- **Maintainability**: Clear separation of concerns
- **Scalability**: Independent service evolution

### Why Event-Driven Design?
- **Loose Coupling**: Services don't need direct knowledge of each other
- **Scalability**: Asynchronous processing handles load spikes
- **Reliability**: Event replay and processing guarantees
- **Extensibility**: New services can subscribe to existing events

### Why gRPC?
- **Performance**: Binary protocol with HTTP/2 multiplexing
- **Type Safety**: Strongly typed contracts with Protobuf
- **Language Agnostic**: Easy polyglot service development
- **Streaming**: Bidirectional streaming for real-time features

---

> 🇷🇺 [читать на русском](README.ru.md)

> 🚧 **Production Ready**: All core services are battle-tested with comprehensive monitoring, testing, and CI/CD pipelines. Ready for production deployment with Docker/Kubernetes.
