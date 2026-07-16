# Contributing

Documentation changes should make a user task easier or correct product truth.

## Before you edit

1. Read [AGENTS.md](./AGENTS.md).
2. Verify the claim against the current deployment registry and code.
3. Decide whether the page describes something available now, a limitation, or future work.

Do not turn future work into present tense. Do not preserve a page only because the corresponding code still exists.

## Write and review

- Keep one clear purpose per page.
- Lead with what the reader can do.
- Use examples that match the current chain and CLI.
- Explain risks, permissions, and unavailable paths at the point of action.
- Add redirects when removing or renaming a public page.

## Validate

```bash
npx mint broken-links
npx mint validate
npx mint a11y
```

Preview the changed pages at desktop and mobile widths before opening a pull request.
