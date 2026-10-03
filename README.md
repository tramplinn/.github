<div align="center">

<img src="assets/logo.png" width="96" alt="Трамплин">

# Трамплин

### Знания становятся практикой

Учебная платформа: курсы с картой модулей, интерактивные тесты,
алгоритмические задачи с запуском кода и AI-тьютор рядом с материалом.

[![Спецификации](https://img.shields.io/badge/Спецификации-продукт_и_кейсы-2b7fff?style=for-the-badge)](https://gitlab.com/tramplin1/specs)
[![Архитектура](https://img.shields.io/badge/Архитектура-5_сервисов-16a34a?style=for-the-badge)](#под-капотом)

![Python](https://img.shields.io/badge/Python_3.14-3776AB?logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white)
![Vue](https://img.shields.io/badge/Vue_3-35495E?logo=vuedotjs&logoColor=4FC08D)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL_+_pgvector-4169E1?logo=postgresql&logoColor=white)
![RabbitMQ](https://img.shields.io/badge/RabbitMQ-FF6600?logo=rabbitmq&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?logo=redis&logoColor=white)
![Docker](https://img.shields.io/badge/Docker_Compose-2496ED?logo=docker&logoColor=white)
![Caddy](https://img.shields.io/badge/Caddy-1F88C0?logo=caddy&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?logo=grafana&logoColor=white)

</div>

---

## Зачем

Учебный процесс в колледже разбросан по файлам, чатам и разным сервисам: теория в одном месте,
практика в другом, а помощь — только на паре. **Трамплин** собирает путь от первого урока
до работающего кода в одно пространство — с прогрессом, практикой и AI-помощью по ходу.
Преподаватели создают и публикуют материалы там же. Бизнес-ценность и пользовательские
кейсы — в [спецификациях](https://gitlab.com/tramplin1/specs).

## Как это работает

| 🗺️ Учиться | 🧩 Проверять себя | 💻 Практиковаться | ✍️ Преподавать |
| :---: | :---: | :---: | :---: |
| Карта курса связывает модули и уроки в маршрут, прогресс возвращает туда, где остановился | Тесты с разными типами ответов и интерактивными заданиями, AI-тьютор по материалу урока | Условие, редактор и запуск кода на одном экране; решения выполняются в изолированном Piston | Редактор уроков с live-превью, публикация и AI-агенты, наполняющие курс через MCP |

<div align="center">
<a href="assets/screenshots/course-map.jpg"><img src="assets/screenshots/course-map.jpg" width="720" alt="Карта курса: модули, связи и прогресс обучения"></a><br>
<sub>Карта курса «Fullstack-разработка»: модули, связи и прогресс студента</sub>
</div>

<details>
<summary>📸 Ещё скриншоты: урок, тест, AI-тьютор, задачи, редактор, люди</summary>

<table>
<tr>
<td width="50%"><a href="assets/screenshots/lesson.jpg"><img src="assets/screenshots/lesson.jpg" alt="Урок"></a><br><sub>Урок с Markdown и подсветкой кода</sub></td>
<td width="50%"><a href="assets/screenshots/quiz-dnd.jpg"><img src="assets/screenshots/quiz-dnd.jpg" alt="Интерактивный тест"></a><br><sub>Интерактивный тест с перетаскиванием</sub></td>
</tr>
<tr>
<td><a href="assets/screenshots/tutor-chat.jpg"><img src="assets/screenshots/tutor-chat.jpg" alt="AI-тьютор"></a><br><sub>AI-тьютор по материалам урока</sub></td>
<td><a href="assets/screenshots/algorithm-solve.jpg"><img src="assets/screenshots/algorithm-solve.jpg" alt="Решение задачи"></a><br><sub>Алгоритмическая задача: код, запуск, отправка</sub></td>
</tr>
<tr>
<td><a href="assets/screenshots/lesson-editor.jpg"><img src="assets/screenshots/lesson-editor.jpg" alt="Редактор урока"></a><br><sub>Редактор урока с предпросмотром</sub></td>
<td><a href="assets/screenshots/people.jpg"><img src="assets/screenshots/people.jpg" alt="Люди"></a><br><sub>Профили пользователей платформы</sub></td>
</tr>
</table>

</details>

## В цифрах

<div align="center">

![5 сервисов](https://img.shields.io/badge/5-сервисов-2b7fff?style=for-the-badge)
![140+ эндпоинтов](https://img.shields.io/badge/140+-эндпоинтов_API-16a34a?style=for-the-badge)
![37 таблиц](https://img.shields.io/badge/37-таблиц_в_модели_данных-6366f1?style=for-the-badge)
![450+ тестов](https://img.shields.io/badge/450+-тестов-f59e0b?style=for-the-badge)
![16 MCP-инструментов](https://img.shields.io/badge/16-MCP--инструментов-db2777?style=for-the-badge)

</div>

Покрытие тестами backend и email-service — не ниже 90 %; integration-тесты проверяют каждый
эндпоинт на настоящем PostgreSQL. Интерфейс — на русском и английском.

## Под капотом

<table>
<tr><th colspan="2">🎓 Продукт</th></tr>
<tr>
<td width="48" align="center">🖥️</td>
<td><a href="https://gitlab.com/tramplin1/frontend"><b>frontend</b></a> — интерфейс студента, преподавателя и администратора: каталог, уроки, тесты, практика алгоритмов<br><sub>Vue 3 · TypeScript · Vite · Pinia · TanStack Query · CodeMirror</sub></td>
</tr>
<tr>
<td align="center">⚙️</td>
<td><a href="https://gitlab.com/tramplin1/backend"><b>backend</b></a> — API, авторизация, курсы, прогресс, рекомендации, AI-тьютор и ассистент; единственный владелец базы<br><sub>Python 3.14 · FastAPI · SQLAlchemy · Dishka · FastStream · pgvector</sub></td>
</tr>
<tr>
<td align="center">📨</td>
<td><a href="https://gitlab.com/tramplin1/email-service"><b>email-service</b></a> — доставка писем из очереди в SMTP с circuit breaker<br><sub>Python · FastStream · RabbitMQ · aiosmtplib</sub></td>
</tr>
<tr><th colspan="2">🤖 AI-агенты</th></tr>
<tr>
<td align="center">🔌</td>
<td><a href="https://gitlab.com/tramplin1/mcp-server"><b>mcp-server</b></a> — Codex, Claude Code и другие агенты наполняют курсы от имени преподавателя: план, валидация, diff, применение<br><sub>FastMCP · httpx · OAuth 2.1 + PKCE</sub></td>
</tr>
<tr><th colspan="2">🏗️ Платформа</th></tr>
<tr>
<td align="center">🏗️</td>
<td><a href="https://gitlab.com/tramplin1/infra"><b>infra</b></a> — stage/prod: HTTPS-прокси, брокер, изолированный запуск кода, логи и метрики<br><sub>Docker Compose · Caddy · RabbitMQ · Piston · Prometheus / Loki / Grafana / Alloy</sub></td>
</tr>
<tr><th colspan="2">📚 Знания</th></tr>
<tr>
<td align="center">📚</td>
<td><a href="https://gitlab.com/tramplin1/specs"><b>specs</b></a> — бизнес-ценность, продукты, пользовательские кейсы по ролям и спецификации изменений<br><sub>Markdown</sub></td>
</tr>
</table>

<div align="center">
<a href="assets/arch.png"><img src="assets/arch.png" width="720" alt="Схема архитектуры Трамплина"></a><br>
<sub>Backend — единственный владелец базы данных. Email-service берёт задания из RabbitMQ, MCP-сервер ходит в API backend, Piston живёт во внутренней сети без доступа к базе</sub>
</div>

## Команда

<table>
<tr>
<td align="center">
<a href="https://gitlab.com/semao0"><img src="assets/team/semao0.png" width="80" alt=""><br><b>Семён Белоусов</b></a><br>
<sub>Backend · Frontend · Инфраструктура</sub>
</td>
</tr>
</table>

<div align="center">
<sub>Трамплин · 2026</sub>
</div>
