# Agent instructions

## Scope and privacy

- Work only within this Chromium source checkout. Do not stage, copy, or publish files from parent or sibling folders.
- Never commit API keys, access tokens, passwords, credentials, private endpoints, personal data, or other sensitive material. Check every diff for sensitive data before committing.
- Do not add API credentials or external API/service integrations unless the user explicitly changes this instruction.

## Changes and commits

- Make the smallest change that fulfills the user's request and is enough for the requested behavior to run.
- Do not add or run tests, builds, linters, benchmarks, or other validation unless the user explicitly asks.
- Upload each completed requested change from this checkout to `2q9e/uwu-browser` using the GitHub plugin. Include every added, modified, and deleted file in that change. Make one commit per small, independently complete change as soon as it is ready; do not batch unrelated changes. Use GitHub plugin commit/ref or contents operations instead of `git push`.
- Never upload to the Chromium upstream remote (`origin`) or publish files from outside this checkout.
