# OpenHiggsfield — agent rules

Open-source image/video generation studio. Next.js 16 App Router, React 19, plain CSS, Zustand, pnpm. Deployed on Vercel.

## Layout
- `src/app/` — routes, layout, `api/` route handlers, `base.css`.
- `src/generation/` — model `catalog/`, platform client (`platform.ts`, `to-platform.ts`), polling, uploads, credentials, `stores/` (Zustand).
- `src/openhiggsfield/` — UI: `composer.tsx`, `gallery.tsx`, `asset-picker.tsx`.
- `src/proxy.ts` — Next 16 proxy (formerly middleware).

## Commands
- `pnpm install` · `pnpm dev` (port 3000) · `pnpm build` (also the type check; there is no lint or test script).

## Rules
- Next.js 16 changed APIs (proxy replaces middleware, async request APIs). Check current docs (Context7) before using a Next API from memory.
- The user's platform key (`id:secret`) must never be logged, persisted server-side or committed.
- Styling is plain CSS; do not add Tailwind or a CSS-in-JS library.
- Adding a model = a catalog entry in `src/generation/catalog/` with its own settings schema.
