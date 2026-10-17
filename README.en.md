# Resource contract checks 1.0.0

[Português](README.md) · [English](README.en.md) · [Español](README.es.md)

Standalone reusable composite Action with the CLI and engine included. Requires Node.js 20+ on the runner. MIT. The check installs no dependencies and makes no network requests.

In the main repository, checkout and use the local path. From another repository use `YagoLagrottiBracco/portfolio/packages/resource-action@master` (prefer a reviewed full commit SHA). Alternatively extract the ZIP to `.github/actions/resource-check` and use `uses: ./.github/actions/resource-check`.

```yaml
steps:
  - uses: actions/checkout@v4
  - uses: YagoLagrottiBracco/resource-contract-checks@v1
    with:
      tool: env
      reference: .env.example
      candidate: .env.ci
```

Inputs: `tool` (`json` or `env`), `reference`, `candidate`. Outputs: `status` and `exit-code`. The step fails with 1 for differences and 2 for invalid input. Summaries publish only status and counts, never paths, key names, snippets or values. Arguments use environment variables without shell interpolation.

The Action is published in this repository with `v1` and `v1.0.0` tags and a `v1.0.0` release. Real workflow execution passed on Node 20 and 22 in GitHub Actions. Prefer a reviewed full commit SHA. Marketplace listing requires account acceptance; no listing is claimed. The immutable ZIP preserves its release-preparation documentation.

```sh
node --test test/*.test.mjs
```

[Source](https://github.com/YagoLagrottiBracco/resource-contract-checks) · [Metadata syntax](https://docs.github.com/en/actions/reference/workflows-and-actions/metadata-syntax)
