# Brand Context

## Brand
- **Name**: TOON Protocol
- **Category**: Open payments and hosting protocol / developer infrastructure (value routing for apps and agents)
- **Description**: An open network where your app or agent runs on your own machine and gets paid for every request, with no cloud, no domain and no open port.
- **Stage**: Live on mainnet. The project's node at toon.ar.io settles in USDC on Base mainnet and Solana mainnet, and four apps are priced on it. Devnet (Base Sepolia, Solana devnet, test tokens) stays for testing. Independent mainnet operators are not yet shown.
- **Website**: https://toon.ar.io (served from Arweave via the ArNS name `toon`)

## Audience
- **Primary Audience**: Independent developers and AI-agent builders who want to ship an HTTP service or agent from their own hardware, set a price and earn per request, without a cloud account, a payment processor or infrastructure to run.
- **Key Problem**: Getting paid for a small service is harder than building it. You need a public host, a domain, open ports, accounts and a billing stack, and none of that works for agents paying other agents per request.
- **Their Language**: "host it from home", "paid per request", "no account", "self-hosted", "hidden service", "agents paying agents", "micropayments", "just HTTP", "my own machine". From the project's own copy: "every request that reaches it has been paid for", "reads are free, writes are paid".

## Positioning
- **Differentiation**: Payment works like a reverse proxy. A connector terminates payment the way nginx terminates SSL and hands the app ordinary HTTP that has already been paid for. A packet carries its own claim, so there is no invoice or settle round trip. Payments route hop by hop across peered connectors and change token along the way, and the app can sit behind a home router. Thesis: *sending a message and sending money are the same action.*
- **Competitors**: x402 / Coinbase-style HTTP payment rails; Lightning (L402, Nostr zaps); Cloudflare Tunnel / ngrok + Stripe (the status-quo stack); decentralized compute such as Akash.
- **Market Position**: Niche: open-source protocol infrastructure for developers and agents.

## Brand Personality
- **Personality Words**: direct, exact, independent, unhyped, practical
- **Tone**: Casual-leaning but precise; serious, not playful. Engineer to engineer: short declarative sentences, no hype, say what is shipped versus what is planned.
- **Voice Admires**: TBD

## Values & Mission
- **Core Values** (working draft): Sovereignty (your machine, your price, no gatekeeper); Openness (open protocol, open source, free reads); Honesty (state what is live versus in progress; let the node describe itself); Simplicity (plain HTTP at the edge, one config file, one binary).
- **Mission** (working draft): Make getting paid as simple as answering a request, so anyone (person or agent) can run a service from their own machine and earn from it directly.

## Goals
- **Primary Goal**: Get independent operators running nodes on mainnet, and real paid traffic to apps and agents beyond the project's own.
- **Key Metrics**: Live paid apps, paid packets per day, independent operators/nodes, active payment channels.
