# BloodBridge

A blood donation and availability platform built with React, TypeScript, Vite, Tailwind CSS, shadcn/ui, and Supabase.

## Local Development

```bash
npm install
npm run dev
```

The dev server runs at `http://localhost:8080` by default.

## Build

```bash
npm run build
npm run preview
```

## Environment Variables

Copy `.env.example` to `.env` and fill in the values you need.

The frontend can run without Supabase variables. In that standalone demo mode, backend-backed actions such as authentication, AI assistant responses, password reset emails, uploads, and database writes return safe errors instead of crashing the UI.

Required for live backend features:

```bash
VITE_SUPABASE_URL=
VITE_SUPABASE_PUBLISHABLE_KEY=
```

Supabase Edge Functions use their own server-side variables from `.env.example`, such as `SUPABASE_SERVICE_ROLE_KEY`, `ADMIN_SECRET_KEY`, `BREVO_API_KEY`, `ELEVENLABS_API_KEY`, and `OPENAI_API_KEY`.

## Deployment

This project is ready for Vercel as a static Vite SPA. `vercel.json` rewrites all routes to `index.html`, so direct visits to React Router routes work after deployment.

Set the same frontend variables in the deployment environment if you want live Supabase features.

## Project Structure

```text
src/
  components/       Reusable UI and feature components
  config/           App route constants
  hooks/            React hooks
  integrations/     Supabase client wrapper
  lib/              Utilities
  pages/            Route pages
  test/             Vitest setup and tests
supabase/
  functions/        Edge Functions
  migrations/       Database migrations
```
