# CLAUDE.md

Jacob West's personal site, served at https://jacobwestcreative.com.

## Stack

- Nuxt 2 (`target: 'static'`) with Vuetify 2 (dark theme), `@nuxt/content` and `@nuxtjs/axios`.
- Yarn 1 with `yarn.lock`. ESLint via `@nuxtjs/eslint-config`.
- No tests.

## Commands

```bash
yarn install
yarn dev       # localhost:3000
yarn generate  # static site into dist/
yarn lint
```

Node version matters. The deps (Nuxt 2.14, node-sass/fibers) only build on **Node 14**, which is what CI uses. On Node 16+ `nuxt generate` fails (fibers binary missing, then a `Function.prototype.apply` fatal on Node 22). Use `nvm use 14` or similar, or upgrade the stack first.

## Deploy

There are two deploy paths:

- **Netlify** (project `jacobwestcreative`) is connected to the repo and builds every PR into a deploy preview (`deploy-preview-<n>--jacobwestcreative.netlify.app`). Build settings live in the Netlify dashboard, since the repo has no `netlify.toml`. This is probably what serves production.
- `.github/workflows/cd.yml` is a legacy GitHub Pages workflow (`yarn generate`, then push `dist/` to `gh-pages`, with the domain from `CNAME`). It runs on `push` and `pull_request`, and it currently **fails** at `yarn install`: node-gyp can't build node-sass/fibers on the current ubuntu-latest runner. Remove it or fix it during a stack upgrade.

## Layout

- `pages/index.vue`: home. Logo plus buttons to `/photo`, `/web` and the YouTube channel.
- `pages/photo.vue`, `pages/web.vue`: "coming soon" placeholders.
- `pages/code.vue`: placeholder, not linked from anywhere.
- `layouts/default.vue`: bare `<v-app>`, used by all pages.
- `layouts/jbw-default.vue`: unused Vuetify starter layout. `layouts/error.vue`: 404/error page.
- `components/logo.vue`: logo image from `static/jbw-white.png`.
- `content/hello.md`: Nuxt Content starter file, not rendered anywhere.
- Site metadata (title template, description) lives in `nuxt.config.js` under `head`.
