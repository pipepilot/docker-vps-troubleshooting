# HTTPS / TLS Problems

## Command

```bash
curl -Iv https://example.com
```

## Check

- certificate validity
- certificate hostname
- TLS handshake
- DNS resolution
- port 443 accessibility
- reverse proxy configuration

## Diagnostic Order

```text
DNS
 ↓
TCP 443
 ↓
TLS handshake
 ↓
HTTP
 ↓
Application
```

This prevents mixing a certificate problem with an application problem.
