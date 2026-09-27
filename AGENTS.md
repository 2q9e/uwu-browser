# Agent instructions

## Scope and privacy

- Work only within this Chromium source checkout. Do not stage, copy, or publish files from parent or sibling folders.
- Never commit API keys, access tokens, passwords, credentials, private endpoints, personal data, or other sensitive material. Check every diff for sensitive data before committing.
- Do not add API credentials or external API/service integrations unless the user explicitly changes this instruction.

## Changes and commits

- Make the smallest change that fulfills the user's request and is enough for the requested behavior to run.
- Do not add or run tests, builds, linters, benchmarks, or other validation unless the user explicitly asks.
- Commit and push each small, independently complete requested change to `https://github.com/2q9e/uwu-chromium.git` as soon as it is ready. Do not batch unrelated changes into a later commit.
- Never push to the Chromium upstream remote or publish files outside this checkout.
