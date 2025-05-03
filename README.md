# Pinstack — микросервисная социальная сеть

Микросервисный pet-проект, вдохновлённый Pinterest. Каждый сервис — в отдельном репозитории, взаимодействие — через gRPC и Kafka.

## 📦 Репозитории проекта

| Название                      | Назначение                                  | Ссылка                                                                 |
|------------------------------|---------------------------------------------|------------------------------------------------------------------------|
| **User Service**             | Работа с пользователями                     | [pinstack-user-service](https://github.com/Soloda1/pinstack-user-service) |
| **Proto Definitions**        | Общие `.proto`-файлы для gRPC               | [pinstack-proto-definitions](https://github.com/Soloda1/pinstack-proto-definitions) |
| **Infrastructure Deployments** | Docker Compose, Kafka, PostgreSQL и прочее | [pinstack-infra-deployments](https://github.com/Soloda1/pinstack-infra-deployments) |

## 🛠️ Стек технологий

- Go (chi, gRPC, protobuf, pgx)
- PostgreSQL
- Redis
- Kafka
- Docker, Docker Compose
- make, slog, validator

## ⚙️ Архитектура

- **Микросервисный подход** — каждый сервис отвечает за свою зону ответственности.
- **Связь сервисов** — gRPC и Kafka.
- **Контракты** — отдельный репозиторий с `.proto`-файлами.
- **Инфраструктура** — деплой и локальный запуск через `pinstack-infra-deployments`.

## 🔧 В разработке

- [ ] Авторизация (отдельный Auth Service)
- [ ] Notification Service
- [ ] Swagger/OpenAPI документация
- [ ] CI/CD пайплайны

---

> Репозиторий `pinstack` пока служит индексом и сводкой всех микросервисов проекта. Описание и документация будут дорабатываться по мере развития проекта.
