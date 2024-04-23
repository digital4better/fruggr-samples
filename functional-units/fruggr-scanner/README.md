# Running functional unit with Fruggr scanner

You can find here samples about Fruggr scanner.

## Requirements

All samples are built with [Docker Compose](https://docs.docker.com/compose/).
So, install:
- [Docker Desktop](https://docs.docker.com/desktop/)/Engine (Windows/WSL, MacOS, Linux)
- Docker Compose (usually bundled with Docker Desktop)

You also need a Fruggr digital service, with "admin" permission, where you can get [your CI/CD Access Token](https://wiki.fruggr.io/hc/fr/articles/9694438970653). It is named later `FRUGGR_API_KEY`.

## Samples

1. [Basic "go to" a public HTTP URL](navigate)

   The configuration is handled by Fruggr Saas

1. [Test a functional unit when the script is local](testing-local-script)

   The configuration script is local

## Troubleshooting / FAQ

### Error `Fruggr API key is required`

Check the [requirements](#requirements) if you get this message:

```
[scanner] Fruggr API key is required, you must set FRUGGR_API_KEY environment variable
exited with code 1
```

### Error `Fail to create screenshots directory /tmp/fruggr/screenshots`

If you get this message:

```
[scanner] Fail to create screenshots directory /tmp/fruggr/screenshots.
fruggr-scanner-1  | Is a Docker volume mounted and writable for '/tmp/fruggr' container path?
fruggr-scanner-1  |  {
fruggr-scanner-1  |   "stack": "Error: EACCES: permission denied, mkdir '/tmp/fruggr/screenshots'",
fruggr-scanner-1  |   "message": "EACCES: permission denied, mkdir '/tmp/fruggr/screenshots'",
fruggr-scanner-1  |   "errno": -13,
fruggr-scanner-1  |   "code": "EACCES",
fruggr-scanner-1  |   "syscall": "mkdir",
fruggr-scanner-1  |   "path": "/tmp/fruggr/screenshots"
fruggr-scanner-1  | }
```

Check the permissions of the mounted volume on `FRUGGR_DEBUG_PATH`, it must be world-writable (777 permissions).

## Getting help

👉 Documentation and tutorials: https://wiki.fruggr.io/hc

👉 If you need more help: support@fruggr.io
