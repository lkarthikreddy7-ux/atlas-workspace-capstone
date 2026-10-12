# Atlas Workspace — Production Capstone Demo

A complete static capstone demonstration combining a responsive SaaS project manager and REST API-powered product discovery.

## Features

- Simulated sign-in/profile (name only; **not real authentication**)
- Project CRUD: create, edit, delete, search, filter, change status
- Task CRUD: create, edit, delete, completion toggles, due dates
- Persistent project/task/theme/profile state via browser localStorage
- Live REST API (`https://fakestoreapi.com/products`), search, category filter, sorting, retry, cached data and offline demo fallback
- Accessible dialogs, semantic HTML, responsive mobile/tablet/desktop layout, dark mode
- No backend, build tools, API keys, or credentials required

## Run locally

Open this folder in VS Code and use the **Live Server** extension on `index.html`, or run `python -m http.server 5500` in the project directory and visit `http://localhost:5500`.

## Deploy to GitHub Pages

1. Create a **public** repository named `atlas-workspace-capstone` on GitHub. Do not initialize it with a README.
2. In this folder, run:

```bash
git init
git add .
git commit -m "Complete production capstone demo"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/atlas-workspace-capstone.git
git push -u origin main
```

3. GitHub repository → **Settings → Pages** → **Build and deployment → Deploy from a branch** → `main` / `/(root)` → Save.
4. Once GitHub Pages publishes, your URL will generally be `https://YOUR_USERNAME.github.io/atlas-workspace-capstone/`.
5. Submit **both** the repository URL and live deployment URL as requested by your mentor.

Alternatively, deploy the directory directly to Netlify or Cloudflare Pages as a static site (publish directory: project root).

## Architecture

```text
Browser
 ├─ index.html  → semantic UI / dialogs
 ├─ style.css   → responsive design tokens / themes
 └─ app.js
     ├─ Project/task CRUD + localStorage persistence
     ├─ Simulated profile + theme state
     └─ REST API client → Fake Store API
                           └─ cached products / offline demo fallback
```

## Important scope and security notes

This is a **front-end capstone demo**, not a secure production authentication or multi-user backend. Profiles and projects are stored on each device/browser; clearing localStorage removes local data. Never store real passwords or sensitive information here. Fake Store API product data is public sample data. Offline demo fallback is explicitly labeled in the UI. There is no payment processing.

## Evaluation checklist

- Create/edit/delete a project and refresh: changes should persist.
- Add/edit/delete a task, toggle its checkbox and refresh.
- Test project search and active/completed filters.
- Enter a demo name, switch theme, refresh and verify persistence.
- Check product search/category/sort; click Refresh to retry the API.
- Test mobile layout and browser Console for JavaScript errors.
- Deploy and verify public GitHub Pages URL.
