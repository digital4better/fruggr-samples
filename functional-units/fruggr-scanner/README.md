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
