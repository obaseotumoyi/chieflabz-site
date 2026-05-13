# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Workspace Overview

This home directory contains three separate web projects, each with its own git repo:

| Directory | Stack | Purpose |
|---|---|---|
| `my-next-app/` | Next.js 16, React 19, TypeScript, Tailwind CSS v4 | Next.js app |
| `chieflabz-site/` | Static HTML, Netlify | Static site |
| `ekor-blog/` | Eleventy (11ty v2), Nunjucks | Personal blog |

## my-next-app

**Critical:** This uses Next.js 16 — a version with breaking changes from what is in Claude's training data. Before writing any Next.js code, read the relevant guide in `node_modules/next/dist/docs/`. Heed any deprecation notices.

```bash
cd my-next-app
npm run dev      # dev server at http://localhost:3000
npm run build    # production build
npm run lint     # eslint
```

- App Router (`app/` directory) with TypeScript strict mode
- Tailwind CSS v4 (configured via `@tailwindcss/postcss`, not `tailwind.config.js`)
- Path alias `@/*` maps to the project root

## ekor-blog

```bash
cd ekor-blog
npm start        # dev server (npx @11ty/eleventy --serve)
npm run build    # static output to _site/
```

- Source in `src/`, output to `_site/`
- Templates use Nunjucks (`.njk`)
- Custom `date` filter via luxon in `.eleventy.js`
- Passthrough: `src/style.css`, `src/darkmode.js`

## chieflabz-site

Static HTML site. Deployed to Netlify with publish directory set to `.` (repo root).

## Environment

- Package manager: npm
- Runtime: Node via Homebrew
- Containers: OrbStack (Docker-compatible)
