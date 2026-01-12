# Copilot / AI agent instructions for Rose City Roll placeholder site

Summary
- **Type:** Static single-page placeholder website (HTML + CSS + media).
- **Main files:** [index.html](index.html), [404.html](404.html), [style.css](style.css), `media/` (fonts, images, video).

Quick context
- This repository holds a small static site (no build system). The root `index.html` is the live landing page. `404.html` is a simple error page. Styles are in `style.css` and custom fonts/images/videos live under `media/`.
- A `CNAME` file is present which indicates GitHub Pages is used with a custom domain; the default branch is `main`.

What you should do as an AI coding agent
- Preserve the simple, static nature: avoid adding heavy frameworks, build tooling, or package managers unless the user requests them.
- Prefer small, targeted edits to `index.html`, `404.html`, and `style.css` for content, layout, and asset updates.

Patterns & examples (concrete)
- Hero content: edit the page title and tagline in [index.html](index.html) — look for the `<h1>` and the following `<p>`.
- Background video: file at `media/VistaStateWebBackdrop.mp4`. To swap or resize, update the `<video>` source in [index.html](index.html) and adjust `.backdrop-vid` in [style.css](style.css).
- Logos & images: stored in `media/images/` (e.g., `UnionDeCulturas-logo.svg`, `404-animated-web.webp`). Note: `404.html` uses an absolute path `/media/images/404-animated-web.webp` which requires serving from the repo root.
- Fonts: custom font declared via `@font-face` in [style.css](style.css) using `media/fonts/futura.ttf`.
- Links: the “More information” button uses an external Instagram URL in the `#more-info` anchor—update the href directly if needed.

Developer workflows
- Local preview (no build): run a static server from the project root so absolute paths resolve correctly:

  - `python -m http.server 8000`
  - or: `npx serve .`

  Then open `http://localhost:8000`.
- Deploy: updating the `main` branch and pushing to GitHub will update Pages (repository appears to be configured for Pages with `CNAME`). Confirm Pages settings in the repo if asked to change domain or branch.

Conventions & gotchas specific to this repo
- Keep edits minimal and reversible: this is a lightweight landing page meant as a placeholder.
- Watch for absolute vs relative paths: `404.html` uses `/media/...` (rooted) while other pages use `./media/...`—test locally with a server.
- CSS uses many ID selectors (`#content-container`, `#overlay`, `#more-info`) and `overflow: hidden` on `html`/`body`; UI changes may be hidden unless you adjust sizing or `overflow`.
- Favicon referenced as `./media/bigrosecityroll(small).svg` — preserve or update this file if changing branding.

When to ask the user before changing things
- Changes that affect hosting (CNAME, branch, Pages settings), the custom domain, or adding new external services.
- Large redesigns or adding scripts that change privacy/security posture (analytics, trackers, external embeds).

If you make edits
- Create a short PR with a one-line summary and list touched files. Keep diffs small (single-purpose commits).
- In the PR description, include a preview URL or instructions to run locally using `python -m http.server 8000`.

Questions for the maintainer
- Do you want this to remain a single-file static landing page, or should we introduce a minimal build step (e.g., for templating)?

End of file
