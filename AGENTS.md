# Repository Guidelines

## Project Structure & Module Organization
- Root config: `_config.yml` (site) and optional `_config.landscape.yml` (theme overrides).
- Content: `source/` holds Markdown posts under `source/_posts/` and any pages/assets.
- Scaffolds: `scaffolds/` define front‑matter templates for `post`, `page`, and `draft`.
- Themes: `themes/` for custom themes; default theme comes from `node_modules/hexo-theme-landscape`.
- Build artifacts: `public/` (generated) and `db.json` are ephemeral; do not edit by hand.

## Build, Test, and Development Commands
- `npm run server` — Start local server at http://localhost:4000 with live reload.
- `npm run build` — Generate static site into `public/`.
- `npm run clean` — Remove cached/generated files.
- `npm run deploy` — Deploy via Hexo’s one‑command deploy (configure `deploy` in `_config.yml`).
- Example: create a post with `npx hexo new post "my-first-post"`.

## Coding Style & Naming Conventions
- Markdown: One H1 per file; sentence‑case headings; wrap at ~100 chars.
- Front‑matter: YAML with clear fields: `title`, `date`, `tags`, `categories`.
- Filenames: lowercase, hyphen‑separated (e.g., `my-first-post.md`). Config uses `new_post_name: :title.md`.
- Indentation: 2 spaces for YAML/Markdown lists and code examples.
- Links/images: Use relative paths under `source/` when possible.

## Testing Guidelines
- No formal test suite. Validate by:
  - Running `npm run build` (should succeed without errors/warnings).
  - Previewing via `npm run server` and checking pages, navigation, and assets.
- Prefer drafts during writing: `npx hexo new draft "post-idea"` then publish when ready.

## Commit & Pull Request Guidelines
- Commits: Small, focused changes with imperative subject (e.g., "add post: async-await guide").
- Include scope keywords when helpful: `content:`, `theme:`, `config:`, `ci:`.
- PRs must include:
  - Purpose summary and screenshots/URLs for visual changes.
  - Linked issue (if applicable) and notes on config changes.
  - Checklist: builds locally, no broken links, no changes to generated `public/`.

## Security & Configuration Tips
- Never commit secrets in `_config.yml` or theme configs; use environment variables or deploy provider settings.
- Keep Node.js to a current LTS (e.g., 18/20) and run `npm ci` for reproducible installs.
