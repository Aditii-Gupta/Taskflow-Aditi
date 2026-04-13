# TaskFlow

A project and task management app. Built with React + TypeScript (frontend), Node.js + Express (backend), and PostgreSQL.

---

## Running Locally

> Docker is the only requirement.

```bash
git clone https://github.com/Aditii-Gupta/Taskflow-Aditi.git
cd Taskflow-Aditi-main
cp .env.example .env
docker compose up
```

App available at **http://localhost:3000**

---

## Migrations

Migrations and seed data run automatically on startup. No manual steps needed.

---

## Test Credentials

```
Email:    test@example.com
Password: password123
```

Logs in to a pre-seeded account with a sample project ("Website Redesign") and three tasks.

---

## API Reference

All endpoints except `/auth/*` require:
```
Authorization: Bearer <token>
```

### Auth
| Method | Endpoint | Description |
|---|---|---|
| POST | `/auth/register` | Register — body: `{ name, email, password }` |
| POST | `/auth/login` | Login — body: `{ email, password }` |

Both return `{ token, user }`.

### Users
| Method | Endpoint | Description |
|---|---|---|
| GET | `/users/me` | Current user |
| GET | `/users` | All users |

### Projects
| Method | Endpoint | Description |
|---|---|---|
| GET | `/projects` | List your projects |
| POST | `/projects` | Create — body: `{ name, description? }` |
| GET | `/projects/:id` | Get project + tasks |
| PATCH | `/projects/:id` | Update — body: `{ name?, description? }` |
| DELETE | `/projects/:id` | Delete (owner only) |

### Tasks
| Method | Endpoint | Description |
|---|---|---|
| GET | `/projects/:id/tasks` | List tasks (filter: `?status=todo&assignee=<uuid>`) |
| POST | `/projects/:id/tasks` | Create — body: `{ title, description?, status?, priority?, assignee_id?, due_date? }` |
| PATCH | `/tasks/:id` | Update — any task fields |
| DELETE | `/tasks/:id` | Delete |

**Errors:**
```json
{ "error": "validation failed", "fields": { "email": "is invalid" } }
```

