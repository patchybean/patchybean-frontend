# Patchybean Frontend

A tiny [Next.js](https://nextjs.org) site that renders Patchy Bean's greeting. The project now exports a fully static bundle so it can be hosted from GitHub Pages without any server side runtime.

## Development

1. Install dependencies with `npm install` (or your preferred package manager).
2. Start the local dev server with `npm run dev` and visit <http://localhost:3000>.
3. Run `npm run lint` to keep the codebase clean.

`npm run build` produces the static site in `out/`, matching what gets published to Pages.

## Continuous Deployment to GitHub Pages

- Workflow: `.github/workflows/deploy.yml` builds the site on pushes to `master` (and on manual dispatch).
- Pipeline steps: checkout ➜ install ➜ lint ➜ `next build` ➜ upload the `out/` directory ➜ deploy via `actions/deploy-pages`.
- Permissions and concurrency are already configured to satisfy the GitHub Pages requirements.

After the first successful run, ensure **Settings → Pages → Build and deployment** is set to **GitHub Actions**. Each subsequent push to `master` will refresh <https://patchybean.github.io/patchybean-frontend/> automatically. You can also trigger redeploys from the **Actions** tab via the manual workflow dispatch.
