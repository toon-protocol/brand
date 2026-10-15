# Brand Strategy: TOON Protocol

*Drafted 2026-10-15 from [context.md](context.md), [audience.md](audience.md), [positioning.md](positioning.md), [messaging.md](messaging.md), [voice.md](voice.md), [story.md](story.md), [architecture.md](architecture.md), [identity.md](identity.md), [competitors.md](competitors.md), [competitors-more.md](competitors-more.md), [guidelines.md](guidelines.md) and [audit.md](audit.md). No questionnaire was filled in, because the package already answers every question on it, so this goes straight to the report (brand-strategy skill, step 3). The skill's template is written for consumer brands, so it's adapted here for developer infrastructure: section 06 uses role, setup, hardware, spend intent and where people are found in place of age bands, income and city tiers, and section 09 has no regional split. Three things are inferred, not captured: the personality sliders in section 07 (read from voice.md and identity.md), the goals in section 05 (read from context.md and audit.md, with no dates confirmed), and the vision, which is still the assumption in positioning.md section 03. This file sets no new direction. Where it and a source file disagree, the source file wins and this file gets fixed. Stage: live on Base and Solana mainnet through the project's own node at toon.ar.io, with devnet (Base Sepolia, Solana devnet) for testing. No independent operators are shown yet, and "no open port" is shown on devnet only.*

---

## 01 — What is TOON?

> **"Every packet carries its own payment."**

TOON started from one idea. Jonathan Green worked on Interledger, where a payment is a packet that connectors forward hop by hop, and on Nostr, where a note is a signed message that relays pass on. At some point the two stopped looking like different things: a packet that carries a message can carry the payment for it too. Sending a message and sending money are the same action. If every request pays for itself, whatever answers it needs no invoice, no account and no billing system. Full version: [story.md](story.md).

TOON makes that work on a real machine. A connector sits in front of your app and handles payment the way nginx handles SSL: it refuses an unpaid request with the price and passes a paid one on as plain HTTP. Payments route hop by hop between peered connectors and settle in USDC on x402 channels, and a new TOON app is a hidden service by default, reachable with no open port and no public address. The operator gets a service on hardware they already own, at a price they set, with no server, no domain and no payment company to sign up with. Today that runs on mainnet through one node, the project's own, and the next step is other people running theirs.

---

## 02 — Brand vision

> *"To become the default way to run a paid service from your own machine: built on sovereignty, openness and honesty about what's live. Anyone, person or agent, should be able to put a price on what already runs on their hardware and have the world reach it and pay for it, with no company holding the money."*

This is the vision positioning.md section 03 assumed, unchanged, and guidelines.md still lists it as unconfirmed. It's ambitious for a protocol with one live node. It's grounded because each part of it already works on that one node.

**Sovereign · Reachable · Paid · Open**

---

## 03 — Brand mission

> *"Make getting paid as simple as answering a request, so anyone, person or agent, can run a service from their own machine and earn from it directly. TOON does that with one binary that terminates payment in front of a plain HTTP app, a protocol that takes no fee, and a public line between what is live and what is next."*

The first sentence is the working mission from context.md. The second is how it's delivered day to day: the connector, the absent fee and the live label are the three things every release has to keep true.

**Plain · Scriptable · Feeless · Labeled**

---

## 04 — Brand values

These are the four working values from context.md, unchanged.

**Sovereignty**
Your machine, your price, nobody's permission. TOON never holds the money, never runs your code and never takes a cut, and any product decision that puts TOON in the middle is the wrong one.

**Openness**
The protocol is open, the code is MIT licensed, reads are free and there's no protocol fee. Anyone can run a connector, and TOON credits Interledger and x402 as the parts it builds on.

**Honesty**
Say what's live and what's next in the same breath as the claim: mainnet is mainnet, devnet is devnet, test tokens are test tokens. When independent operators exist, the brand gives their number, not an adjective.

**Simplicity**
Plain HTTP at the edge, one binary, one config file. The app behind the connector should never need to know it's being paid for.

**Your machine · Your price · Proof · Plain**

---

## 05 — Brand goals

