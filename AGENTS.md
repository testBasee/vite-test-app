# Base44 Dev Environment

## Overview

Minimal Vite + React + TypeScript + Tailwind app. No backend, no database, no external services.

## Running

```sh
docker compose -f docker-compose.base44.yml up -d --build
```

The Vite dev server runs on port 8080 inside the container, mapped to host port 3000. Source is bind-mounted so edits hot-reload. Dependencies install on container startup via `npm install` (no lockfile is committed).

## Verification

- `curl http://localhost:3000/` should return the HTML with `<div id="root">`.
- The page renders a centered card with a counter (− / + buttons).
- No credentials or external services are required.
