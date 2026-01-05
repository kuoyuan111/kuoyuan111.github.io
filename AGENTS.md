# Repository Guidelines

## Project Structure & Module Organization
- `index.html` is the entire app: HTML, CSS, JavaScript, and the question bank live in one file.
- There are no separate build scripts, assets, or test directories. Keep edits scoped to this file.

## Build, Test, and Development Commands
- `open index.html` (macOS) or double-click the file (Windows): runs the game locally with no server.
- `python3 -m http.server` then visit `http://localhost:8000/index.html`: optional local server when testing on devices.

## Coding Style & Naming Conventions
- Use 2-space indentation for HTML/CSS/JS to match the existing style.
- Keep everything in a single HTML file and avoid external dependencies (no CDN links).
- JavaScript strings must not contain unescaped newlines (use `\n`), especially for iOS/Safari compatibility.
- Naming: prefer clear, descriptive IDs/classes (e.g., `btnStart`, `subjectSel`), and keep new constants in ALL_CAPS only when they are truly constant.

## Testing Guidelines
- No automated tests are configured.
- Manual smoke checks after edits:
  - Start a session, answer a few questions, and finish to see the summary.
  - Verify wrong-book entries persist across reloads (localStorage).
  - Confirm mobile layout works by resizing the browser.

## Content & Question Bank Updates
- Questions are plain JS objects in the in-file bank. Required fields include `id`, `subject`, `topic`, `type`, `q`, `options`, and `answer`.
- Multi-select answers must be an index array (e.g., `[0,2,3]`), and true/false must use `options: ["A 是（○）","B 否（×）"]`.
- Subject/topic filtering is handled by `filterBank()`, so keep `subject` and `topic` consistent.

## Commit & Pull Request Guidelines
- Git history shows simple, short messages (e.g., “Add files via upload”) with no enforced convention.
- If you open a PR, include: a brief description of the change, screenshots for UI changes, and notes on manual testing.
