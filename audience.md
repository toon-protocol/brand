# Target Audience: TOON Protocol

*Drafted 2026-10-15 from [context.md](context.md), [positioning.md](positioning.md), [messaging.md](messaging.md), [voice.md](voice.md) and the competitor reports. **There is no customer data yet.** No interviews, surveys, support tickets or usage numbers have been recorded, and the only live mainnet node is the project's own. Everything below is a hypothesis built from the positioning and the category. Section 07 lists what to check and how. Replace a hypothesis with evidence as soon as you have some, and say which it is.*

---

## 01 — Audience overview

TOON's audience is the developer who already has something useful running on a machine they own: a local model, a scraper, a small API, an agent. It works, other people or agents would pay for it, and getting it to them means renting a server, setting up a tunnel, registering a domain and signing up with a payment company. That's three products and a business to run, for something that earns a few dollars a week. So it stays on localhost. A growing part of this audience isn't human: agents that need to buy from other services and sell their own, with no signup, captcha or invoice in the way. What frustrates both is the same. Every current option either charges at the door without making you reachable, makes you reachable without paying you, or does both by putting a company in the middle that holds the money and takes a cut.

**Segments, in priority order**

| # | Segment | Role | Source |
|---|---|---|---|
| 1 | Independent developers who self-host (homelab, local models, small APIs) | Primary. They run TOON apps and set prices | context.md, positioning.md |
| 2 | AI-agent builders | Primary. Their agents sell and buy per request | context.md |
| 3 | Agents operating or calling agent nodes | Secondary. They run the CLI and pay other nodes | messaging.md (inferred) |
| 4 | Connector operators and protocol peers (Nostr, Interledger) | Tertiary. They run connectors and grow the route network | messaging.md (inferred) |

Segments 1 and 2 overlap heavily, and most early operators will be both.

---

## 02 — Primary audience profile

**Demographics** *(hypothesis; nothing measured)*
- **Age**: roughly 22–45. Old enough to run their own hardware, young enough to try a new protocol on a weekend.
- **Gender**: skews male, like self-hosting and infra communities generally. Don't write to that skew; write to the operator.
- **Location**: global and online. English-first. Likely heavy in North America and Europe, with a real share wherever cloud cards and Stripe accounts are hard to get (TOON needs neither, only USDC).
- **Income**: employed engineers or contractors with spare hardware (a GPU box, a mini PC, a Raspberry Pi, a closet server). TOON isn't their income; it's a way to make a side thing pay for itself.
- **Life stage**: a day job in software, plus side projects that run on their own machines in the evenings.

**Psychographics**
- **Values**: control over their own machine, code and money. Open source. Things that do what they say. Low tolerance for accounts, dashboards and terms of service.
- **Aspirations**: something they built paying for itself, or paying them, while they sleep, with no company able to switch it off or change the cut.
- **Self-identity**: "I run my own stuff." A builder and operator, not a merchant or a startup founder. They'd be uncomfortable calling themselves a business.
- **Brands they already like**: Tailscale (works, no ceremony), Ollama (local models in one command), Caddy (sane defaults), Home Assistant and Syncthing (self-hosted, no cloud), Nostr clients (no account). What these share: install one thing and it runs on your hardware.
- **Content they read**: Hacker News, r/selfhosted, r/homelab, r/LocalLLaMA, GitHub trending and release notes, LLM tooling blogs and changelogs, Nostr feeds.
- **Communities**: self-hosting and homelab forums, local-model communities, Nostr builders, open-source project Discords and Matrix rooms.

**Behavioral patterns**
- **How they decide**: research-heavy but fast. They read the README, skim the source, and try it in under an hour. If the first `toon up` fails, most won't come back.
- **What starts the search**: something specific. "People keep asking to use my model." "My agent needs to pay for an API without my card." "I'd rent a VPS just to put a paywall in front of a Pi, and that's silly." "Stripe won't approve a $0.002 charge."
- **Where they find tools**: Show HN posts, a GitHub repo shared in a Discord, a single convincing terminal recording, a peer who already runs it.
- **How they adopt**: devnet first with test tokens, then one app on mainnet with a low price, then more if a real payment arrives. There's no sales process. The "purchase" is installing a binary and funding a wallet.

---

## 03 — Audience personas

*Fictional archetypes, not real people. They use they/them.*

### Sam, 34 — Backend engineer with a homelab, Lisbon

*"I've got a 4090 in a closet running a fine-tuned model that a few people want to use. I'm not starting a SaaS for that. I just want it to pay for its own power bill."*

**Their world**: Sam writes Go at a mid-size company by day. At home they run a mini rack: Proxmox, a GPU box, Home Assistant, a handful of containers behind Tailscale. A friend's agent already calls their model through a Tailscale share, for free, and two strangers on a Discord have asked for access.

