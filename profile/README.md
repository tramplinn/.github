<div align="center">

<img src="../assets/logo.png" width="96" alt="Tramplin">

# Tramplin

### Knowledge turns into practice

A learning platform with courses, quizzes, runnable coding problems,
and an AI tutor next to every lesson.

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

## Why

Classes still revolve around slides and copying lectures into notebooks. Code from
a lecture can't be run, mistakes only show up at the exam, and if a topic doesn't
click, you wait until the next class.

In **Tramplin**, the material is already online, so class time goes to discussion
and practice. Code runs in the browser, quizzes are graded instantly, and the AI
tutor is there 24/7. Teachers prepare lessons with an AI assistant and MCP agents,
and the college keeps its own platform and data. More in the
[business value](https://github.com/tramplinn/specs/blob/main/product/business-value.md) doc.

## How it works

| Learn | Check yourself | Practice | Teach |
| :---: | :---: | :---: | :---: |
| A course map shows the path; you pick up where you left off | Quizzes with different question types, and an AI tutor that knows the lesson | Problem, editor, and run button on one screen; code runs in a Piston sandbox | Lesson editor with live preview, plus AI agents that fill courses via MCP |

<div align="center">
<a href="../assets/screenshots/course-map.jpg"><img src="../assets/screenshots/course-map.jpg" width="720" alt="Course map"></a><br>
<sub>Course map of "Fullstack Development" with student progress</sub>
</div>

<details>
<summary>More screenshots: lesson, quiz, AI tutor, problems, editor, people</summary>

<table>
<tr>
<td width="50%"><a href="../assets/screenshots/lesson.jpg"><img src="../assets/screenshots/lesson.jpg" alt="Lesson"></a><br><sub>Lesson with Markdown and code highlighting</sub></td>
<td width="50%"><a href="../assets/screenshots/quiz-dnd.jpg"><img src="../assets/screenshots/quiz-dnd.jpg" alt="Interactive quiz"></a><br><sub>Interactive drag-and-drop quiz</sub></td>
</tr>
<tr>
<td><a href="../assets/screenshots/tutor-chat.jpg"><img src="../assets/screenshots/tutor-chat.jpg" alt="AI tutor"></a><br><sub>AI tutor</sub></td>
<td><a href="../assets/screenshots/algorithm-solve.jpg"><img src="../assets/screenshots/algorithm-solve.jpg" alt="Solving a problem"></a><br><sub>Algorithm problem: code, run, submit</sub></td>
</tr>
<tr>
<td><a href="../assets/screenshots/lesson-editor.jpg"><img src="../assets/screenshots/lesson-editor.jpg" alt="Lesson editor"></a><br><sub>Lesson editor with preview</sub></td>
<td><a href="../assets/screenshots/people.jpg"><img src="../assets/screenshots/people.jpg" alt="People"></a><br><sub>Platform user profiles</sub></td>
</tr>
</table>

</details>

## Under the hood

<table>
<tr><th>Product</th></tr>
<tr>
<td><a href="https://github.com/tramplinn/frontend"><b>frontend</b></a> — the web app for students, teachers, and admins<br><sub>Vue 3 · TypeScript · Vite · Pinia · TanStack Query · CodeMirror</sub></td>
</tr>
<tr>
<td><a href="https://github.com/tramplinn/backend"><b>backend</b></a> — API, auth, courses, progress, recommendations, AI tutor; the only service with database access<br><sub>Python 3.14 · FastAPI · SQLAlchemy · Dishka · FastStream · pgvector</sub></td>
</tr>
<tr>
<td><a href="https://github.com/tramplinn/email-service"><b>email-service</b></a> — sends emails from a queue over SMTP<br><sub>Python · FastStream · RabbitMQ · aiosmtplib</sub></td>
</tr>
<tr><th>AI agents</th></tr>
<tr>
<td><a href="https://github.com/tramplinn/mcp-server"><b>mcp-server</b></a> — lets Codex, Claude Code, and other agents fill courses on a teacher's behalf<br><sub>FastMCP · httpx · OAuth 2.1 + PKCE</sub></td>
</tr>
<tr><th>Platform</th></tr>
<tr>
<td><a href="https://github.com/tramplinn/infra"><b>infra</b></a> — proxy, queues, code sandbox, logs, and metrics for stage and prod<br><sub>Docker Compose · Caddy · RabbitMQ · Piston · Prometheus / Loki / Grafana / Alloy</sub></td>
</tr>
<tr><th>Knowledge</th></tr>
<tr>
<td><a href="https://github.com/tramplinn/specs"><b>specs</b></a> — business value, products, use cases, and upcoming changes<br><sub>Markdown</sub></td>
</tr>
</table>

<div align="center">
<a href="../assets/arch.png"><img src="../assets/arch.png" width="720" alt="Tramplin architecture diagram"></a>
</div>

## Getting started

| I want to… | Go to |
| --- | --- |
| **understand the product** | [business value](https://github.com/tramplinn/specs/blob/main/product/business-value.md) → [products](https://github.com/tramplinn/specs/blob/main/product/products.md) → [use cases by role](https://github.com/tramplinn/specs/blob/main/product/use-cases.md) |
| **run it locally** | in **backend**: `make up && make migrate && make seed && make run`, then in **frontend**: `pnpm install --frozen-lockfile && pnpm dev` → http://localhost:5173 |
| **connect an AI agent** | [mcp-server](https://github.com/tramplinn/mcp-server), sign in as a teacher |
