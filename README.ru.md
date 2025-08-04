# Pinstack — Микросервисная социальная сеть 🖼️

**Pinstack** — это социальная сеть на основе микросервисной архитектуры, написанная на **Go** с акцентом на чистую архитектуру, модульность, масштабируемость и современные подходы (gRPC, Kafka, Redis, Docker).

---

## 🧩 Архитектура микросервисов

| Сервис                                         | Статус      | Описание                                                                                                  |
|------------------------------------------------|-------------|-----------------------------------------------------------------------------------------------------------|
| [**User Service**](https://github.com/Soloda1/pinstack-user-service)            | ✅ Готов    | Управление пользователями: CRUD, взаимодействие через gRPC.                                               |
| [**Auth Service**](https://github.com/Soloda1/pinstack-auth-service)            | ✅ Готов    | Аутентификация и авторизация, JWT и refresh токены.                                                       |
| [**Post Service**](https://github.com/Soloda1/pinstack-post-service)            | ✅ Готов    | Управление постами, связь с тегами и пользователями.                                                      |
| [**Relation Service**](https://github.com/Soloda1/pinstack-relation-service)    | ✅ Готов    | Подписки и подписчики.                                                                                    |
| [**Notification Service**](https://github.com/Soloda1/pinstack-notification-service) | ✅ Готов    | Уведомления о событиях через Kafka.                                                               |
| [**Feed Service**](#)                         | 🔜 В планах | Агрегация ленты из подписок.                                                                              |
| [**Activity Service**](#)                     | 🔜 В планах | Лайки, репосты, комментарии, просмотры — вся пользовательская активность в одном сервисе.                 |
| [**System-tests Service**](https://github.com/Soloda1/pinstack-system-tests)         | ✅ Готов | Автоматизированные тесты: выполнение всех публичных API-запросов, определённых в Swagger.             |
| [**Logging/Monitoring Service**](https://github.com/Soloda1/pinstack-monitoring-service)          | ✅ Готов | Централизованные логи и мониторинг (Prometheus, ELK и др.).                                   |

---

## 🔌 Инфраструктура и интерфейсы

| Компонент                                     | Статус      | Описание                                                                                                  |
|-----------------------------------------------|-------------|-----------------------------------------------------------------------------------------------------------|
| [**API Gateway**](https://github.com/Soloda1/pinstack-api-gateway)              | ✅ Готов (базовый) | Единая точка входа: валидация, роутинг HTTP → gRPC. Будет расширяться.                             |
| [**Proto Definitions**](https://github.com/Soloda1/pinstack-proto-definitions)  | ✅ Готов (базовый) | Общие `.proto` контракты, используемые всеми сервисами.                                               |
| [**Infra Deployments**](https://github.com/Soloda1/pinstack-infra-deployments)  | ✅ Готов (базовый) | Docker Compose: PostgreSQL, Redis, Kafka и др. Гибкая инфраструктура.                                 |

---

## 🗂 Репозитории проекта

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

## ⚙️ Технологии

- **Go** — основной язык микросервисов
- **gRPC / Protobuf** — коммуникация между сервисами
- **PostgreSQL** — основная база данных
- **Redis** — кеширование и сессии
- **Kafka** — событийная архитектура
- **Docker / Compose** — контейнеризация и деплой
- **Swagger** — документация

---

## 🚀 CI/CD Pipeline

Весь проект **Pinstack** использует современный CI/CD подход с **GitHub Actions** для автоматического тестирования и **Makefile** для локальной разработки.

### Автоматизация тестирования 🔄

**Каждый микросервис** имеет свой собственный CI pipeline, который включает:

- **Unit Tests** — юнит-тесты с покрытием кода
- **Integration Tests** — интеграционные тесты с необходимой инфраструктурой
- **Auto Cleanup** — автоматическая очистка Docker ресурсов
- **Linting & Formatting** — проверка качества кода

### Makefile команды для разработки 📋

Каждый сервис включает удобные команды для разработки:

```bash
# Проверка кода и тесты
make fmt                    # Форматирование кода
make lint                   # Проверка кода
make test-unit              # Юнит-тесты
make test-integration       # Интеграционные тесты
make ci-local              # Полный CI процесс локально

# Управление инфраструктурой
make start-infrastructure   # Запуск необходимых Docker контейнеров
make stop-infrastructure    # Остановка контейнеров
make clean                  # Полная очистка
```

### Особенности CI/CD системы 🔧

- **Изолированная инфраструктура**: каждый сервис тестируется только с необходимыми зависимостями
- **Полная интеграция в Gateway**: API Gateway тестирует всю систему целиком
- **Автоматическая очистка**: все Docker ресурсы очищаются автоматически
- **Быстрая разработка**: локальные команды для быстрого тестирования
- **Качество кода**: автоматическая проверка форматирования и линтинг

---

> 🇬🇧 [Read in English](README.md)

> 🚧 Проект находится в активной разработке. Репозитории, сервисы и структура могут меняться.
