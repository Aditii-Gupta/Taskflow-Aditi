# TaskFlow

A project and task management app. Built with React + TypeScript (frontend), Node.js + Express (backend), and PostgreSQL.

---

## Running Locally

> Docker is the only requirement.

```bash
git clone https://github.com/your-name/ag-project
cd ag-project
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
