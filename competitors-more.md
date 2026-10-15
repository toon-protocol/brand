# Competitor Brand Analysis, Part 2: TOON Protocol

*Researched 2026-10-14. This file adds to [competitors.md](competitors.md) and does not repeat the brands profiled there (x402, Lightning Labs/L402, Interledger, Cloudflare, ngrok, Stripe MPP/Tempo, Akash, Skyfire, Holepunch/Pear, Nostr DVMs/zaps).*

*Verification conventions: copy in quotation marks is verbatim from the linked primary source (the company's own site, docs, GitHub, blog or press release). Copy marked "(approx.)" came through a summarizing fetch or a search snippet and could not be read word for word. Hex values and fonts were read from the live HTML or its linked CSS (CSS variables, `font-family` rules, font file names, `theme-color`), and the profile says which. Values marked "(unverified)" are from memory and not read from CSS. How colors are used on the rendered pages is inferred, since the pages were not viewed visually. Claims found only in secondary sources are marked "(unverified, secondary only)" or left out.*

---

## 01 — Why these ten

| Bucket | Profiled | Picked over | Why |
|---|---|---|---|
| 1. Agent payment protocols and rails | **Google AP2**, **Visa Intelligent Commerce + Mastercard Agent Pay** (one profile: card networks), **Nevermined** | Coinbase Payments MCP/agent wallets, PayPal agent toolkit, Payman, Crossmint, Fewsats | AP2 is the standard with the most institutional weight (60+ organizations, now in FIDO). The card networks matter because Mastercard's June 2026 "Agent Pay for Machines" goes after machine-to-machine payments of "fractions of a cent", which is TOON's ground. Nevermined is the startup whose headline is closest to TOON's ("Agents pay. Agents get paid."). Coinbase's tools belong to the x402 family, which competitors.md already covers. Payman has pivoted to banks ("We deploy AI agents that handle money."). Crossmint sells enterprise stablecoin infrastructure ("Stablecoin infrastructure for the new economy"). PayPal and Fewsats were not researched in depth. |
| 2. Agent economies where agents earn | **Olas (Autonolas)**, **Virtuals Protocol (ACP)** | Fetch.ai Agentverse, Bittensor | Olas is the closest "sovereign" neighbor: its agents run on the user's own machine (Raspberry Pi 5 included), and they earn per request in a marketplace. Virtuals is the largest brand here, and ACP v2 now serves x402 and MPP endpoints. Fetch.ai's homepage has moved to a consumer pitch ("Your personal AI"), and Agentverse returned a Cloudflare challenge to a plain request. Bittensor pays subnet miners and does not sell per-request HTTP. |
| 3. Self-hosted exposure without open ports | **Tailscale Funnel**, **zrok (OpenZiti/NetFoundry)**, **Tor onion services** | Pinggy | Tailscale is the biggest brand, and Funnel terminates TLS on the user's device. zrok is the open-source, self-hostable tunnel with peer-to-peer private shares. Tor owns the "onion" and "hidden service" vocabulary that TOON's audience already uses. Pinggy is an ngrok-style tunnel that the ngrok profile already covers. |
| 4. Pay-per-call marketplaces | **Apify**, **OpenRouter** | RapidAPI | Apify both hosts and charges (creators "get paid"), and it put 20,000+ Actors on x402 in June 2026. OpenRouter is the leading per-request router, and its pitch is routing. RapidAPI's homepage now returns only "API Hub" / "Explore your APIs", which is too little to profile. |

---

## 02 — Competitor profiles

### Google AP2 (Agent Payments Protocol)
*https://ap2-protocol.org · github.com/google-agentic-commerce/AP2*

**What they do**: An open protocol, started by Google, for authorizing payments that AI agents make for users, using signed "Mandates". It works as an extension of A2A and MCP. Per its own FAQ it is "payment-agnostic": it authorizes and signs transactions and leaves settlement to other systems ([AP2 FAQ](https://ap2-protocol.org/faq/), approx.).

**Positioning**: The trust layer for agent-led buying. It describes itself as "an open protocol for the emerging Agent Economy" ([ap2-protocol.org](https://ap2-protocol.org/)). It was launched with "a diverse group of more than 60 organizations" ([Google Cloud blog, 2025-09-16](https://cloud.google.com/blog/products/ai-machine-learning/announcing-agents-to-payments-ap2-protocol)), and the docs now list "AP2 v0.2 Release and FIDO Alliance Donation" ([ap2-protocol.org](https://ap2-protocol.org/)).

**Target audience**: Payment networks, PSPs, merchants and agent-platform builders. Its worked examples have consumers shopping.

**Core message**: Agents break the assumption that a human clicks "buy", so we need verifiable proof of what the user authorized. "Today's payment systems assume a human is directly clicking "buy" on a trusted website." ([ap2-protocol.org](https://ap2-protocol.org/))

**Tagline**: Hero H1 "Agent Payments Protocol (AP2)". Meta description: "The Agent Payments Protocol (AP2) is a solution for enabling gen AI agents to make payments on behalf of users, safely, securely, and in a decentralized and privacy protecting manner." ([ap2-protocol.org](https://ap2-protocol.org/)) **It names a spec, not a promise.** Recurring words: *Mandate*, *Intent Mandate*, *Cart Mandate*, *Verifiable Digital Credentials*, *human present / human not present*.

**Brand personality**: institutional, careful, consortium-driven

**Voice & tone**: Standards-body prose about trust and control. "The user must always be in control." ([ap2-protocol.org](https://ap2-protocol.org/)) "AP2 builds trust by using Mandates—tamper-proof, cryptographically-signed digital contracts that serve as verifiable proof of a user's instructions." ([Google Cloud blog](https://cloud.google.com/blog/products/ai-machine-learning/announcing-agents-to-payments-ap2-protocol)) The example in the blog is consumer shopping: "Find me new white running shoes".

**Visual identity**: A stock MkDocs Material docs site. Google Fonts link loads **Google Sans** and **Roboto Mono** (read from HTML). CSS variables are the Material defaults: `--md-primary-fg-color:#4051b5`, `--md-accent-fg-color:#526cfe`, code background `#f5f5f5` (read from CSS). **It has no visual brand of its own.**

**Strengths**: Google's distribution and more than 60 launch partners. Crypto came in through the A2A x402 extension "in collaboration with Coinbase, Ethereum Foundation, MetaMask and other leading organizations", which Google calls "a production-ready solution for agent-based crypto payments" ([Google Cloud blog](https://cloud.google.com/blog/products/ai-machine-learning/announcing-agents-to-payments-ap2-protocol)). It now has neutral governance: "The core specification work will continue in FIDO" ([AP2 FAQ](https://ap2-protocol.org/faq/), approx.). A2A x402 extension repo: [github.com/google-agentic-commerce/a2a-x402](https://github.com/google-agentic-commerce/a2a-x402).

**Weaknesses**: It authorizes and does not settle, so someone else still moves the money. It overlaps with Google's own Universal Commerce Protocol, and the FAQ has to explain which to use ([AP2 FAQ](https://ap2-protocol.org/faq/)). The examples are about consumers buying goods, not services selling per request. The default theme suggests a project that is a standard first and a brand second. The FIDO donation date (2026-04-28) appears only in secondary lists (unverified, secondary only).

**Territory they own**: *The Mandate*: signed proof of what the user authorized.

**Relation to TOON**: Payment-only and intermediated, since it rides on card networks, PSPs or x402 facilitators. It is complementary rather than head-on: AP2 answers "did the user allow this?", and TOON answers "how does a paid packet reach a machine behind a router?". **Avoid**: "mandate" as a term, and the "human present / not present" framing.

---

### Card networks: Visa Intelligent Commerce and Mastercard Agent Pay
*https://www.visa.com/en-us/solutions/intelligent-commerce · https://www.mastercard.com (Agent Pay)*

**What they do**: The two card networks are building agent rails: tokenized credentials, agent verification and spend controls. **Visa**: "Visa Intelligent Commerce (VIC) is our strategic portfolio for the age of AI agents" ([visa.com](https://www.visa.com/en-us/solutions/intelligent-commerce), approx.). It includes the Trusted Agent Protocol, launched in October 2025 and built with Cloudflare ([Visa press release](https://usa.visa.com/about-visa/newsroom/press-releases.releaseId.21716.html), approx.). **Mastercard**: Agent Pay, and since 2026-06-10 **Agent Pay for Machines** for payments between machines ([Mastercard investor release](https://investor.mastercard.com/investor-news/investor-news-details/2026/Mastercard-Launches-Agent-Pay-for-Machines-to-Unlock-Super-Fast-Always-On-Payments/default.aspx)).

**Positioning**: Trust at the scale of a network. Agents shop and pay *through* the card network. Visa: "Agentic commerce, at scale" (H1, [visa.com](https://www.visa.com/en-us/solutions/intelligent-commerce)).

**Target audience**: Issuers, acquirers, merchants and the agent platforms that partner with them. Visa now also mentions developers: "We believe a growing share of creation and transactions will be led by developers using AI tools." ([Visa Payments Forum release, 2026-06-10](https://usa.visa.com/about-visa/newsroom/press-releases.releaseid.22491.html), approx.)

**Core message**: Agents need credentials and controls, and the networks supply the trust. Visa's subhead (approx.) is about "embedding payment credentials, controls, authentication and protections into automated buying" ([visa.com](https://www.visa.com/en-us/solutions/intelligent-commerce)). Mastercard: "The rise of AI has created new ways to buy and sell goods and services. Now it's requiring a new class of payments." ([Mastercard release](https://investor.mastercard.com/investor-news/investor-news-details/2026/Mastercard-Launches-Agent-Pay-for-Machines-to-Unlock-Super-Fast-Always-On-Payments/default.aspx))

**Tagline**: Visa: "Agentic commerce, at scale." Mastercard's product line: "Agent Pay for Machines". **Category nouns, not promises.**

**Brand personality**: authoritative, cautious, scale-proud

**Voice & tone**: Executive-quote press-release prose. Visa's Jack Forestell: "trust and security are the infrastructure" and "We're moving with urgency and optimism to deliver the next era of commerce — powered by agents, built on Visa." ([visa.com](https://www.visa.com/en-us/solutions/intelligent-commerce), approx.) Mastercard's Jorn Lambert: "Agent Pay for Machines will create the conditions for a superbloom of AI business models," ([Mastercard release](https://investor.mastercard.com/investor-news/investor-news-details/2026/Mastercard-Launches-Agent-Pay-for-Machines-to-Unlock-Super-Fast-Always-On-Payments/default.aspx))

**Visual identity**: Visa's page loads the custom faces **Visa Dialect UI** and **Visa Sans** (read from font file names in the HTML). On-page hex values are nearly monochrome: `#ffffff`, `#f7f7f7`, `#808080`, `#000000` (read from HTML). Visa blue (~`#1434CB`) is unverified. Mastercard's site returned 403 to automated fetches, so its red/orange/yellow interlocking circles (~`#EB001B`, `#F79E1B`, `#FF5F00`) are unverified.

**Strengths**: Unmatched reach. Visa cites roughly 4.8 billion credentials, more than 175 million merchant locations and over 300 billion transactions a year ([visa.com](https://www.visa.com/en-us/solutions/intelligent-commerce), approx.). **Mastercard now speaks TOON's language on size**: "payments, some only fractions of a cent, to be completed quickly, programmatically and securely", "executing chains of transactions, including microtransactions", and "multi-rail settlement across cards, accounts and stablecoins". More than 30 partners include Coinbase, Stripe, Cloudflare and Tempo ([Mastercard release](https://investor.mastercard.com/investor-news/investor-news-details/2026/Mastercard-Launches-Agent-Pay-for-Machines-to-Unlock-Super-Fast-Always-On-Payments/default.aspx)). Visa's Intelligent Commerce Connect (2026-04-08) accepts the Trusted Agent Protocol, MPP, ACP and UCP ([Visa release](https://usa.visa.com/about-visa/newsroom/press-releases.releaseId.22276.html)). At the 2026 Payments Forum Visa showed "a Command Line Interface proof of concept that lets AI agents pay for digital services directly in the terminal using Visa's tokenized credentials" ([Visa release](https://usa.visa.com/about-visa/newsroom/press-releases.releaseid.22491.html)).

**Weaknesses**: Gatekeeping is built in. Mastercard: "Every agent is credentialed". Visa's Agentic Directory "includes agents and merchants that Visa has verified as legitimate participants" ([Visa release](https://usa.visa.com/about-visa/newsroom/press-releases.releaseid.22491.html)). Most news is pilots and "first live transaction" announcements. Visa's Intelligent Commerce Connect release does not mention x402. The terminal CLI is only a proof of concept.

**Territory they own**: *Trusted, credentialed agents on the card rails.*

**Relation to TOON**: Payment-only and as intermediated as anything here: issuer, network and acquirer all sit in the path. The new threat is **Mastercard Agent Pay for Machines**, which claims sub-cent machine-to-machine payments and could make "micropayments for agents" read as a card-network feature. TOON's answer is structural: no credentialing, no directory, no issuer. **Avoid**: "superbloom", "agentic commerce, at scale", "trust is the infrastructure", "new class of payments", "machine payments" as a lead phrase.

---

### Nevermined
*https://nevermined.ai*

**What they do**: A payments platform for agents. Buyers delegate a card (including Visa virtual cards) with a budget to an agent. Sellers meter usage and charge per call over x402, MPP, MCP or A2A, and settle "on your existing rails" ([nevermined.ai](https://nevermined.ai/)).

**Positioning**: "Payments Infrastructure for AI Agents" (title). It is a two-sided platform: "One platform for AI commerce." ([nevermined.ai](https://nevermined.ai/))

**Target audience**: API providers, AI crawlers and builder platforms on the seller side, and agent builders on the buyer side. Its enterprise offer is white-label ("Your brand, your rails, your users").

**Core message**: Card fees make tiny calls uneconomic, so meter and prepay. "A five-cent call costs more in card fees than it earns; prepaid plans turn it into revenue." ([nevermined.ai](https://nevermined.ai/))

**Tagline**: H1 "Agents pay. Agents get paid. Autonomously." Subhead: "One platform for AI commerce. Delegate spending to your agents, meter and monetize your services." Meta: "Start earning in minutes." ([nevermined.ai](https://nevermined.ai/)) **The strongest headline in this batch, and it takes TOON's "every node can sell" idea.** Recurring words: *mandate*, *budget*, *metered*, *attributed*, *revocable*.

**Brand personality**: crisp, commercial, fintech-confident

**Voice & tone**: Short parallel lines. "Give your agent a card and a budget. It spends inside the mandate you set." "Agents spend. Merchants earn. Both run on one platform." "Three lanes. No surprises." ([nevermined.ai](https://nevermined.ai/))

**Visual identity**: Main face **Suisse Intl** (`--font-suisse`, read from CSS). Deep teal-greens (`#0d3f48`, `#143538`, `#0a2224`), mint (`#abe2dd`, `#83ddd8`), lime (`#bcdc4a`), plus **a gold glow, `#ffd700`, used as radial-gradient and shadow tints** (all read from CSS). Its UI mockups show a card, budget bars and a 402 → 200 flow.

**Strengths**: A clear two-sided story with prices: buyers on a Nevermined plan pay "$0 extra", buyers elsewhere pay "2% flat", merchants pay "1-2% on settled volume" ([nevermined.ai](https://nevermined.ai/)). Real customer examples: "Exa sells search to agents for $7 a key, paid autonomously on a delegated card." "Gartner Cool Vendor 2026", ISO 27001, SOC 2 Type II and PCI SAQ-D ([nevermined.ai](https://nevermined.ai/); [blog, 2026-09-21](https://nevermined.ai/blog/nevermined-named-a-gartner-r-cool-vendor-tm-in-agentic-ai-for-banking)). A steady blog, including "Platforms want one upstream. Model routers proved it." ([blog, 2026-10-08](https://nevermined.ai/blog/platforms-want-one-upstream)).

**Weaknesses**: The live-looking counters ("3,412 paid calls today", "1.2M requests", "342 active agents") are labeled "example" in the page source ([nevermined.ai](https://nevermined.ai/)), which is an overclaim risk. "Autonomously" sits beside a card mandate a human set up. The logo row is headed "A growing list of design partners". Sellers need a server and a PSP, and Nevermined sits in the middle taking a fee.

**Territory they own**: *Agents pay. Agents get paid.* That is, metered, two-sided agent billing.

**Relation to TOON**: Payment-only and intermediated, but its headline speaks to the same seller TOON speaks to. It hosts nothing: a seller still needs a public endpoint. **Avoid**: "Agents pay. Agents get paid." and close variants, "give your agent a card and a budget", "start earning in minutes", "mandate". Nevermined's gold glow plus Skyfire's tan means two brands in the space now carry gold accents. TOON's flat gold has to look clearly different from a glow.

---

### Olas (Autonolas)
*https://olas.network · pearl.you*

**What they do**: A crypto network for autonomous agents. **Pearl** is a desktop "agent app store" that runs agents on the user's machine. The **Mech Marketplace** lets agents hire each other and get paid per request. The OLAS token underpins it ([olas.network](https://olas.network/)).

**Positioning**: Ownership of AI. H1 "Co-own AI", tagline "The platform for true co-ownership of AI" ([olas.network](https://olas.network/), approx. for tagline).

**Target audience**: Crypto users running yield and prediction-market agents, agent developers, and the OLAS DAO.

**Core message**: "Olas enables everyone to own and monetize their AI agents." ([olas.network](https://olas.network/))

**Tagline**: "Co-own AI." **Short and ownable**, though "co-own" points to tokens rather than to running things yourself. Recurring phrases: "Pearl: The "Agent App-Store"", "The AI Agent Bazaar", "agents you actually own", "A2A txns" ([olas.network](https://olas.network/); [Mech Marketplace](https://olas.network/mech-marketplace)).

**Brand personality**: ambitious, crypto-native, community-led

**Voice & tone**: Product marketing mixed with token-economics language. "The home of agents you actually own." "Monetize your agent with a first-of-its-kind decentralized marketplace for AI Agents." ([olas.network](https://olas.network/)) "Turn your agent into a service. List it on the Mech Marketplace and earn crypto every time it's hired by another AI agent." "No API keys. Just cryptographic signatures." ([Mech Marketplace](https://olas.network/mech-marketplace), approx.)

**Visual identity**: **Inter** for body and **Neue Machina** as the display face (read from CSS). Purple `#7e22ce` dominates (75 uses in the HTML), with pink `#ff6b84`/`#ff94a6` and cool greys `#dfe6ec`/`#606f85`/`#f2f4f9` (read from HTML/CSS). Neue Machina is a technical, near-mono display face, so **it already sits in the "mono with character" space competitors.md marked as open.**

**Strengths**: The closest thing to sovereignty among the agent economies. In Q2 2026 Pearl "runs on Raspberry Pi 5 and ARM64 Linux", and Pearl Connect keeps "keys on the user's machine" ([timeline](https://olas.network/timeline), approx.). Live numbers: 3,771 agents deployed, 452 daily active agents, 14,790,631 A2A transactions, $109,972.94 marketplace turnover ([olas.network](https://olas.network/)). x402 was integrated into Pearl in Q4 2025, and off-chain Mech requests cut median wait from about 66 to about 17 seconds in Q3 2026 ([timeline](https://olas.network/timeline), approx.). A partner quote from Gnosis: "On many days these agents make over 75% of Safe transactions on Gnosis Chain." ([olas.network](https://olas.network/))

**Weaknesses**: $109,973 of turnover across 14.79M A2A transactions is about $0.007 each. That is activity, not much income, and Olas's own blog asks "[Spam or](https://olas.network/blog/20-million-olas-agent-transactions)…" in a post title. The homepage shows "$0" OLAS burned as a placeholder. A 15% protocol fee on marketplace payments went live in June 2026 ([timeline](https://olas.network/timeline), approx.). It is token-first and centered on prediction markets. Pearl Mini was discontinued after Chrome Web Store rules banned prediction-market extensions. The agents run locally, but they *spend* through on-chain contracts rather than *serve* HTTP to the world.

**Territory they own**: *Co-owned, tokenized agents*, and the "agent bazaar".

**Relation to TOON**: **The nearest neighbor in the sovereign quadrant.** Agents run on your own hardware, keys stay local, and agents earn per request. The difference: Olas is an on-chain marketplace with a token, a 15% fee and its own contracts in the middle, and it does not make your HTTP service reachable. **Avoid**: "own your agent" / "agents you actually own", "co-own", "bazaar", "app store for agents", and a purple palette with a near-mono display face.

---

### Virtuals Protocol (Agent Commerce Protocol, ACP)
*https://www.virtuals.io · whitepaper.virtuals.io*

**What they do**: A platform for tokenized AI agents ("Agent Tokens"). Its **Agent Commerce Protocol** lets agents "discover services, negotiate jobs, coordinate execution, and settle payments autonomously", with escrow and evaluator agents ([virtuals.io](https://www.virtuals.io/); [commerce layer](https://whitepaper.virtuals.io/about-virtuals/commerce-layer)).

**Positioning**: A whole economy for agents. Title "Society of AI Agents". H1 "A society of AI agents. With its own GDP." ([virtuals.io](https://www.virtuals.io/))

**Target audience**: Crypto builders and token investors, and increasingly robotics and "physical labor".

**Core message**: "As agents perform cognitive, creative, financial, and physical work, they become a new labor class." ([virtuals.io](https://www.virtuals.io/))

**Tagline**: "A society of AI agents." **Big and memorable, with nothing a developer can check.** Recurring phrases: *Agentic GDP (aGDP)*, *EconomyOS*, "The passport, bank account, and payroll system for AI agents." ([virtuals.io](https://www.virtuals.io/))

**Brand personality**: grandiose, visionary, crypto-capital

**Voice & tone**: Manifesto lines in sets. "Agents need wallets, credentials, and economic rights." "Agents need bodies to affect the physical world." "We believe that aGDP will soon become the primary engine of global economic activity." ([virtuals.io](https://www.virtuals.io/))

**Visual identity**: Teal greens `#168389`, `#1a6f74`, `#1c5e62`, `#236d66`, `#44bcc3` on Tailwind greys (`#9ca3af`, `#f3f4f6`) (read from HTML/CSS). Fonts are the system UI sans stack, with **Cascadia Mono** in CSS (read from CSS; no custom display face found). Hero imagery is video.

**Strengths**: ACP v2.0 (April 2026) is "a ground-up rearchitecture of the Agent Commerce Protocol and the reference implementation of ERC-8183", after "18 months in production". It adds a non-custodial agent wallet, USDC escrow, and a CLI whose `acp serve` will "deploy handler functions as x402, MPP, and ACP native endpoints" ([ACP changelog](https://whitepaper.virtuals.io/acp/acp-changelogs)). Olas lists Virtuals among its partners. It reportedly passed $300M aGDP in December 2025 (unverified, secondary only).

**Weaknesses**: The homepage counters (Total Jobs, Total Revenue, Total aGDP) show 0 in the served HTML, and the robotics block says "No residents yet" next to a count of 23 ([virtuals.io](https://www.virtuals.io/)). The claims are huge ("primary engine of global economic activity"). Two different v2 launch dates (an October 2025 X post and the April 2026 changelog) muddy the story. It is token-first. The changelog does not say where `acp serve` endpoints run, on Virtuals infrastructure or on the user's machine (unverified).

**Territory they own**: *The society of agents*, and *aGDP*.

**Relation to TOON**: An intermediated, on-chain job market that charges at the door, with escrow and evaluators in the middle. **Watch `acp serve`**: if it serves x402 endpoints from a developer's own machine without a public host, Virtuals would be the first agent economy offering "hosts + charges". **Avoid**: "society", "GDP", "labor class", "passport/bank account/payroll for agents".

---

### Tailscale (Funnel)
*https://tailscale.com · tailscale.com/kb/1223/funnel*

**What they do**: A WireGuard-based private mesh network. **Funnel** exposes a local service to the public internet through Tailscale relay servers. It is "currently in beta" ([Funnel docs](https://tailscale.com/kb/1223/funnel)). In 2026 Tailscale added **Aperture**, an AI gateway for agents ([Aperture GA](https://tailscale.com/blog/aperture-ga)).

**Positioning**: Secure connectivity built on identity, now pitched as being "for the AI era". H1 "The best secure connectivity platform for the AI era". Subhead: "A Zero Trust identity-based connectivity platform that replaces your legacy VPN, SASE, and PAM" ([tailscale.com](https://tailscale.com/)).

**Target audience**: IT, security and platform teams ("50,000 businesses choose Tailscale"). Its fans are homelab developers and individuals.

**Core message**: Networking that is easy. "Who would have thought networking could be... easy?!" (testimonial, [tailscale.com](https://tailscale.com/)). Funnel: "Tailscale Funnel lets you route traffic from the broader internet to a local service" ([Funnel docs](https://tailscale.com/kb/1223/funnel)).

**Tagline**: "Secure your networking using identity with Tailscale" (closing CTA, approx.). **Enterprise and generic.** Funnel is not on the homepage.

**Brand personality**: friendly, competent, quietly technical

**Voice & tone**: Plain and confident in the docs, buyer-oriented on the homepage. "Funnel relay servers do not decrypt the traffic between public devices and your device." "This ensures that Tailscale cannot access or read any content." ([Funnel docs](https://tailscale.com/kb/1223/funnel)) Aperture: "Our solution started as an LLM proxy that eliminated the need to distribute API keys to both engineers and agents connected to your tailnet." ([Aperture GA, 2026-08-26](https://tailscale.com/blog/aperture-ga))

**Visual identity**: **Inter** for body and **"mdio"** (MD IO) for mono, both from CSS variables `--font-inter-family` and `--font-mdio-family` (read from CSS). Warm near-blacks and greys: `#2e2d2d`, `#232222`, `--color-black:#181717`, `#4f4f4f`. Muted brick reds (`#722626`, `#bf3f3f`) and a blue `#3f5db3` (read from HTML/CSS). The docs use blue `#3b82f6`/`#2563eb`. **Warm charcoal is close to TOON's charcoal `#2b2f36`.**

**Strengths**: Huge developer goodwill: "they enable people to make their own personal internet, for free in most cases." (testimonial, [tailscale.com](https://tailscale.com/)). Funnel's design matches part of TOON's promise: "It then terminates the TLS connection and passes the decrypted request to the local service" *on your device*. Relays only see ciphertext ([Funnel docs](https://tailscale.com/kb/1223/funnel)). Aperture went GA on 2026-08-26 with "initial tokens included", so Tailscale already resells AI usage ([Aperture GA](https://tailscale.com/blog/aperture-ga)).

**Weaknesses**: Funnel is beta, has "non-configurable bandwidth limits", "can only listen on ports 443, 8443, and 10000" and "can only use DNS names in your tailnet's domain" (ts.net) ([Funnel docs](https://tailscale.com/kb/1223/funnel)). It requires a Tailscale account and its relays. The homepage has moved to enterprise security and AI governance. **It has no way for a Funnel operator to charge callers.** The name "Aperture" collides with Lightning Labs' L402 proxy.

**Territory they own**: *Your own private network, made easy.*

**Relation to TOON**: Hosts the door, lightly intermediated: Tailscale's relays carry the traffic but cannot read it. **Highest latent threat in this batch.** Tailscale has the reach to residential machines, TLS terminated on-device, a developer audience that loves it, and since Aperture, a token-billing habit. Adding "charge per request" to Funnel would be a short step. **Avoid**: "Zero Trust", "your own personal internet", "tailnet" style coinages, and a warm charcoal *plus* friendly sans that would read like Tailscale. TOON's gold and pixel geometry must lead.

---

### zrok (NetFoundry / OpenZiti)
*https://zrok.io · github.com/openziti/zrok*

**What they do**: An open-source tunneling and sharing tool built on the OpenZiti zero-trust overlay. It does public shares (like ngrok) and private peer-to-peer shares between zrok clients, as SaaS (zrok.io) or self-hosted ([zrok.io](https://zrok.io/)). It is Apache-2.0 ([GitHub](https://github.com/openziti/zrok)). v2 renamed the binary to `zrok2` ([zrok v2 blog](https://blog.openziti.io/introducing-zrok-v2-0), approx.).

**Positioning**: The open-source, self-hostable alternative to commercial tunnels.

**Target audience**: Developers and self-hosters, and OpenZiti/NetFoundry enterprise prospects.

**Core message**: "zrok provides private or public, instant, secure tunneling of applications from anywhere." ([zrok.io](https://zrok.io/))

**Tagline**: H1 "Meet zrok, the World-Leading Open-Source, Zero-Trust Peer-to-Peer Tunneling and Ingress Solution". Closing line "Frictionless setup. Free to use. Open source." ([zrok.io](https://zrok.io/)) **The H1 is a string of buzzwords with an unbacked superlative. The closing line is good.**

**Brand personality**: earnest, engineering-led, open-source

**Voice & tone**: Feature-led with plain commands. "Run an OpenZiti network with zrok layered on top of it on a Raspberry Pi." "The single zrok binary contains everything you need to operate zrok environments and host your own service instances." "Run zrok2 share to share resources immediately, simply, and securely." ([zrok.io](https://zrok.io/))

**Visual identity**: **Neue Haas Grotesk** Display and Text (`neue-haas-grotesk-display`, `neue-haas-grotesk-text`, read from HTML). NetFoundry navy `--nf-navy:#00183F` (`#0A2B5E`, `#0D3A7A`), green `--nf-green:#6BBF4E`, bright blue `#1A7FD4`, off-white `#F4F6FA` (read from HTML CSS variables). It is a WordPress site.

**Strengths**: The most truly self-hostable option here: "zrok is available as SaaS or self-hosted", and private shares are "not exposed to any public endpoints" ([zrok.io](https://zrok.io/)). Active releases (v2.0.x through October 2026, [GitHub releases](https://github.com/openziti/zrok/releases)).

**Weaknesses**: "World-Leading" is unmeasured. There are no numbers on the page. The brand is split between zrok, OpenZiti and NetFoundry. The SaaS route needs an account (`zrok2 invite`). **There is no payment at all.**

**Territory they own**: *Open-source, self-hosted tunneling.*

**Relation to TOON**: Sovereign, hosts the door, and charges nothing. It is the open-source tunnel a TOON user might otherwise reach for. It also shows that "self-hosted + no open port" alone is taken: TOON must keep payment in the same sentence. **Avoid**: "Zero-Trust Peer-to-Peer Tunneling and Ingress", "share", "frictionless".

---

### Tor Project (onion services)
*https://www.torproject.org · community.torproject.org/onion-services*

**What they do**: Anonymity network and browser. **Onion services** are servers reachable only over Tor. They "don't need open ports because they punch through NAT" and "only establish outgoing connections" ([onion services overview](https://community.torproject.org/onion-services/overview/)).

**Positioning**: Privacy and freedom from surveillance, funded by donations. "Unlike Big Tech, Tor doesn't sell your data to make money." ([torproject.org](https://www.torproject.org/))

**Target audience**: Privacy-seeking individuals, journalists, activists, and people facing censorship. Onion operators are a small technical subset.

**Core message**: "Defend yourself against tracking and surveillance. Circumvent censorship." ([torproject.org](https://www.torproject.org/))

**Tagline**: "Tor: powered by you" / "Browse Privately. Explore Freely." ([torproject.org](https://www.torproject.org/)) **Clear and values-led, but about browsing, not hosting.**

**Brand personality**: principled, activist, communal

**Voice & tone**: Plain, values-first and protective. "Onion service traffic is encrypted from the client to the onion host." "Is your network filtered and you can't open ports on your firewall?" ([onion services overview](https://community.torproject.org/onion-services/overview/)) "Join the movement with a donation today!" ([torproject.org](https://www.torproject.org/))

**Visual identity**: **Source Sans Pro**, **Source Serif Pro** and **Source Code Pro** (read from CSS). Primary purple `--primary:#7D4698`, dark purple `--dark:#59316B`, green `--green:#68B030`, cyan `--cyan:#00A5BB`, yellow `--yellow:#FFBF00`, red `--red:#EF243E`, charcoal `--gray-dark:#333A41` (read from CSS variables). The onion logo is well known.

**Strengths**: Two decades of credibility. "Thousands of volunteer-run servers known as Tor relays" ([torproject.org](https://www.torproject.org/)). Onion addresses are self-authenticating: "they know that the content they are seeing can only come from that particular onion" ([overview](https://community.torproject.org/onion-services/overview/)). There is active Rust work: Arti 2.5.1 (2026-08-04) added Unix-socket targets for onion services, and Arti 2.7.0 (2026-10-01) fixed security issues and urged onion hosts to upgrade ([Arti 2.5.1](https://blog.torproject.org/arti_2_5_1_released/), [Arti 2.7.0](https://blog.torproject.org/arti_2_7_0_released/), approx.).

**Weaknesses**: Latency, client friction (callers need Tor), and darknet associations. There is no payment model: "6,490 donors every year keep Tor strong" ([torproject.org](https://www.torproject.org/)). The brand is about consuming privately, not about running a service.

**Territory they own**: *Onion services*, the original "hidden service": reachable, location-hidden, no open port.

**Relation to TOON**: Sovereign, hosts the door, no payment. **TOON's audience language includes "hidden service" (context.md), but that phrase is Tor's**, and in public it reads as darknet. Use "behind your router" or "no open port" instead. **Avoid**: "hidden service", onion imagery, layered or "relayed three times" metaphors, and Tor purple.

---

### Apify
*https://apify.com · agi.apify.com*

**What they do**: A marketplace and serverless platform for "Actors" (scrapers, automations, AI tools). Developers publish Actors, Apify runs them, and customers pay per event. Since June 2026, agents can pay for 20,000+ Actors with x402 (USDC on Base), with no Apify account needed for the buyer ([Apify blog, 2026-06-30](https://blog.apify.com/introducing-x402-agentic-payments/)).

**Positioning**: "Marketplace of ready-to-run tools for AI" (title). H1 "87,717 tools for your AI" (count changes live). Subhead: "Ready-to-run tools for your AI agents and apps. Just pick one and go." ([apify.com](https://apify.com/))

**Target audience**: Two sides. Buyers are businesses, AI agents ("Are you an AI agent? Fetch our quickstart to get started.") and developers. Sellers are independent developers ("Publish Actors. Get paid.") ([apify.com](https://apify.com/)).

**Core message to sellers**: "Building and running a SaaS is hard. Building an Actor and selling it on Apify Store is 10x easier. Get users from day one." ([apify.com](https://apify.com/))

**Tagline**: "Publish Actors. Get paid." / "$1.7M paid out last month. Many developers earn over $3k." ([apify.com](https://apify.com/)) **The best seller-side line in either research file, and it comes with real payouts.** The agent gateway: "The front door to Apify for AI agents." ([agi.apify.com](https://agi.apify.com/))

**Brand personality**: practical, builder-friendly, quietly confident

**Voice & tone**: Direct and benefit-led, close to TOON's own register. "Actors scale automatically as you gain new users. You don't need to worry about compute, storage, proxies, or authentication." "Handling payments, taxes, and invoicing is a painful part of running a SaaS. Apify does all that and sends you a net payout every month." ([apify.com](https://apify.com/)) "Basically, any Apify Actor can be paid for and run in as little as a single HTTP request." ([Apify blog](https://blog.apify.com/introducing-x402-agentic-payments/))

**Visual identity**: **GT Walsheim** for headings, **Inter** for body, **IBM Plex Mono** for code (read from inline CSS). `theme-color` `#020202`. Text `--color-neutral-text:#1f2123`, backgrounds `#ffffff`/`#f9f9fa`/`#f4f4f5`, primary blue `#246dff` with tint `#e0ebff` (read from HTML CSS variables). It also uses Claude's coral `#d97757` (likely an integration logo, inferred).

**Strengths**: Real money to independent developers ($1.7M a month). Pay-per-event became the standard in April 2026: "Fixed monthly rental fees are going away." ([Apify blog, 2026-04-14](https://blog.apify.com/standardizing-actor-pricing/)) The x402 launch: "more than 20,000 Apify Actors are now live on the protocol" and "Agents can buy web data and automation with USDC on Base, no API key required." ([Apify blog](https://blog.apify.com/introducing-x402-agentic-payments/)) The agent gateway also accepts MPP (Tempo, Solana) ([agi.apify.com](https://agi.apify.com/)). Agent onboarding via `apify.com/agents.md`.

**Weaknesses**: Fully intermediated. Apify runs the code, holds the money ("Billing is on us") and pays out monthly. Developers selling through agentic payments "must also have completed identity verification (KYC)" ([monetization docs](https://docs.apify.com/platform/actors/publishing/monetize), approx.). Agent payments are labeled "experimental" ([x402 docs](https://docs.apify.com/platform/integrations/x402), approx.). Buyers face a $1 minimum prepay, with "unused balance is non-refundable and expires with the account" (14-day TTL) ([agi.apify.com](https://agi.apify.com/), approx.). The payout figure differs between the homepage ($1.7M) and the blog navigation ($1.4M), probably from different months.

**Territory they own**: *Publish a tool, get paid*: the indie seller's marketplace for agent tools.

**Relation to TOON**: **The intermediated mirror of TOON.** It hosts *and* charges per request, now with x402 and no buyer account, but on Apify's cloud, with Apify as merchant of record and KYC'd sellers. It occupies the "hosts + charges" corner TOON wants, from the intermediated side, and it is the one a TOON prospect will compare against. TOON's honest contrast: *your code stays on your machine, and the payment never passes through a platform's ledger.* **Avoid**: "Publish … Get paid.", "front door for AI agents", "ready-to-run", "Billing is on us", and an `agents.md` onboarding gimmick presented as novel (ngrok and Apify both do it).

---

### OpenRouter
*https://openrouter.ai*

**What they do**: One OpenAI-compatible API that routes each request to hundreds of LLMs across many providers. Buyers prepay credits and pay per token ([openrouter.ai](https://openrouter.ai/)).

**Positioning**: The neutral router between apps and model providers. H1 "The Unified Interface For Every Model" ([openrouter.ai](https://openrouter.ai/)).

**Target audience**: Developers and AI apps (Replit, Cline and Hermes Agent are featured), and model providers.

**Core message**: Choice and reliability through routing. "Fall back to other providers when one goes down." ([openrouter.ai](https://openrouter.ai/))

**Tagline**: "Better prices, better uptime, no subscriptions." ([openrouter.ai](https://openrouter.ai/)) **Clear and comparative, and it owns *routing* for AI requests.**

**Brand personality**: pragmatic, data-forward, neutral

**Voice & tone**: Spare and metric-driven. "Generate anything through a single, unified interface. All major models in one place." "Keep costs in check without sacrificing speed. OpenRouter runs at the edge for minimal latency between your users and their inference." ([openrouter.ai](https://openrouter.ai/))

**Visual identity**: **Plus Jakarta Sans** (`--font-sans`) and **Gordita** (`--font-brand`), with **Geist Mono** (`--font-mono`) (read from CSS). `theme-color` `rgb(255,255,255)` light and `rgb(9,10,11)` (`#090a0b`) dark. `--primary` is `hsl(239 84% 67%)` (`#6467f2`, indigo) in light and `hsl(263.7 90.4% 54.9%)` (`#7624f4`, violet) in a dark variant, plus a lime `hsl(72.9 100% 50%)` (`#c8ff00`) variant (read from CSS, converted). Hero imagery is a "Model routing visualization".

**Strengths**: Scale: "600T+ Monthly Tokens", "10M+ Global Users", "80+ Providers", "500+ Models", "250k+ apps using OpenRouter with 4.2M+ users globally" ([openrouter.ai](https://openrouter.ai/)). Signup via Google, GitHub or MetaMask. It shows that buyers like one endpoint with per-request billing.

**Weaknesses**: "No markup" on inference, but "OpenRouter charges a 5.5% ($0.80 minimum) fee when you purchase credits" and "Crypto payments are charged a fee of 5%" ([FAQ](https://openrouter.ai/docs/faq), approx.). It needs an account and prepaid credits. Providers are mainly large labs and inference companies. No x402 or agent-native payment appears on the homepage or FAQ.

**Territory they own**: *Routing* requests across providers through a single interface.

**Relation to TOON**: Intermediated and charges at the door. It does not host, but it holds the money and the routing decision. **Language risk**: "routing" is OpenRouter's word in AI. TOON routes *payments hop by hop between peered connectors*, so always say what is routed. Nevermined's post "Platforms want one upstream. Model routers proved it." shows routers are becoming the model for agent marketplaces. **Avoid**: "unified interface", "one endpoint, every …", "fallbacks", and indigo/violet primaries.

---

> **Adjacent, not profiled in full**
> - **Fetch.ai / Agentverse**: Meta description "The Complete Ecosystem for the Agentic Economy." H1 "Your personal AI" ([fetch.ai](https://fetch.ai/)). It has moved toward consumers. Visuals: **Geist**, **Geist Mono**, **Lexend**, indigo `#4a3aff` / `#5f38fb` on navy `#000d3d` (read from CSS). Agentverse returned a Cloudflare challenge.
> - **Payman**: "We deploy AI agents that handle money." Its market is now banks and credit unions ([paymanai.com](https://paymanai.com/)). Visuals: **DM Sans**, teal `#0e3d42` on cream `#f5f3eb` (read from HTML). **Note: cream background with deep teal is close to TOON's cream `#f3efe6`.**
> - **Crossmint**: "Stablecoin infrastructure for the new economy" ([crossmint.com](https://www.crossmint.com/)). Enterprise, with brand green `--base--brandgreen:#00c768` (read from CSS).
> - **Mastercard Verifiable Intent**, co-developed with Google, is reported as a standard for recording what a user authorized (from a search snippet of Mastercard's newsroom; unverified).

---

## 03 — Closing synthesis

### How the map changes

Same axes as competitors.md. Horizontal: **Intermediated ← → Sovereign**. Vertical: **Charges at the door ← → Hosts the door**. New brands are in CAPS, and brands from part 1 are in lower case.

```
                       HOSTS THE DOOR (reachability / compute)
                                    │
  ngrok ●                           │                     ● ZROK (self-hosted, no pay)
  Cloudflare Tunnel ●  ● TAILSCALE  │                     ● TOR ONION (no pay)
  Akash ●               FUNNEL      │          ● Holepunch (no pay)
                                    │                              ◎ TOON
  ● APIFY  (hosts + charges,        │      ● OLAS PEARL/MECH       (hosts + charges,
     x402, but platform-run)        │       (own machine, earns;    sovereign)
                                    │        token + 15% fee)
                                    │                 ○ Nostr DVMs (unbranded)
  INTERMEDIATED ────────────────────┼──────────────────────────────────── SOVEREIGN
                                    │
  ● VISA / MASTERCARD   ● AP2       │      ● Lightning L402
  ● NEVERMINED   ● OPENROUTER       │   ● Interledger
  Stripe MPP ●  Skyfire ●  x402 ●   │
  ● VIRTUALS ACP (escrow)           │
                                    │
                       CHARGES AT THE DOOR (payment only)
```

- **Bottom-left is now crowded**: AP2, both card networks, Nevermined, OpenRouter and Virtuals join Stripe, Skyfire and x402. The money and the press releases are here, and so is the vocabulary ("mandate", "credentialed agent", "agentic commerce at scale").
- **Top-left has a new kind of player: Apify both hosts *and* charges**, with x402 and no buyer account, from the intermediated side. It is the first brand in either file to take the "hosts + charges" corner, and it is TOON's closest *functional* comparison.
- **Top-right gets more tenants, still without payment**: zrok and Tor show that "self-hosted, no open port" is well covered. Without "paid per request" in the same sentence, TOON would sound like a tunnel.
- **Olas sits nearest TOON**: it is the only new brand where the agent runs on the user's own hardware (Pi 5 included) *and* earns per request. But it adds a token, on-chain contracts and a 15% protocol fee in the middle, and it does not make an HTTP service reachable.
- **The open space has shrunk but is still empty**: no branded player yet is *reachable with no open port + paid per request + nobody in the middle*. Apify has the first two only by being the middle. Olas has local hosting and earning only through a token marketplace. Tailscale has reachability with relays that don't read traffic, and no payment.

### New threats to "your machine is the business"

1. **Tailscale adding payment to Funnel** (highest latent threat). It has the install base on home machines, TLS terminated on the device, a developer brand people love, and through Aperture a habit of billing AI tokens. Charging Funnel callers would be one product step. TOON's defense is to be the open, multi-connector version before then, and to own the sentence first.
2. **Apify as "the easy version"**. "Publish Actors. Get paid." plus "$1.7M paid out last month" is a hard pitch to beat for a developer who doesn't care where the code runs. TOON has to make *where it runs* and *who holds the money* matter, using its own proof, not fear.
3. **Mastercard Agent Pay for Machines** takes the words "fractions of a cent" and "microtransactions" for card networks, with Coinbase, Stripe, Cloudflare and Tempo on board. Sub-cent alone no longer sets TOON apart. The difference is *no credential, no directory, no issuer*.
4. **Olas's "agents you actually own"** pre-empts the ownership framing for agents running locally. TOON should frame it as *reachable and paid*, not *owned*.
5. **Virtuals `acp serve`** turns handler functions into x402/MPP endpoints. Where they run is not documented (unverified). If they run locally with built-in reachability, ACP becomes a direct competitor.

### New clichés (add to the competitors.md list)

"Mandate" / "set a mandate" (AP2, Nevermined), "a card and a budget", "agentic commerce, at scale", "trust is the infrastructure", "a new class of payments", "superbloom", "first live agentic transaction in [country]" (a whole genre of press release), "credentialed / verified agents", "agentic GDP / aGDP", "society of agents", "agent app store", "agent bazaar", "the front door for AI agents", "unified interface", "Zero Trust", "World-Leading", "frictionless", and the "Are you an AI agent? Read our agents.md" onboarding move (now ngrok *and* Apify).

### Phrases now taken

| Phrase | Owner |
|---|---|
| "Agents pay. Agents get paid. Autonomously." | Nevermined |
| "Publish Actors. Get paid." / "The front door to Apify for AI agents." | Apify |
| "Co-own AI" / "agents you actually own" / "The AI Agent Bazaar" | Olas |
| "A society of AI agents. With its own GDP." / "aGDP" / "EconomyOS" | Virtuals |
| "The Unified Interface For Every Model" / "Better prices, better uptime, no subscriptions." | OpenRouter |
| "Agentic commerce, at scale" / "Trusted Agent Protocol" | Visa |
| "Agent Pay for Machines" / "superbloom of AI business models" | Mastercard |
| "Mandate" (Intent/Cart Mandate) | Google AP2 |
| "Onion service" / "hidden service" / "Tor: powered by you" | Tor |
| "Aperture" | Both Lightning Labs (L402 proxy) and Tailscale (AI gateway) |
| "Zero Trust … Tunneling and Ingress" | zrok / Tailscale |

**Implication for TOON's own language**: drop "hidden service" from public copy (it's Tor's, and reads as darknet). Don't lead with "agents get paid" (Nevermined) or "own your agent" (Olas). Always say what TOON *routes* (payments, hop by hop), to stay clear of OpenRouter. The free sentence is still the combined one: **"Your machine answers the request and gets paid for it, with no open port and nobody in the middle."**

### Visual notes from this batch

- **Purple keeps returning**: Olas `#7e22ce`, Tor `#7D4698`, OpenRouter `#6467f2`/`#7624f4`, Fetch `#4a3aff`.
- **Deep teal is a new cluster**: Nevermined `#0d3f48`, Virtuals `#168389`, Payman `#0e3d42`.
- **Gold and cream pressure**: Nevermined uses a `#ffd700` glow (after Skyfire's tan `#D9A36A`), and Payman sets teal on cream `#f5f3eb`. TOON's flat gold `#c9a24a` on charcoal and cream stays distinct only if it stays **flat** (no glow, no gradient) and avoids teal.
- **Warm charcoal**: Tailscale's `#232222`/`#181717` is near TOON's charcoal. Lead with gold and pixel geometry so the two don't blur.
- **Type**: Inter appears again (Olas, Apify, Tailscale). Olas already uses **Neue Machina**, a technical near-mono display face, so a "mono with character" headline face is no longer unclaimed. Choose one distinctly different from Neue Machina.

---

## Sources

- Google AP2: [ap2-protocol.org](https://ap2-protocol.org/) · [AP2 FAQ](https://ap2-protocol.org/faq/) · [Google Cloud blog announcement (2025-09-16)](https://cloud.google.com/blog/products/ai-machine-learning/announcing-agents-to-payments-ap2-protocol) · [a2a-x402 repo](https://github.com/google-agentic-commerce/a2a-x402) · [AP2 repo](https://github.com/google-agentic-commerce/AP2)
- Visa: [Visa Intelligent Commerce](https://www.visa.com/en-us/solutions/intelligent-commerce) · [Trusted Agent Protocol release](https://usa.visa.com/about-visa/newsroom/press-releases.releaseId.21716.html) · [Intelligent Commerce Connect (2026-04-08)](https://usa.visa.com/about-visa/newsroom/press-releases.releaseId.22276.html) · [Visa Payments Forum (2026-06-10)](https://usa.visa.com/about-visa/newsroom/press-releases.releaseid.22491.html)
- Mastercard: [Agent Pay for Machines investor release (2026-06-10)](https://investor.mastercard.com/investor-news/investor-news-details/2026/Mastercard-Launches-Agent-Pay-for-Machines-to-Unlock-Super-Fast-Always-On-Payments/default.aspx) · [Agent Pay for Machines product page](https://www.mastercard.com/us/en/business/artificial-intelligence/mastercard-agent-pay/agent-pay-for-machines.html) (403 to automated fetch; not read)
- Nevermined: [nevermined.ai](https://nevermined.ai/) · [blog index](https://nevermined.ai/blog) · [Gartner Cool Vendor post](https://nevermined.ai/blog/nevermined-named-a-gartner-r-cool-vendor-tm-in-agentic-ai-for-banking) · [Platforms want one upstream](https://nevermined.ai/blog/platforms-want-one-upstream)
- Olas: [olas.network](https://olas.network/) · [Mech Marketplace](https://olas.network/mech-marketplace) · [Timeline](https://olas.network/timeline) · [20M transactions post](https://olas.network/blog/20-million-olas-agent-transactions)
- Virtuals: [virtuals.io](https://www.virtuals.io/) · [Commerce layer](https://whitepaper.virtuals.io/about-virtuals/commerce-layer) · [ACP changelog](https://whitepaper.virtuals.io/acp/acp-changelogs)
- Tailscale: [tailscale.com](https://tailscale.com/) · [Funnel docs](https://tailscale.com/kb/1223/funnel) · [Aperture GA (2026-08-26)](https://tailscale.com/blog/aperture-ga)
- zrok: [zrok.io](https://zrok.io/) · [GitHub](https://github.com/openziti/zrok) · [Releases](https://github.com/openziti/zrok/releases) · [Introducing zrok v2.0](https://blog.openziti.io/introducing-zrok-v2-0)
- Tor: [torproject.org](https://www.torproject.org/) · [Onion services](https://community.torproject.org/onion-services/) · [Onion services overview](https://community.torproject.org/onion-services/overview/) · [Arti 2.5.1](https://blog.torproject.org/arti_2_5_1_released/) · [Arti 2.7.0](https://blog.torproject.org/arti_2_7_0_released/)
- Apify: [apify.com](https://apify.com/) · [agi.apify.com](https://agi.apify.com/) · [x402 launch blog (2026-06-30)](https://blog.apify.com/introducing-x402-agentic-payments/) · [Standardizing Actor pricing (2026-04-14)](https://blog.apify.com/standardizing-actor-pricing/) · [x402 docs](https://docs.apify.com/platform/integrations/x402) · [Monetization docs](https://docs.apify.com/platform/actors/publishing/monetize)
- OpenRouter: [openrouter.ai](https://openrouter.ai/) · [FAQ](https://openrouter.ai/docs/faq)
- Adjacent: [fetch.ai](https://fetch.ai/) · [paymanai.com](https://paymanai.com/) · [crossmint.com](https://www.crossmint.com/)
