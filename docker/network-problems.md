# Docker Network Problems

## Symptoms

One container cannot reach another container.

## Commands

```bash
docker network ls
docker network inspect <network>
docker inspect <container>
```

## Check

```text
Container A
    │
    │ DNS / TCP
    ▼
Container B
```

Verify:

- both containers share a network
- service name is correct
- target port is correct
- target process is listening
- application binding is compatible with the network

## Common Docker Concept

Inside a Compose network, another service is normally reached by its service name:

```text
postgres:5432
```

rather than:

```text
localhost:5432
```
