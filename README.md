# Tramplin

Tramplin — учебная платформа колледжа ННГУ: курсы, уроки, тесты, практика
алгоритмических задач с реальным выполнением кода, рекомендации, AI-ассистент
для студентов и AI-инструменты для преподавателей-авторов курсов.

Проект выполнен как курсовая работа и построен как набор независимых
сервисов, каждый — отдельный git-репозиторий со своим CI/CD, тестами и
README:

```text
tramplin/
  backend/         FastAPI API: домен, авторизация, бизнес-логика
  frontend/        Vue 3 SPA: интерфейс студента, преподавателя и админа
  email-service/   independent-воркер доставки писем (очередь → SMTP)
  mcp-server/      MCP-сервер для наполнения курсов AI-агентами
  infra/           общая инфраструктура: reverse proxy, очереди, мониторинг
```

## Что умеет платформа

- **Каталог курсов**: треки, курсы, модули, уроки с Markdown/подсветкой кода.
- **Тесты**: вопросы с разными типами ответов, попытки, прогресс по курсу.
- **Практика по алгоритмам**: банк задач, тест-кейсы, запуск и проверка
  решений на нескольких языках в изолированном окружении (Piston), очередь
  заданий на RabbitMQ.
- **Рекомендации**: подбор курсов на основе прогресса и интересов студента,
  с векторными эмбеддингами (pgvector).
- **AI-тьютор для студентов** и **AI-ассистент для преподавателей**
  поверх LLM.
- **Authoring и админка**: создание и редактирование курсов, публикация,
  каскадные обновления, управление пользователями, новости.
- **MCP-сервер**: агент (Codex, Claude Code и т.д.) может через OAuth войти
  под преподавателем и сам наполнить курс — прочитать, провалидировать,
  показать diff и применить план, не заходя напрямую в базу.
- **Аутентификация**: email-код, OAuth через GitHub и Яндекс, JWT-сессии.
- **Доставка писем** — отдельным сервисом, с circuit breaker и без знания
  о шаблонах писем (их готовит backend).

## Скриншоты

| | |
| --- | --- |
| ![Карта курса](assets/screenshots/course-map.jpg) Карта курса — иерархия модулей и уроков | ![Редактирование урока](assets/screenshots/lesson-editor.jpg) Редактирование урока — Markdown с live-превью |
| ![Урок](assets/screenshots/lesson.jpg) Прохождение урока студентом | ![Тест с drag-and-drop](assets/screenshots/quiz-dnd.jpg) Тест с интерактивным вопросом (drag-and-drop) |
| ![Решение алгозадачи](assets/screenshots/algorithm-solve.jpg) Решение алгоритмической задачи в редакторе кода | ![AI-тьютор](assets/screenshots/tutor-chat.jpg) Чат с AI-тьютором по уроку |
| ![Люди](assets/screenshots/people.jpg) Профили пользователей платформы | |

## Архитектура

![Архитектура Tramplin](assets/arch.png)

Backend — единственный владелец базы данных. Email-service и MCP-сервер в
базу не ходят: email-service читает только очередь RabbitMQ, MCP-сервер
работает через публичный authoring API backend. Piston не видит базы и
доступен только внутри внутренней сети.

## Технологии

| Компонент      | Стек                                                                 |
| -------------- | --------------------------------------------------------------------- |
| backend        | Python 3.14, FastAPI, SQLAlchemy (async), PostgreSQL, pgvector, Redis, RabbitMQ (FastStream), Alembic, Dishka (DI), uv |
| frontend       | Vue 3, TypeScript, Vite, Pinia, Vue Router, Reka UI, CodeMirror, Vitest |
| email-service  | Python 3.14, FastStream, aiosmtplib                                   |
| mcp-server     | Python 3.14, FastMCP, httpx, OAuth 2.1 + PKCE                         |
| infra          | Docker Compose, Caddy, RabbitMQ, Piston, Prometheus, Loki, Grafana, Alloy |

Везде: Ruff, mypy (strict), pytest с покрытием ≥90% на backend и
email-service, ESLint/Prettier и Vitest на frontend. Каждый репозиторий имеет
собственный GitLab CI/CD пайплайн: линт, тесты, security-сканирование
(gitleaks, Semgrep, Trivy, Nuclei) и деплой immutable-образов на stage/prod.

## Быстрый запуск для демонстрации

Инструкции по локальному запуску и переменным окружения — в README каждого
сервиса:

- [`backend/README.md`](https://gitlab.com/tramplin1/backend) — API, база, миграции, seed-данные.
- [`frontend/README.md`](https://gitlab.com/tramplin1/frontend) — веб-интерфейс.
- [`mcp-server/README.md`](https://gitlab.com/tramplin1/mcp-server) — MCP-сервер для агентов.
- [`infra/README.md`](https://gitlab.com/tramplin1/infra) — общая инфраструктура (очереди,
  выполнение кода, мониторинг) для staging/production.

Минимальный локальный сценарий: поднять `backend` (`make up && make migrate
&& make seed && make run`), затем `frontend` (`pnpm install && pnpm dev`) —
этого достаточно, чтобы показать каталог курсов, прохождение уроков и тестов,
authoring и AI-ассистента. Полная инфраструктура (`infra`), email-service и
mcp-server нужны для очередей, реальной отправки писем, практики по
алгоритмам и подключения внешних AI-агентов.

## Продуктовая и архитектурная документация

- [PRD алгоритмической практики](https://gitlab.com/tramplin1/backend/-/blob/main/artifacts/prd/algorithmic-sessions.md)
- [PRD авторинга алгоритмических задач через MCP](https://gitlab.com/tramplin1/mcp-server/-/blob/main/docs/algorithm-authoring-prd.md)