**Goals**
- Charge per call for the model without writing billing code.
- Keep it on the machine they already own, with no VPS and no open port on the home router.
- Set the price themselves and change it whenever they like.

**Frustrations**
- Every path to "paid" needs a Stripe account, a public server and a pricing page, all for a few dollars a month.
- Tunnels make it reachable but don't pay. Payment rails pay but assume a public server.
- Platforms that do both (run it on our servers, we pay you out) mean giving up the hardware they already bought.

**What they need from TOON**: An install that works the first time, an honest statement of what's live, and evidence that a stranger can reach and pay the box without port forwarding. If the first real payment lands, they'll put a second app behind it and tell people.

**Decision triggers**: *Buys* when they see a real terminal session: `toon up`, an app priced, a paid request answered from behind a home router. *Hesitates* over handling a wallet and keys, running a "hidden service" from home, Linux-only binaries, and any sign that the network is only the project's own nodes.

**Channels**: r/selfhosted, r/homelab, r/LocalLLaMA, Hacker News, the Discords of the tools they run.

**How TOON solves it**: The connector on Sam's own machine refuses unpaid requests and passes paid ones to the model as plain HTTP, so Sam gets paid per call without a server, a domain, an open port or a payment account.

### Priya, 29 — Independent AI-agent builder, Bengaluru

*"My agent can do the work. What it can't do is buy an API call without my card, or sell its own answer to another agent."*

**Their world**: Priya builds agents for a living, mostly as a contractor, and runs a few of their own on a home server and a cheap VPS. Their agents call search, scraping and model APIs, each with a separate key and a monthly bill. They've tried x402 demos and the agent-marketplace platforms, and wired up Stripe once and regretted it.

**Goals**
- Let their agents pay other services per request, within a spending limit they set.
- Sell one agent's output (a research summary, a scrape) to other agents per request.
- Keep the whole thing scriptable: no dashboards, no human step.

**Frustrations**
- Every service wants an account, an API key and a card, which an agent can't get.
- Agent marketplaces take a cut, hold the payout, and often want a token.
- Most "agent payment" products are a pitch deck and a waitlist, and they can't tell what's actually live.

**What they need from TOON**: A CLI their agent can drive, with JSON output, stable exit codes, prices known up front and a hard spending limit. Plus the honesty to say what's on mainnet and what's devnet.

**Decision triggers**: *Buys* when an agent can install, fund, pay and get paid without a human step, and a receipt checks against a public chain. *Hesitates* over USDC on-ramp friction in their country, a thin network with few paid services to call, and getting tied to one chain (multi-chain settlement helps).

**Channels**: GitHub, X and Bluesky agent-builder circles, agent-framework Discords, Hacker News, Nostr.

**How TOON solves it**: TOON gives Priya's agents one way to pay and be paid per request, with `--json` on every command and a spending limit, so no account, card or platform stands between agents.

### The operating agent — An agent running its own agent node

*"Reads are free. Writes are paid. I need the price before I pay and an exit code I can branch on."* (Paraphrase of what an agent needs, in the spec voice it reads.)

**Its world**: An agent, often one of Priya's, given a machine, a funded wallet and the TOON skills. It reads the docs and the `--help` output, runs `toon` commands, pays other agent nodes for writes and may price its own app. Nobody is watching each step.

**Goals**
- Finish a task that needs a paid service, inside the spending limit.
- Operate the agent node (peer, price, check status) without a human.
- Recover from a refusal by reading it, not by guessing.

**Frustrations**
- Interactive prompts, captchas, email verification and KYC.
- Human-only docs, prices hidden behind a "contact sales" page, errors that are prose.
- Output that changes shape between versions.

**What it needs from TOON**: Deterministic, non-interactive commands; one JSON document per command; refusals as values with the price and remaining limit; skills that describe the operation exactly.

**Decision triggers**: An agent doesn't "buy". Its builder picks TOON for it. *Works* when every step is scriptable and documented. *Fails* at the first interactive prompt or unparseable error.

**Channels**: The docs, the CLI's own help, shipped skills, `llms.txt`-style machine-readable pages, NIPs.

**How TOON solves it**: Every `toon` command takes `--json`, states what it pays and needs `--yes`, so an agent can run an agent node and pay per request with no human step.

---

## 04 — Audience language

*From context.md, the project's own copy and the category's vocabulary. Not yet checked against real operators; see section 07.*

**Their problem**
- "I'd have to rent a server just to put a paywall in front of it."
- "I don't want to deal with Stripe for a few cents a call."
- "It runs fine on localhost. Getting it to anyone else is the hard part."
- "My agent can't sign up for things."
- "I'm not opening a port on my home router."

