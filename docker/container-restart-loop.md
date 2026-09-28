# Docker Container Restart Loop

## Symptom

```bash
docker compose ps
```

shows a service as:

```text
Restarting
```

## Collect Evidence

```bash
docker compose ps
docker compose logs --tail=200 <service>
docker inspect <container>
```

## Hypotheses

- application process crashes
- invalid environment variable
- missing configuration
- incorrect volume permissions
- dependency unavailable
- wrong command or entrypoint

## Investigation

Start with logs. Identify the first meaningful error rather than the final cascade of errors.

Then verify the configuration:

```bash
docker compose config
```

Check mounted paths and container state:

```bash
docker inspect <container>
```

## Verification

After applying one change:

```bash
docker compose up -d <service>
docker compose ps
docker compose logs --tail=100 <service>
```

A successful restart is not enough; verify that the application remains healthy.
