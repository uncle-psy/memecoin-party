# Memecoin Party

Responsive multi-creator launchpad frontend for Memecoin Party DUNA, organization ID 638382.

## Run

Serve this folder using any static web server. No build step or dependencies are required. Deploy the root directory to Vercel with framework set to Other.

## Experience

Discovery and network filters; coin details; four-step launch studio with image upload, supply, curves, fees and collaborator allocations; creator profiles; creator dashboard; configuration export; watchlist; wallet provider connection; portfolio; community notebook; notification preferences; governance proposal drafting; dark mode; responsive layouts.

## State and integration boundaries

Browser-local persistence uses the `party:` namespace. A prominent prototype banner appears across all routes. Coins, market data, trades, contract statuses, governance activity, and earnings are illustrative examples. Launching saves a configuration and renders a simulated live coin; it does not mint a token. Trades and claims are simulated and do not move funds. Wallet connection uses installed providers and never requests signing or transfers. Community notes, reports and proposals remain local.

Backend integration: replace browser state with authenticated storage; add chain-specific token factory and curve adapters; index confirmed events; attach quote routing, transaction preparation, wallet signing and confirmation tracking; add collaborator recipient validation, moderation, notifications, governance eligibility and published records. Display success only after the corresponding service or chain confirms it.

Research-derived fee percentages and curve targets are configurable product defaults, not verified platform economics. Contract deployment, audits, authoritative market data, execution, payouts, social authentication, cross-chain bridging and server delivery are not implemented.

## Checks

`node --check app.js`

User-provided branding is in mascot.png. The source research is intentionally excluded from the repository.

## Accounts and internal wallet
Night mode is the default; explicit theme choices persist. account.js implements example sign-in, account creation, invitation code, a browser-local internal USDC ledger, simulated Stripe checkout and external-wallet funding, and balance-aware trades. PARTY-DEMO is the only invitation code. Email, passwords, card information and wallet keys are neither persisted nor transmitted. The example connector does not call installed providers. Production requires server-side authentication, account isolation, ledger accounting, Stripe/onramp and chain integrations, webhook verification and confirmed settlement.
