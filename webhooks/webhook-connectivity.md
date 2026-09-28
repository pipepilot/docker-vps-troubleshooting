# Webhook Connectivity

## Request Path

```text
External Service
       ↓
     DNS
       ↓
    HTTPS
       ↓
 Reverse Proxy
       ↓
   Application
       ↓
    Webhook
```

## Diagnostic Questions

Determine whether the request:

1. never reached the server
2. reached the reverse proxy
3. reached the application
4. reached the webhook
5. failed during processing

## Commands

```bash
curl -I https://example.com
docker compose logs caddy
docker compose logs n8n
```

For POST webhooks, test with the correct method and content type rather than relying only on a `GET` request.

## Principle

Always identify the first layer where the request stops.
