# DNS Problems

## Commands

```bash
dig example.com
dig A example.com
dig AAAA example.com
```

## Check

- DNS record
- resolved IP
- authoritative nameservers
- IPv4 / IPv6
- TTL / propagation
- whether the hostname points to the intended server

## Principle

Separate DNS problems from HTTP problems.

If DNS resolves correctly, continue to TCP, TLS and HTTP diagnostics.
