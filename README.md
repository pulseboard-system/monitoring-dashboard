# Pulseboard

Pulseboard is a polished, static, client-facing demo of a feedback and review monitoring dashboard for mobile apps. It is designed for screen sharing in sales presentations.

## Run locally

```bash
pnpm install
pnpm dev
```

Build with `pnpm build`; the output is `dist/`.

## Cloudflare Pages

Connect this repository to Cloudflare Pages with:

- Framework preset: Vite
- Build command: `pnpm build`
- Build output directory: `dist`
- Node version: 20 or newer

The project is static and does not require environment variables. It uses browser localStorage for the demo workspace, so each browser keeps its own demo edits.

## Suggested sales walkthrough

Start on Overview, switch the date range, open a theme in Trends, turn it into a reproduction scenario in Testing, create a recommendation, then generate the monthly report. Integrations shows the breadth of the connector catalog while making it clear that live provider access is a production phase.

## Demo limitations and production roadmap

The 78 integrations, sync buttons, analytics, classification and report generation are deliberately simulated/deterministic for a safe sales demo. No API keys or client data are included. A production rollout would need a secure backend, provider-specific OAuth/API credentials, webhooks or scheduled ingestion, normalization, tenant access controls, audit logs, retention rules and a real research/brand governance process. Cloudflare Pages can host this frontend; secrets and live ingestion belong in Workers, a backend service, or another secure server-side environment.