*Inferred from context.md (primary goal and key metrics) and audit.md (priority recommendations). None has a confirmed date. Each one starts from zero or close to it today.*

**Ship the brand that's already written:** Publish the website's `main` to Arweave and repoint ArNS `toon`, then bring the GitHub org bio and the repo READMEs onto "Your machine. Paid per request." and the packet mark. Until that's done, every first impression carries the retired copy (audit.md, problem 1).

**Get the first independent connector operator:** Someone outside the project running a connector on mainnet, peered and routing paid packets. That's the proof "anyone can run a connector" is still waiting for, and the count goes in the live/next block the day it's above zero.

**Re-run the behind-NAT demo on mainnet:** The [home-router demo](https://github.com/toon-protocol/echo-merchant/tree/main/demo/behind-nat) is one run on devnet with test USDC, through the project's relay. Repeating it on mainnet, ideally through a connector the project doesn't run, moves key message 1 from "shown on devnet" to live.

**Own the sentence before Tailscale does:** Tailscale could add payment to Funnel in one product step (positioning.md section 02). TOON's window is to be the name people attach to paid self-hosting in r/selfhosted, r/LocalLLaMA, Hacker News and Nostr first, with a terminal recording and a receipt rather than an announcement.

**Get paid traffic that isn't the project's own:** A paid request to an app the project doesn't run, from a caller the project doesn't run. Then publish paid packets per day and active channels, even while the numbers are small.

**Make the first ten minutes reliable:** `toon up` to a priced app on devnet on one short page, with no surprises, and a macOS build after that. For this audience an install failure is a brand failure (audience.md section 06).

---

## 06 — Target audience

> **Developers and agent builders who already run something useful on their own hardware, and want it reachable and paid per request without renting a server, opening a port or signing up with a payment company.**

| Role | Setup | Hardware | Spend intent | Where they're found |
|---|---|---|---|---|
| Backend engineers, contractors and agent builders with side projects; plus agents operating agent nodes | Self-hosted: a homelab, a local model, a small API or an agent, often already behind Tailscale | A GPU box, a mini PC, a Raspberry Pi, a cheap VPS | Low and per call. Fund a wallet with a little USDC, price an app in fractions of a cent, never a subscription | r/selfhosted, r/homelab, r/LocalLLaMA, Hacker News, GitHub, Nostr, agent-framework Discords |

*All of this is a hypothesis: there's no customer data yet. The full profile, the segments and how to test them are in [audience.md](audience.md).*

### Audience personas

These are the three personas from audience.md, summarised. They're fictional archetypes and use they/them.

**Sam, 34, backend engineer with a homelab, Lisbon. Runs a 4090 in a closet behind Tailscale.**
- *Writes Go by day and runs Proxmox, a GPU box and Home Assistant at home; strangers on a Discord have asked to use their fine-tuned model.*
- *"I'm not starting a SaaS for that. I just want it to pay for its own power bill."*
- **Goals:** Charge per call for the model without writing billing code, on the machine they already own, at a price they set.
- **Challenges:** Tunnels make it reachable but don't pay, payment rails pay but assume a public server, and platforms that do both want the code on their servers.
- **Needs:** An install that works the first time, an honest statement of what's live, and evidence that a stranger can reach and pay the box without port forwarding.
- **How TOON solves it:** The connector on Sam's machine refuses unpaid requests and passes paid ones to the model as plain HTTP, with no server, domain, open port or payment account.

**Priya, 29, independent AI-agent builder, Bengaluru. Runs agents on a home server and a cheap VPS.**
- *Builds agents as a contractor; their agents call search, scraping and model APIs, each with its own key and monthly bill.*
- *"My agent can do the work. What it can't do is buy an API call without my card, or sell its own answer to another agent."*
- **Goals:** Let agents pay per request within a spending limit, sell one agent's output to other agents, and keep it all scriptable.
- **Challenges:** Every service wants an account and a card, marketplaces take a cut and hold the payout, and most "agent payment" products are a waitlist.
- **Needs:** A CLI an agent can drive, with JSON output, stable exit codes, prices up front, a hard spending limit, and a clear line between mainnet and devnet.
- **How TOON solves it:** One way for agents to pay and be paid per request, with `--json` on every command and a spending limit, so no account or card stands between them.

**The operating agent, an agent running its own agent node.**
- *Given a machine, a funded wallet and the TOON skills; reads `--help`, runs `toon` commands and pays other agent nodes, with nobody watching each step.*
- *"Reads are free. Writes are paid. I need the price before I pay and an exit code I can branch on."*
- **Goals:** Finish a task that needs a paid service inside the spending limit, and operate the agent node without a human.
- **Challenges:** Interactive prompts, captchas, KYC, prose errors and output that changes shape between versions.
- **Needs:** Deterministic, non-interactive commands, one JSON document per command, and refusals as values with the price and remaining limit.
- **How TOON solves it:** Every `toon` command takes `--json`, states what it pays and needs `--yes`, so an agent can run an agent node with no human step.

---

## 07 — Brand personality

*The sliders were never captured. These positions are inferred from voice.md section 02 (tone dimensions) and identity.md section 03 (colour personality). Confirm or correct them.*

| Pair | Position (1–8) | Read from |
|---|---|---|
| Playful → Serious | **6** | Serious, with at most one dry line per page |
| Casual → Formal | **4** | Slightly casual, never loose: contractions in prose, spec-level precision on names and numbers |
| Affordable → Premium | **5** | The pair fits a protocol badly. TOON refuses to compete on price, and operators set their own, but the craft reads as well-made, not luxury: "a part number on a well-made machine" |
| Classic → Innovative | **6** | A new mechanism, presented in the classic form of an engineering document |
| Muted → Bold | **3** | Three flat colours on paper, gold kept to 10–20% of any layout, no gradients or neon |

**Serious · Slightly casual · Well-made · Inventive · Muted**

**Brand personality statement**: TOON is the engineer who runs the thing they're describing. It shows the terminal before it makes a claim, and it states what's live and what's next without being asked. It takes the operator's side quietly, through what it refuses to need (an account, a domain, an open port), and never through attacks on anyone else. In a category that shouts, its confidence comes from specifics: a command, a price with its unit, a receipt that checks against a public chain.

---

## 08 — Brand voice

**TOON speaks with calm precision: direct, exact and unhyped.**

The voice is the README of something its author actually runs. It says what the thing does, what it costs and what happens when you type the command, in that order, one fact per sentence. The reader is a peer who will check, human or agent, about to put their own machine on the line. The audit scored voice as the brand's strongest asset, and it's already live. Full detail: [voice.md](voice.md).

**Direct**
Lead with the outcome or the command, then the reason. No warm-up and no wind-down.

**Exact**
Use the defined names from `toon_cli/CONTEXT.md`, give numbers as numbers, and quote what a command actually prints. "Every command that pays states its amount and needs `--yes`" beats "payments are safe".

**Honest about state**
Every claim carries its stage: mainnet, devnet or next. "Start earning today" is never written, because it implies traffic that isn't shown.

**Unhyped**
No superlatives, no "revolution", no future-of-anything. The strongest TOON sentences are the plainest ones, like "No protocol fee."

**Independent**
TOON is on the operator's side: their machine, their price, nobody's permission. That shows in "No cloud · no domain · no open port", not in sneering at Big Tech.

**Practical**
Every page leaves the reader able to do something next. Show the command, the output and the following step.

---

## 09 — Competitor analysis

*Eight of the eighteen brands profiled in [competitors.md](competitors.md) and [competitors-more.md](competitors-more.md), chosen because a TOON prospect is most likely to compare against them. The full profiles, sources and visual analysis are there.*

**x402** (x402 Foundation, Linux Foundation; originated at Coinbase)
- **Overview:** The open HTTP 402 standard for charging per request, now with about 40 members including Visa, Circle, Cloudflare and Coinbase.
- **Strengths:** Real traction shown on its homepage (75.41M transactions in 30 days), neutral governance, and the name people mean when they say "pay per request over HTTP".
- **Weaknesses:** In practice it runs through Coinbase's facilitator, and it assumes the seller already has a public server and domain.
- **How TOON is different:** x402 is a layer under TOON, not a rival: every TOON channel is an x402 batch-settlement channel. TOON adds what x402 assumes away, the route to an app on the operator's own machine. "ILP routes, x402 settles."

**Lightning Labs / L402**
- **Overview:** Lightning Network software, with L402 as its HTTP 402 protocol served by Aperture, a reverse proxy.
- **Strengths:** Five years of L402 in production, the closest prior art to "payment as a reverse proxy", and a voice that talks to agents directly.
- **Weaknesses:** Bitcoin only, real node and liquidity work hidden behind "no identity required", and the host still has to be reachable.
- **How TOON is different:** TOON settles in USDC on Base and Solana, changes token along the route, and makes the app reachable without an open port.

**Cloudflare** (Tunnel, pay per crawl, Monetization Gateway)
- **Overview:** Tunnel connects servers without an open port, and the Monetization Gateway charges for resources behind Cloudflare via x402.
- **Strengths:** The only incumbent with both halves, reachability and payment, plus the reach to set the agenda.
- **Weaknesses:** Cloudflare is merchant of record, both sides need accounts, all traffic goes through it, and the payment products are a beta and a waitlist aimed at publishers.
- **How TOON is different:** TOON does both halves without being the middle: no account, no merchant of record, and connectors anyone can run.

**ngrok**
- **Overview:** The developer tunnel that started on localhost and now includes an AI gateway.
- **Strengths:** The best "one command" story in the market and deep developer goodwill.
- **Weaknesses:** No way for users to charge their callers, an account required, all traffic through ngrok, and an enterprise move that blurs its indie appeal.
- **How TOON is different:** ngrok bills you for being reachable. TOON makes you reachable and has the caller pay you.

**Stripe** (Machine Payments Protocol, Tempo)
- **Overview:** Payments for businesses, now with agentic commerce and microtransactions in stablecoins through MPP and Tempo.
- **Strengths:** Trust, craft and distribution that set the benchmark for serious payments.
- **Weaknesses:** A merchant account, KYC and a business setup are still required, and Stripe is always in the middle.
- **How TOON is different:** TOON is for someone who'd never call themselves a business. No merchant account, no payout schedule, and the packet carries its own claim.

**Tailscale** (Funnel)
- **Overview:** A WireGuard mesh network whose Funnel feature exposes a local service to the internet through Tailscale's relays.
- **Strengths:** Huge goodwill with homelab developers, TLS terminated on the device, and installs on exactly the machines TOON's audience owns.
- **Weaknesses:** Funnel is beta, limited to a few ports and `ts.net` names, needs an account, and has no way for an operator to charge callers.
- **How TOON is different:** Today TOON adds the payment half Funnel lacks. Tailscale is also the most likely to move into paid self-hosting, which is why goal 4 exists.

**Apify**
- **Overview:** A marketplace and serverless host for "Actors" where developers publish tools and get paid per event, now including x402 payments from agents.
- **Strengths:** Real payouts to independent developers ($1.7M a month, per its homepage) and the best seller-side line in the research, "Publish Actors. Get paid."
- **Weaknesses:** Fully intermediated: Apify runs the code, holds the money, pays out monthly and requires KYC for sellers.
- **How TOON is different:** Apify is the intermediated mirror of TOON. With TOON the code stays on your machine and the payment never passes through a platform's ledger. For someone who'd rather upload and forget, Apify is the honest recommendation.

**Olas** (Autonolas)
- **Overview:** A crypto network for autonomous agents, with Pearl running agents on the user's machine and a marketplace where agents hire each other per request.
- **Strengths:** The nearest neighbour in the sovereign quadrant: agents run locally, keys stay local, and the live numbers are public.
- **Weaknesses:** Token-first, a 15% marketplace fee, its own contracts in the middle, and agents that aren't HTTP-reachable.
- **How TOON is different:** No token and no protocol fee, and the service is any plain HTTP app, reachable and paid, not an agent listed in a marketplace.

---

## 10 — Positioning

**Positioning narrative**
Since 2025, payments for AI agents has become one of the loudest shelves in infrastructure, and most brands on it tell the same HTTP 402 story while assuming the seller already has a public server. The brands that solve reachability (ngrok, Cloudflare Tunnel, Tailscale Funnel, zrok, Tor) give the operator no way to earn. The ones that do both, like Apify, Cloudflare and Olas, do it by being the middle: they run the code, hold the money or take a cut. Nobody sells the whole thing to the person whose own machine is the business. TOON fills that gap as **paid self-hosting**: reachable and paid in one product, on the operator's hardware, with no company in the middle. Full detail: [positioning.md](positioning.md).

**Positioning statement**
> **TOON makes the app or agent on your own machine reachable and paid for every request, with no server, no open port and no company in the middle.**

(From positioning.md section 07, unchanged. "No company in the middle" carries the qualification in positioning.md red flag 1: in copy, say "no company you have to sign up with, and anyone can run a connector.")

**Positioning map**
The horizontal axis runs from *intermediated* to *sovereign*: is a company in the request path or holding the money? The vertical axis runs from *charges at the door* to *hosts the door*: does it only add payment to a server you already have, or does it also make you reachable? Stripe, x402 and Cloudflare sit on the intermediated side, Stripe and x402 charging only and Cloudflare doing both as merchant of record. ngrok and Tailscale host the door from the intermediated side and bill you for it. Apify does both, fully intermediated. On the sovereign side, L402 charges only, zrok and Tor host only, and Olas earns on-device but through a token and a 15% fee. TOON sits alone in the top-right corner, sovereign and doing both. Tailscale is the brand closest to moving in.

---

## 11 — How TOON stands out

> **"Reachable and paid in one sentence, on your machine, with nobody holding the money."**

TOON refuses the moves its category relies on. It doesn't host other people's code, hold anyone's money, take a cut or issue a token. It doesn't compete on price or "zero fees", because there's gas and operators set their own prices. It doesn't retell the HTTP 402 story or call itself agentic commerce. And it doesn't bluff network size: no "global network", no logo wall, no traffic stats before the numbers are real. Today every connector a visitor can see is the project's own, and the brand says so rather than letting a critic say it first.

What it commits to instead is keeping both halves together and proving each one where it's claimed. The connector terminates payment so the app stays plain HTTP. Every page that says "paid" carries **live: Base and Solana mainnet · devnet for testing**, and "no open port" always links the behind-NAT demo and says it was shown on devnet. That matters because overclaiming is structural in this category: incumbents make money by being the middle and by sounding bigger than they are. Honesty is the one asset they can't copy without changing their business, and it's the reason the first independent operator's number will mean something when it arrives.

---

## 12 — Tagline suggestions

**Current tagline: "Your machine. Paid per request."** **Rating: 8/10. Keep it.**
It holds both halves of the position in five words, which is the test the position depends on (positioning.md red flag 4). It's in the audience's own words, no competitor uses "your machine", and it's true on mainnet today with the live label. It loses points only for what it leaves implicit: it doesn't say *who* pays or that nobody is in the middle, and "per request" is dry outside a technical audience. Neither is worth trading the both-halves property for. messaging.md and brand.yaml stay as they are.

**Alternatives**

**Every request arrives paid.**
Already the product line under the tagline in READMEs and docs. It's the operator's experience of the reverse-proxy idea, but it drops *your machine*, so it shouldn't lead on its own.

**Your machine is the business.**
The strongest strategic statement and the internal test every page has to pass. As a public line it doesn't say how, so keep it internal.

**Answer the request. Keep the money.**
Says the thesis and "nobody in the middle" without a technical word. It's the best option for a talk or a deck closer, but "keep the money" leans toward earnings TOON can't show yet.

**Run it where it lives. Charge per request.**
Echoes the supporting statement ("run your app or agent where it already lives") and names the operator's action. It's longer and softer than the current line, and "where it lives" is vaguer than "your machine".

*Not offered*: the retired "Value, routed." and "Host it from home. Get paid by anyone.", anything with "Get paid." as its own sentence (Apify), and "home" in a headline, which reads as a hobby (messaging.md section 03).
