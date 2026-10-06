# Base44 Dev Environment

## Overview
Vite + React + TypeScript + Tailwind frontend-only app. No backend, no database, no external services.

## Running
- `docker compose -f docker-compose.base44.yml up -d --build`
- Dev server (Vite) runs inside the container on port 8080, mapped to host port 3000.
- Source is bind-mounted; edits hot-reload via Vite HMR.
- Dependencies install on container startup via `npm install`.

## Verification
- `curl http://localhost:3000/` should return the HTML page with title "Vite Test App".
- The app renders a centered card with a counter component.

## Notes
- Vite config uses `host: true` + `allowedHosts: true` to accept the preview's external hostname.
- No secrets or external credentials are required.
