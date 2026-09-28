# Docker Compose Configuration Errors

## First Step

Validate the resolved Compose configuration:

```bash
docker compose config
```

## Useful Checks

```bash
docker compose ps
docker compose config
docker compose logs
```

Check:

- YAML indentation
- environment variables
- volume paths
- service names
- networks
- health checks
- dependency conditions

## Principle

Fix the configuration error before repeatedly restarting containers. A restart does not correct an invalid configuration.
