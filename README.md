[README (1).md](https://github.com/user-attachments/files/35124652/README.1.md)
# hermes-docker-demo

Containerized Python API + Redis, orchestrated with Docker Compose.
Built end-to-end by an AI agent (Hermes) from a Telegram chat message.

## Stack
- Python 3 (stdlib HTTP server)
- Redis 7
- Docker + Docker Compose
- Non-root container user, HEALTHCHECK, restart policy

## Run it

```
docker compose up --build
```

## Test it

```
curl http://localhost:8000/        # app info (JSON)
curl http://localhost:8000/redis   # redis check (returns +PONG)
```

## Useful commands

```
docker compose ps           # list running containers
docker compose logs -f app  # follow app logs
docker compose down         # stop everything
docker images               # see image sizes
```

## Files
- `app.py` — HTTP API with `/` and `/redis` endpoints
- `Dockerfile` — python:3.12-slim, non-root, healthcheck
- `docker-compose.yml` — app + redis services
- `.dockerignore` — keeps the image clean
