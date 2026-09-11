# LUMEN — Pricing & Go-to-Market Case

## What this prototype does

LUMEN Launch Cockpit turns the German market-entry question into a guided decision path: understand the market, test price and channel assumptions, evaluate launch timing, and validate an explainable recommendation. The prototype is intentionally focused on decision support rather than automated execution.

## Business approach

The product compares premium, balanced, and penetration launch scenarios. It makes the price–demand–contribution trade-off visible, combines channel economics with timing signals, and presents assumptions and risks so a commercial team can challenge the recommendation before launch.

## Data and privacy

This workspace currently uses illustrative model inputs. The original case CSV files and brief are not present in this checkout, so no claim is made that the prototype is connected to the source datasets. If `customer_survey.csv` is added, name and email columns must not be loaded into the UI, exposed through an endpoint, or committed to derived exports. Only aggregated, anonymised metrics should be used.

## API keys and deployment

No external API is used by the prototype, so no API key is required. Weather and other external signals are represented by model inputs. A production deployment must keep secrets in the hosting provider's environment variables and must not return raw survey data to visitors.

## Storage

Scenario selection is represented in the URL so a decision state is shareable and reproducible. Temporary summary confirmation is client-side only; a production version should use authenticated server-side persistence with an audit trail.

## Robustness and explainability

Pricing inputs validate positive finite prices and non-negative market sizes. Scenario keys fall back to the balanced case when unknown. The recommendation shows its assumptions, trade-offs, confidence, and risks in plain business language. Missing source data should produce an explicit data-quality state rather than silently being treated as zero.

## Development

```bash
pnpm install
pnpm run dev
pnpm run build
```

## Submission checklist

- [x] Functional prototype for the LUMEN case
- [x] Business explanation and rationale documented above
- [x] No hardcoded external API keys
- [x] Personal survey fields explicitly excluded from the product design
- [ ] Original `data/` CSV files and `data/README_data.md` added from the official fork
- [ ] `LUMEN_Case_Brief.md` and PDF added from the official fork
- [ ] Automatic prompt log `prompts/e254955/session-*.md` committed by Codex
- [ ] GitHub remote configured and branch pushed
- [ ] Live Vercel URL added here after deployment

## Our Approach

We built a business-oriented launch cockpit that helps a team move from context to evidence, from evidence to scenario testing, and from scenario testing to an explainable decision. We chose transparent illustrative assumptions because the official case data is not available in this checkout; the next step is to connect the approved CSVs, validate the calculations with the team, and deploy only after the privacy and data-quality checks pass.
