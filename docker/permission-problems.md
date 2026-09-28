# Docker Permission Problems

## Symptom

Typical message:

```text
Permission denied
```

## Investigation

```bash
ls -la
docker inspect <container>
docker compose config
```

Check:

- container UID/GID
- host directory ownership
- filesystem permissions
- read/write requirements
- mounted volume path

## Avoid Blind Fixes

Do not use:

```bash
chmod -R 777
```

as a default solution.

Instead identify which process needs which permission and change the minimum required ownership or mode.

## Verification

Repeat the original operation and verify that the service works without unnecessarily broad permissions.
