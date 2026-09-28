# HTTP 502

## Meaning

A reverse proxy commonly returns `502 Bad Gateway` when it cannot successfully communicate with the upstream.

## Architecture

```text
Client
  ↓
Caddy
  ↓
Application
```

## Commands

```bash
docker compose ps
docker compose logs caddy
docker compose logs n8n
docker network inspect <network>
```

## Possible Causes

- upstream container stopped
- wrong upstream address
- wrong port
- network problem
- application not listening
- restart loop

## Verification

Test the upstream from the proxy container or network context where appropriate, then repeat the external request.
