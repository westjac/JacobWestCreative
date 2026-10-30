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

`.github/workflows/cd.yml` runs `yarn generate` and publishes `dist/` to the `gh-pages` branch with `peaceiris/actions-gh-pages`. GitHub Pages serves that branch with the custom domain from `CNAME` (`jacobwestcreative.com`). The workflow triggers on both `push` and `pull_request`, so a PR build can also deploy.

## Layout

- `pages/index.vue`: home. Logo plus buttons to `/photo`, `/web` and the YouTube channel.
- `pages/photo.vue`, `pages/web.vue`: "coming soon" placeholders.
- `pages/code.vue`: placeholder, not linked from anywhere.
- `layouts/default.vue`: bare `<v-app>`, used by all pages.
- `layouts/jbw-default.vue`: unused Vuetify starter layout. `layouts/error.vue`: 404/error page.
- `components/logo.vue`: logo image from `static/jbw-white.png`.
- `content/hello.md`: Nuxt Content starter file, not rendered anywhere.
- Site metadata (title template, description) lives in `nuxt.config.js` under `head`.
