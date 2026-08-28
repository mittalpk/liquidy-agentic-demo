# Liquidy — verified liquidity recovery for SMEs

Liquidy is a Google Cloud hackathon project that helps an SME respond to a cash
shortfall caused by the order in which invoices, payroll, tax and customer
receipts settle.

Gemini 3.5 proposes a bounded mix of supplier, receivable and approved-finance
actions. Deterministic financial engines then recompute every amount and date,
reject unsafe candidates and return the remaining constraint for a bounded
replan. A verified plan still requires human approval before any payment
artifact can be created.

## Technology

- Gemini 3.5 through Vertex AI
- Google GenAI SDK with typed function calls
- Pub/Sub with an OIDC-authenticated accounting-snapshot trigger
- Cloud Run frontend and backend
- Cloud Build and Artifact Registry
- Secret Manager and Cloud Logging
- React, TypeScript and FastAPI

## Demonstrated boundary

The showcase uses synthetic financial data. Gemini does not create ledger facts,
perform authoritative arithmetic or authorize payments. DATEV and ISO 20022
features are controlled subsets; this project does not claim vendor, EPC or bank
certification, a live bank transfer, or production readiness.

The Taskmaster path can start from a connector event: Pub/Sub routes a new
synthetic accounting snapshot to forecast, risk triage, bounded Gemini planning
and counterfactual verification. Human approval is still required for payment
artifacts.

## Architecture

See [docs/OVERVIEW.md](docs/OVERVIEW.md) for the component boundaries and
Google Cloud runtime.

## Source access

The complete implementation, tests and detailed financial-domain controls are
maintained separately. Repository access can be provided to hackathon judges
through the private source repository specified in the submission.

## Links

- Live application: _add the Cloud Run URL before publishing_
- Demo video: _add the public video URL before publishing_

## License

The material in this showcase repository is available under the [MIT License](LICENSE).
