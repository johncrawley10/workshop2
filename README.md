# Containerized Django Deployment Lab

A training project for building and running a multi-service Django application behind an Nginx reverse proxy.

> This repository began as `workshop2`. The code is preserved as a learning artifact and is not presented as a production-ready service.

## What this project demonstrates

- Packaging a Python/Django application in Docker
- Running Django with Gunicorn
- Routing traffic through Nginx
- Connecting to PostgreSQL through environment variables
- Sharing static assets with a Docker volume
- Organizing a small web application with user and tutorial components

## Architecture

```text
Client
  |
  v
Nginx :8000
  |
  v
Gunicorn / Django :8000
  |
  v
PostgreSQL (external, configured with environment variables)
```

## Run the lab

1. Copy `.env.example` to `.env`.
2. Replace every placeholder with values for a PostgreSQL instance you control.
3. Start the services:

```bash
docker compose up --build
```

4. Open `http://localhost:8000`.

## Security notes

- Credentials and deployment endpoints are supplied through environment variables.
- `.env` files are ignored and should never be committed.
- Django debug mode defaults to off.
- The sample configuration is intended for a lab. Review dependency versions, TLS, host restrictions, database access, container privileges, and secret storage before any real deployment.
- If an earlier version of this project was connected to live infrastructure, rotate those credentials; changing the current file does not remove values from Git history.

## Technology

Python · Django · Django REST Framework · Gunicorn · Docker Compose · Nginx · PostgreSQL

## Portfolio context

This project supports my infrastructure and security learning by giving me a system to practice service deployment, configuration management, log review, network flows, and hardening.
