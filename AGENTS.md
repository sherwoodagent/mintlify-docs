# Sherwood documentation instructions

This repository contains the public Sherwood documentation. It is a Mintlify site written in MDX.

## Source of truth

Verify claims in this order:

1. Live reads from the current deployment, when available.
2. `contracts/chains/{chainId}.json` in the Sherwood monorepo.
3. Current contract and CLI source in the Sherwood monorepo.
4. The monorepo `CLAUDE.md` and current project state.
5. Existing public documentation.

Code in the repository is not proof that a feature is deployed. Label testnet, development, roadmap, historical, and dynamic facts explicitly. If sources conflict, stop and resolve the conflict before publishing.

## Current public scope

- Document Robinhood L2 Testnet, chain ID `46630`, as the current fund deployment.
- Document Portfolio as the only deployed strategy template.
- Keep the production WOOD token separate from the testnet fund protocol.
- Do not publish pages for undeployed chains, strategy templates, identity systems, or data services.
- Use `fund` in user-facing prose. Preserve contract names such as `SyndicateVault` when technical precision requires them.
- Use `sherwood fund` as the canonical CLI group. Mention `sherwood syndicate` only as a compatibility alias for existing scripts.
- Keep token vesting separate from the fund protocol. Until the canonical deployment registry includes vesting addresses, label the primitive as unavailable on the current deployment.

## Editorial contract

- Write in US English, active voice, and second person when giving instructions.
- Prefer short, concrete sentences. Explain the mechanism before the benefit.
- State operational limits next to the feature they constrain.
- Never imply that an unavailable or unverified feature is live.
- Remove filler, hype, vague superlatives, canned introductions, and repeated conclusions.
- Avoid stock AI constructions such as "at its core", "more than just", and "not just X, but Y".
- Do not use Unicode en dashes or em dashes. Use commas, parentheses, or a colon.
- Use sentence case for headings.
- Give every code fence a language tag and every image useful alt text.

## Structure and components

- Keep navigation shallow and task-oriented.
- Prefer root-relative links for internal pages. For nested pages, use an explicit relative `.mdx` path when the Mintlify link checker on Windows cannot resolve the canonical root-relative URL.
- Use Mintlify components only when they improve scanning or explain a relationship.
- Use `Steps` for procedures, `CardGroup` for entry points, `Tabs` for true alternatives, and Mermaid for architecture or lifecycle diagrams.
- Do not use decorative components to repeat prose.

## Validation

Run from this repository before requesting review:

```bash
npx mint broken-links
npx mint validate
npx mint a11y
```

Also search for stale chain names, undeployed integrations, unsupported strategy names, Unicode dashes, placeholder text, and unqualified roadmap claims.

## Submodule workflow

This repository is included in the Sherwood monorepo as `mintlify-docs`.

1. Create a branch in this repository.
2. Edit and validate the MDX site here.
3. Open and merge the documentation pull request.
4. Update the `mintlify-docs` submodule pointer in the monorepo in a separate change.

Mintlify deploys the documentation repository's default branch. Updating only the parent submodule pointer does not publish the site.
