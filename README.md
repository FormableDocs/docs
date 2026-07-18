# Formable API docs

Documentation for the Formable API, built on [Mintlify](https://mintlify.com).

- **Guides** — introduction, authentication, quickstart, core concepts, and workflow guides (`index.mdx`, `authentication.mdx`, `quickstart.mdx`, `concepts.mdx`, `guides/`).
- **API Reference** — auto-generated from `api-reference/openapi.json`, with one MDX page per endpoint under `api-reference/endpoint/`.
- **Navigation & branding** — configured in `docs.json`.

## Updating the API reference

The reference pages render from the OpenAPI spec at `api-reference/openapi.json`. When the Formable API changes, update that spec (it mirrors the server's `swagger-docs.ts`), then add or adjust the matching MDX file in `api-reference/endpoint/` and its entry in `docs.json`.

Validate changes with:

```
npx mint@latest validate
npx mint@latest openapi-check api-reference/openapi.json
npx mint@latest broken-links
```

## AI-assisted writing

Set up your AI coding tool to work with Mintlify:

```bash
npx skills add https://mintlify.com/docs
```

This command installs Mintlify's documentation skill for your configured AI tools like Claude Code, Cursor, Windsurf, and others. The skill includes component reference, writing standards, and workflow guidance.

See the [AI tools guides](/ai-tools) for tool-specific setup.

## Development

Install the [Mintlify CLI](https://www.npmjs.com/package/mint) to preview your documentation changes locally. To install, use the following command:

```
npm i -g mint
```

Run the following command at the root of your documentation, where your `docs.json` is located:

```
mint dev
```

View your local preview at `http://localhost:3000`.

## Publishing changes

Install our GitHub app from your [dashboard](https://dashboard.mintlify.com/settings/organization/github-app) to propagate changes from your repo to your deployment. Changes are deployed to production automatically after pushing to the default branch.

## Need help?

### Troubleshooting

- If your dev environment isn't running: Run `mint update` to ensure you have the most recent version of the CLI.
- If a page loads as a 404: Make sure you are running in a folder with a valid `docs.json`.

### Resources
- [Mintlify documentation](https://mintlify.com/docs)
