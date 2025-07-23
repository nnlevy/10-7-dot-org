# Contributor Guide

## Repository Overview
- `index.js` – single Cloudflare Worker script containing server routes, HTML/CSS markup and OpenAI logic
- `README.md` – project overview and manual setup instructions

All code lives in `index.js`. Documentation edits go in `README.md`.

## Development Tips
- Use **Node.js 18+**. The script is designed for Cloudflare Workers but can run in Node with the Fetch API available.
- Search within `index.js` to locate functions. Major sections are marked with comment blocks like:

  ```javascript
  /*************************************************************
   * 2) ALL UTILITY & OPENAI FUNCTIONS
   *************************************************************/
  ```
  Preserve this style when introducing new sections.

## Style Guidelines
- **Indentation:** 2 spaces
- **Strings:** prefer double quotes
- **Semicolons:** required
- Keep lines under ~120 characters when possible.
- Document new functions with brief comments or JSDoc.

## Validation
1. Syntax check: `node --check index.js`
2. Optional formatting check: `npx prettier index.js --check`
3. Run the worker locally (e.g. `node index.js` or `npx miniflare index.js`) with the following environment variables set:
   - `OPEN_API_KEY_NEW`
   - `OPENAI_ORG_ID`
   - `Google_Document_AI_Processor_Prediction_Endpoint`
   - `Google-Service-Account-FINAL`

There is no automated test suite; test by sending HTTP requests to the endpoints.

## Pull Request Instructions
- **Title:** `[10-7] <short description>`
- **Body:**
  - Bullet list of key changes
  - How to run/validate the update
  - Any remaining TODOs or follow‑ups

Keep commits concise and in the imperative mood (e.g. "Add fallback for API errors").
