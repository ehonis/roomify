# Roomify

Roomify is a secure-by-default Next.js web application for browsing and booking rooms. This README gives first-time contributors everything needed to set up the project locally and understand the tooling involved.

## Tech Stack

- Next.js 16 (App Router, TypeScript-first)
- React 19 with concurrent features
- TypeScript 5 for end-to-end typing
- Tailwind CSS 4 (`@tailwindcss/postcss`) for styling
- PostCSS pipeline for CSS transforms
- ESLint 9 with `eslint-config-next`
- Node.js runtime (recommended: Node 20 LTS)

## Prerequisites

- Node.js 20 LTS (Next.js 16 requires Node 18.18+, but we standardize on Node 20 for security updates)
- npm 10 (bundled with Node 20; pnpm or yarn work but npm is the default)
- Git
- Optional: Editor with TypeScript and ESLint support (VS Code + relevant extensions)

## Repository Layout

- `/` – Workspace root (global docs, meta files)
- `/roomify` – Next.js application root (run all commands here)
  - `app/` – App Router pages and layouts
  - `public/` – Static assets
  - `globals.css` – Global styles
  - `next.config.ts`, `postcss.config.mjs`, `tailwind.config` – Build tooling

## First-Time Setup

1. Clone the repository and move into the app directory:
   ```bash
   git clone <your-fork-url> roomify
   cd roomify/roomify
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Configure environment variables:
   - Duplicate `.env.example` to `.env.local` if present.
   - Never commit secrets; store them in a secure vault or the deployment platform.
4. (Optional) Enable pre-commit linting by installing your preferred Git hooks (e.g., Husky or lefthook).

## Running the App

- `npm run dev` – Starts the development server at `http://localhost:3000` with hot reload.
- `npm run build` – Creates an optimized production build.
- `npm run start` – Serves the production build locally (run `npm run build` first).
- `npm run lint` – Lints the codebase with ESLint.

> Tip: If you use another package manager, ensure lockfiles stay consistent and security policies are enforced.

## Security & Quality Checklist

- Use an up-to-date Node.js 20.x release (run `node --version` to confirm).
- Run `npm audit` after dependency upgrades; patch high-severity findings promptly.
- Keep dependencies scoped to the minimum required.
- Run `npm run lint` before pushing changes.
- Review `.env.local` locally only; rely on secure CI secrets for deployments.

## Troubleshooting

- Dependency errors: delete `node_modules` and the lockfile, reinstall with `npm install`.
- Port conflicts: set `PORT=3001` (or another open port) in `.env.local`.
- Type errors: run `npm run lint` to surface detailed diagnostics.

## Learn More

- Next.js: https://nextjs.org/docs
- Tailwind CSS: https://tailwindcss.com/docs
- TypeScript: https://www.typescriptlang.org/docs/

For questions or security concerns, notify the maintainers before sharing sensitive details publicly.
