# PostgreSQL Connection Problems

## Commands

```bash
docker compose ps
docker compose logs postgres
docker compose exec postgres pg_isready
```

## Parameters

Check:

```text
Host
Port
Database
User
Password
Network
```

## Docker Detail

If PostgreSQL runs in another container, the application normally connects to:

```text
postgres:5432
```

not:

```text
localhost:5432
```

## Verification

Test database readiness first, then test the application connection.
