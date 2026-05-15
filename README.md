# htmx-go-pgsql-todo

A To Do example based on HTMX and Go backed by PostgreSQL.

The app renders HTML on the server, uses HTMX for partial updates, and stores
data in PostgreSQL.

## Requirements

- Go 1.22+
- PostgreSQL 16+

## Run PostgreSQL

Start a local database with Docker:

```bash
docker compose up -d postgres
```

## Configure

Default connection settings:

```text
DATABASE_URL=postgres://todos:todos@127.0.0.1:5432/todos?sslmode=disable
ADDR=127.0.0.1:3456
```

## Run the app

```bash
go run .
```

Open `http://127.0.0.1:3456`.

## Behavior

- `GET /` serves the HTMX shell
- `GET /todos` renders the current list
- `POST /todos` creates a task
- `PUT /todos/{id}` toggles completion
- `DELETE /todos/{id}` removes a task

The application creates the `todos` table automatically on startup and seeds a
couple of sample items when the table is empty.
