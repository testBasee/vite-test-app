# AGENTS.md — Base44 Dev Environment

## App Overview
- Frontend-only Vite + React + TypeScript + Tailwind app.
- No backend, no database, no external services or credentials required.
- Entry point: `src/main.tsx` → `src/App.tsx` (renders a `Counter` component).

## Running the App
- `docker compose -f docker-compose.base44.yml up -d` brings up the Vite dev server.
- Dev server runs on port 8080 inside the container, mapped to host port 3000.
- Dependencies install on container startup (`npm install`), then `npm run dev -- --host 0.0.0.0` starts Vite with live reload.
- `node_modules` is stored in a named volume (not bind-mounted) to avoid host filesystem conflicts.

## Verification
- `curl http://localhost:3000/` should return HTML with `<title>Vite Test App</title>`.
- Healthcheck confirms the dev server serves the app's HTML.
- Source edits hot-reload automatically (Vite HMR is active).

## Notes
- Vite config (`vite.config.ts`) sets `server.port: 8080` and `host: "::"`; the compose command overrides host to `0.0.0.0` for Docker compatibility.
- No environment variables or secrets are needed.
