# Sherwood documentation

Public documentation for Sherwood, built with Mintlify.

## Local preview

Install the Mintlify CLI and start the preview from this directory:

```bash
npm install -g mint
mint dev
```

The preview opens at `http://localhost:3000` by default.

## Validate a change

```bash
npx mint broken-links
npx mint validate
npx mint a11y
```

Read [AGENTS.md](./AGENTS.md) before changing product claims. It defines the source hierarchy, current public scope, and editorial rules.

## Publish

Open a pull request against this repository. Mintlify deploys the default branch after merge. If you are working from the Sherwood monorepo, update its `mintlify-docs` submodule pointer only after the documentation change is merged.
