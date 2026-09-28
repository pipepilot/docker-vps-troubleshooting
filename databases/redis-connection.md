# Redis Connectivity

## Commands

```bash
docker compose ps
docker compose logs redis
docker inspect redis
docker compose exec redis redis-cli ping
```

Expected response:

```text
PONG
```

## Check

- service name
- port 6379
- shared Docker network
- Redis process state
- application Redis configuration

## Principle

Test connectivity from the same network context as the application.
