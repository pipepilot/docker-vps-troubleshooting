# HTTP 403

## Meaning

`403 Forbidden` means the server understood the request but refused access.

## Find the Layer

```text
Internet
   ↓
DNS
   ↓
Reverse Proxy
   ↓
Application
```

## Commands

```bash
curl -I https://example.com
docker compose logs caddy
docker compose logs n8n
```

## Check

- authentication
- path matching
- request method
- reverse proxy rules
- headers
- application authorization

## Verification

Repeat the exact request that originally produced `403` and confirm which layer now returns the expected response.