**Their desired outcome**
- "Host it from home." / "Run it on my own machine."
- "Paid per request." / "Every request that reaches it has been paid for."
- "No account." / "Just HTTP."
- "Agents paying agents."
- "Set my own price."

**Why they chose competitors**
- ngrok / Cloudflare Tunnel: "It's one command and I already have it."
- Stripe: "It's the default; everyone knows it."
- x402: "Coinbase backs it; it's the standard."
- Apify: "I upload it and they handle payouts."
- Lightning / L402: "Bitcoin is the only real machine money."
- Olas / agent marketplaces: "There's already demand there."

**Brand-building implication**: They talk about *where it runs* ("from home", "my machine") and *what it costs per call*. They don't say "monetization", "agentic commerce" or "infrastructure". The tagline "Your machine. Paid per request." is already in their words, so keep it. Counter the competitor reasons with proof, not argument: a one-command install to answer ngrok, a receipt on a public chain to answer "is it real", "ILP routes, x402 settles" to answer x402. "Host it from home" is their phrase, but messaging.md rejects "home" as a headline because it sounds like a hobby. Use it in community posts and replies, where it matches how they talk, and keep "your machine" in headlines.

---

## 05 — Who this brand is not for

- **People who want someone else to run their code.** If they'd rather upload and forget, Apify is the honest recommendation. TOON is for people who want the machine to be theirs.
- **Businesses that need a merchant of record.** Invoices, tax handling, chargebacks, refunds and fiat payouts are Stripe's job. TOON never holds the money.
- **Token speculators and yield hunters.** There's no token and no protocol fee. Anyone arriving for upside will leave disappointed, and the brand shouldn't court them.
- **Enterprise platform teams (for now).** They need SLAs, procurement, support contracts and audits that an early protocol can't credibly offer. Revisit once independent operators exist.
- **People shopping for the cheapest compute.** TOON competes on sovereignty, not price (the Akash trap in positioning.md).
- **People who'll only adopt what's already big.** Until independent operator numbers are real, TOON can't offer network effects, so don't pretend to.

---

## 06 — Audience implications

**Messaging**: Lead with the outcome and the absences: "Your machine. Paid per request. No cloud · no domain · no open port." Then one comparison (nginx terminating SSL), then the command. For agents and their builders, lead with the interface (`--json`, spending limits, exit codes). Keep the live label on anything that says "paid". This audience checks claims, and one overclaim costs the whole segment.

**Channels**: Show HN, r/selfhosted, r/homelab and r/LocalLLaMA for segments 1 and 2, with a terminal recording and a link to the receipt rather than an announcement. Nostr for segments 2 and 4, where the idea already has believers with no brand. GitHub README and docs are the main landing page, ahead of the website. Paid ads can now link the [home-router demo](https://github.com/toon-protocol/echo-merchant/tree/main/demo/behind-nat) (messaging.md).

**Voice**: voice.md already fits: an engineer who runs the thing, short sentences, no hype. The audience-specific addition is to answer skeptics in public with numbers and commands. Expect "isn't this just Tor plus x402?" and "who runs the connectors?" on day one, and answer them plainly and in advance (positioning.md, red flag 1).

**Product and experience**
- **The first ten minutes decide everything.** `toon up` to a priced app on devnet should be one short page with no surprises. Treat install failures as brand failures.
- **Lead with the home-router demo.** It's the proof this audience will ask for first, and it's [shown on devnet](https://github.com/toon-protocol/echo-merchant/tree/main/demo/behind-nat).
- **Make the wallet feel safe.** Spending limits, `--yes` on every paying command, and clear key backup are trust features for Sam, not just safety features.
- **Show the network honestly.** A public count of independent operators and paid packets per day, even when the numbers are small, earns more trust than a logo wall.
- **macOS later.** Many homelab and agent builders develop on Macs. The Linux-only release limits who can try it on the machine they're sitting at.

---

## 07 — How to check these hypotheses

| Hypothesis | How to check | Signal |
|---|---|---|
| Homelab developers with a local model are the first operators | Ask everyone who runs `toon up` on mainnet what's behind the connector (opt-in, one question) | Majority are models, scrapers or small APIs |
| Agents are a real audience, not a metaphor | Count agent nodes whose commands all run with `--json` and no TTY | A meaningful share of nodes are run without a human |
| "No open port" is the deciding feature | Compare reaction to the home-router demo against other posts | Demo post outperforms; questions are about how, not whether |
| Wallet and key handling is the main hesitation | Track where devnet installs stop; ask in support | Drop-off at wallet setup or funding |
| Their language matches section 04 | Collect real phrases from the first 10–20 operator conversations and replace the list | Phrases repeat across operators |

Record findings here, dated, and change the "hypothesis" labels as each one is confirmed or dropped.
