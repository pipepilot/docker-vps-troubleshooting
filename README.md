# Docker VPS Troubleshooting

**Practical Linux, Docker and VPS troubleshooting cases.**

This repository documents reproducible infrastructure problems and the diagnostic process used to identify and resolve them.

> **Problem → Evidence → Hypotheses → Testing → Fix → Verification**

## Repository Structure

```text
docker-vps-troubleshooting/
├── README.md
│
├── docker/
│   ├── container-restart-loop.md
│   ├── permission-problems.md
│   ├── network-problems.md
│   └── compose-errors.md
│
├── networking/
│   ├── http-403.md
│   ├── http-502.md
│   ├── dns-problems.md
│   └── tls-problems.md
│
├── databases/
│   ├── postgres-connection.md
│   └── redis-connection.md
│
└── webhooks/
    └── webhook-connectivity.md
```

## Troubleshooting Method

```text
Problem
   ↓
Collect evidence
   ↓
Form hypotheses
   ↓
Test hypotheses
   ↓
Fix
   ↓
Verify
   ↓
Document
```

## Diagnostic Toolkit

### Docker

```bash
docker ps
docker ps -a
docker compose ps
docker compose logs
docker inspect <container>
docker stats
docker network ls
docker network inspect <network>
```

### Linux

```bash
systemctl status <service>
journalctl -u <service>
df -h
free -h
uptime
top
```

### Networking

```bash
ss -tulpn
ip addr
ip route
ping
curl
dig
```

### Configuration

```bash
docker compose config
```

## Engineering Principles

1. Collect evidence before changing configuration.
2. Change one important variable at a time.
3. Prefer reversible changes.
4. Verify the result.
5. Document the root cause.

## Security

Never publish:

- passwords
- API keys
- SSH private keys
- Telegram bot tokens
- database credentials
- client data
- production `.env` files

Use placeholders such as:

```text
example.com
192.0.2.10
YOUR_API_KEY
YOUR_PASSWORD
```

## Case Format

Each case should contain:

```text
Problem
Symptoms
Environment
Initial Evidence
Hypotheses
Investigation
Root Cause
Fix
Verification
Prevention
```

## What This Repository Demonstrates

- Linux troubleshooting
- Docker
- Docker Compose
- container networking
- PostgreSQL
- Redis
- reverse proxies
- Caddy
- DNS
- HTTPS / TLS
- webhooks
- log analysis
- systematic troubleshooting

## Disclaimer

The examples are demonstrations and should be adapted to the specific environment before production use.
