# Pinstack — микросервисная социальная сеть 🖼️

Pinstack — это pet-проект социальной сети в стиле Pinterest, реализованной с использованием микросервисной архитектуры. В проекте используются gRPC, Kafka, PostgreSQL, Redis, Docker и Go.

## 🧩 Архитектура микросервисов

| Сервис | Статус | Описание |
|--------|--------|----------|
| **User Service** | ✅ Готов | Управление пользователями: создание, получение, обновление. |
| **Post Service** | 🚧 В разработке | Создание и отображение постов (связь с тегами и пользователями). |
| **Tag Service** | 🚧 В разработке | Управление и выдача тегов (автокомплит, фильтрация). |
| **Relation Service** | 🚧 В разработке | Подписки и фолловеры между пользователями. |
| **Notification Service** | 🚧 В разработке | Отправка событийных уведомлений (Kafka + Redis). |
| **Proto Definitions** | ✅ Готов | Общие `.proto` файлы для gRPC контрактов. |
| **Infra Deployments** | ✅ Готов | Docker Compose, Kafka, PostgreSQL, Redis, etc. |

## ⚙️ Потенциальные сервисы (позже)

| Сервис | Описание |
|--------|----------|
| **Auth Service** | Авторизация и аутентификация пользователей, JWT, refresh-токены. |
| **Feed Service** | Сборка ленты из постов подписанных пользователей. |
| **Search Service** | Полнотекстовый поиск по тегам, постам и пользователям. |

---

## 🗂 Репозитории проекта

- [`pinstack-user-service`](https://github.com/Soloda1/pinstack-user-service) — сервис пользователей.
- [`pinstack-proto-definitions`](https://github.com/Soloda1/pinstack-proto-definitions) — gRPC контракты.
- [`pinstack-infra-deployments`](https://github.com/Soloda1/pinstack-infra-deployments) — инфраструктура и деплой.

---

## 📌 Технологии

- Язык: **Go**
- API: **gRPC**
- Асинхронность: **Kafka**
- База данных: **PostgreSQL**
- Кэш: **Redis**
- CI/CD: **Docker Compose**
- Контракты: **protobuf**

---

> ✅ README будет дополняться по мере развития проекта.
