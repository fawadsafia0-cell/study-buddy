# Vintage Study Buddy — The Study Society

A responsive AI-powered study app using OpenRouter, Node.js, Express and browser-local textbook storage.

## Run locally
1. Install Node.js 20 or later.
2. Open this folder in VS Code.
3. Run `npm install`.
4. Open `.env` and replace `PASTE_YOUR_KEY_HERE` with your OpenRouter key. Never share or commit this file.
5. Run `npm start`.
6. Visit http://localhost:3000.
7. Open My Library, upload a text-based PDF or paste chapter text, then click Save.
8. Try Chat, Revision, Flashcards and Exam Studio.

## GitHub safety
`.env` is ignored by `.gitignore`. Only `.env.example` is safe to publish. Do not put keys in `public/`, `index.html`, JavaScript, or `manifest.json`. If you accidentally publish a key, revoke it immediately and create a new one. To check: `git status --ignored`.

## Hosting
GitHub Pages can host only the static `public/` files, **not** the `/api` routes. To publish the working app, deploy the complete Node.js project to a backend-capable host (e.g. Render or Railway) and set `OPENROUTER_API_KEY` as a secret environment variable in the host's dashboard. Do not upload `.env` to GitHub. Add HTTPS for phone installation. For a public launch, add user authentication, per-user quotas, and durable database-backed book storage.

## Current limits
- Books are saved only in the current browser's localStorage; there is no cross-device synchronization.
- PDF extraction handles selectable text, not scanned/image-only PDFs.
- PDF extraction is capped at 180,000 characters and AI requests use the first 50,000 characters. For best results save one chapter at a time.
- A free OpenRouter model may have rate limits, limited availability or fail to return valid flashcard JSON. You can change `OPENROUTER_MODEL` in `.env` to a model available to your account.
- PDF text is processed in memory by the server. AI prompts send selected book text to OpenRouter. Review privacy policies before uploading sensitive books.
- Browser installation depends on HTTPS/browser support. The manifest provides app metadata, but offline mode is not supported.


## General AI mode
You can use chat, exams, revision and flashcards without uploading a book. Adding a textbook is optional and helps with exact chapter-specific content.
