# Pinstack — микросервисная социальная сеть 🖼️

**Pinstack** — это pet-проект социальной сети, реализованной на **Go** с использованием **микросервисной архитектуры**. Основной упор — на чистую структуру, модульность, масштабируемость и практику продвинутых паттернов (gRPC, Kafka, Redis, Docker и др.).

---

## 🧩 Архитектура микросервисов

| Сервис                | Статус        | Описание |
|------------------------|----------------|----------|
| **User Service**       | ✅ Готов        | Управление пользователями: CRUD, взаимодействие через gRPC. |
| **Auth Service**       | ✅ Готов | Авторизация и аутентификация, JWT, refresh-токены, работа через gRPC. |
| **Post Service**       | ✅ Готов | Работа с постами, привязка к тегам и пользователям. |
| **Relation Service**   | 🚧 В разработке | Подписки и фолловеры между пользователями. |
| **Notification Service** | 🚧 В разработке | Отправка событийных уведомлений через Kafka и Redis. |
| **Feed Service**       | 🔜 Запланировано | Генерация ленты из постов подписок. |
| **Search Service**     | 🔜 Запланировано | Полнотекстовый поиск по постам, тегам, юзерам. |

---

## 🔌 Инфраструктура и интерфейсы

| Компонент                | Статус        | Описание |
|---------------------------|----------------|----------|
| **API Gateway**           | ✅ Готов (базово) | Общая точка входа, валидация, маршрутизация HTTP → gRPC. Расширяется с появлением новых сервисов. |
| **Proto Definitions**     | ✅ Готов (базово) | Общие `.proto` контракты, используется всеми сервисами. Расширяется при добавлении новых интерфейсов. |
| **Infra Deployments**     | ✅ Готов (базово) | Docker Compose, PostgreSQL, Redis, Kafka и другие зависимости. Постепенно расширяется. |

---

## 🗂 Репозитории проекта

- [`pinstack-post-service`](https://github.com/Soloda1/pinstack-post-service) — сервис постов.
- [`pinstack-user-service`](https://github.com/Soloda1/pinstack-user-service) — сервис пользователей.
- [`pinstack-auth-service`](https://github.com/Soloda1/pinstack-auth-service) — сервис авторизации и аутентификации.
- [`pinstack-proto-definitions`](https://github.com/Soloda1/pinstack-proto-definitions) — gRPC контракты.
- [`pinstack-infra-deployments`](https://github.com/Soloda1/pinstack-infra-deployments) — инфраструктура.
- [`pinstack-api-gateway`](https://github.com/Soloda1/pinstack-api-gateway) — точка входа, проксирование запросов.
- [`pinstack-relation-service`](https://github.com/Soloda1/pinstack-relation-service) - сервис подписок.

---

## ⚙️ Технологии

- **Go** — язык разработки микросервисов
- **gRPC / Protobuf** — коммуникация между сервисами
- **PostgreSQL** — основная БД
- **Redis** — кэш и сессии
- **Kafka** — событийная архитектура
- **Docker / Docker Compose** — контейнеризация
- **Swagger** — документация

---

🇺🇸 [Read in English](README.md)
> ⚠️ Проект в активной разработке. Репозитории будут дополняться, архитектура — уточняться, а сервисы — расширяться.

