# Competitor Brand Analysis: TOON Protocol

*Researched 2026-10-14. Hero copy is verbatim from live homepages unless marked "(approx.)". Hex values and fonts were read from site CSS unless marked "(unverified)". How colors are used on the rendered pages is inferred, since the pages were not viewed visually. Sources are listed at the end.*

*Part 2, [competitors-more.md](competitors-more.md), profiles ten more brands from primary sources: Google AP2, Visa and Mastercard, Nevermined, Olas, Virtuals, Tailscale Funnel, zrok, Tor onion services, Apify and OpenRouter. Its findings are merged into sections 01 and 03–07 below. The full profiles live there.*

---

## 01 — Competitive landscape overview

Since 2025, "payments for AI agents" has become one of the loudest categories in infrastructure, and almost every brand in it tells the same story. The web reserved HTTP 402 for payments, nobody used it, and agents now need it. x402 ("an open, neutral standard for internet-native payments"), L402 ("the Internet-Native Payments Protocol for Agents"), Cloudflare ("dust off a mostly forgotten piece of the web"), Stripe's Machine Payments Protocol and Skyfire ("The Agent Trust Stack") all compete for the words *internet-native*, *agentic* and *no signup*.

The category takes something for granted: **the seller already has a public server**, plus often an account with a company in the middle (Coinbase's facilitator, Cloudflare as merchant of record, a Stripe merchant account). The brands that do solve reachability (ngrok, Cloudflare Tunnel, Tailscale Funnel, zrok, Tor, Holepunch) or compute (Akash) offer no way for the operator to earn per request. Hosting and payment are sold as separate products by separate companies. There are two partial exceptions. **Apify** hosts and charges ("Publish Actors. Get paid."), but on its own servers, holding the money itself. **Olas** runs agents on the user's own machine and pays them per request, but through a token marketplace that takes a 15% fee. Meanwhile the card networks and Google have arrived: AP2 "mandates", Visa Intelligent Commerce, and Mastercard's Agent Pay for Machines at "fractions of a cent".

Visually the category has two looks. The first is purple-tinted dev-infra: ngrok, Lightning, Interledger, Nostr. The second, newer one is an editorial serif with JetBrains Mono: x402 and Akash both use Instrument Serif. Copy is just as uniform: "Zero fees", "one line of code", "no signup, no API key", "agents are here". Nobody brands the person TOON serves: someone whose own machine is the business.

---

## 02 — Competitor profiles

### x402 (x402 Foundation / Linux Foundation; originated at Coinbase)
*https://www.x402.org · docs.cdp.coinbase.com/x402*

**What they do**: An open protocol that uses HTTP 402 to let any API or digital service charge per request, with payment inside the request–response cycle.

**Positioning**: *The* neutral standard for paying over HTTP. Governance is now institutional: about 40 members, with Visa, Circle, Cloudflare and Coinbase quoted at the July 2026 launch.

**Target audience**: Developers selling APIs and content, agent builders, and increasingly payments and cloud institutions.

**Core message**: "Payments on the internet are fundamentally flawed." The fix is built into HTTP.

**Tagline**: "x402 is an open, neutral standard for internet-native payments." **It's clear and claims the standard**, but the meta description goes further ("the internet's payment standard"), which overclaims and contradicts "neutral".

**Brand personality**: confident, institutional, manifesto-like

**Voice & tone**: Short, sure and mission-driven, framed as "broken internet vs. fix built into HTTP". Examples: "Accept payments with a single line of code." "It's how the internet should be: open, free, and effortless." The "Zero" list reads: "Zero protocol fees / Zero wait / Zero friction / Zero centralization / Zero restrictions."

**Visual identity**: Light and editorial. Instrument Serif for display, Inter for body. Nearly monochrome (`#222222`, `#000`, `#FFF`, `#F1F1F1`), with one blue (`#3452FF`) used only in the loader. It is built on a WordPress Salient theme and has little visual identity it can own.

**Strengths**: Real traction: the homepage shows 75.41M transactions and $24.24M volume over 30 days, with 22K sellers. Partners on the logo strip include AWS, Cloudflare, Stripe and Vercel. Neutral governance takes Coinbase out of the story.

**Weaknesses**: "Zero centralization" sits next to Coinbase's dominant facilitator. Volume averages about $0.32 per transaction, which looks like microtransactions or test traffic. The visuals come from a template. Membership lists differ between sources. And it still assumes a public server and domain.

**Territory they own**: *The HTTP 402 standard.* When people say "pay per request over HTTP", x402 is the name they mean.

---

### Lightning Labs / L402
*https://lightning.engineering · docs.lightning.engineering*

**What they do**: Open-source Lightning Network software (LND, Lightning Terminal, Loop). L402 is their HTTP 402 payment protocol, served by **Aperture, an L402 reverse proxy**. Lightning Agent Tools (Feb 2026) bundles 7 agent skills, `lnget` and Aperture, and names Claude Code and Codex.

**Positioning**: Bitcoin as the money agents use, with L402 as "the standard for selling and buying digital resources."

**Target audience**: Node operators and bitcoin devs. Since 2026, agent builders too, and the agents themselves ("(Hi agents! 👋)").

**Core message**: Agents can't get bank accounts, so they need money that is native to the internet.

**Tagline**: "building faster, cheaper, global layer-two bitcoin." **No.** It is generic and dated, and says nothing about agents. All the agent energy is on the blog: "The agents aren't coming. They're here."

**Brand personality**: playful, technical, evangelical

**Voice & tone**: Punchy, casual, with emoji in titles. "Agents don't have government IDs or bank accounts." "The machine-payable web won't build itself. Actually, it might. But it'll be faster with your help." "No signup, no API key, no identity required."

**Visual identity**: Light grey background (`#f5f5f5`), navy text (`#252f4a`), deep purple (`#57038d`), with pink (`#f5406e`) and orange (`#ff7c00`) accents. Work Sans and Open Sans. It reads as corporate-tech.

**Strengths**: Five years of L402 in production (Loop). It is the **closest prior art to TOON's "payment as a reverse proxy"**, and its voice talks to agents directly, wittily.

**Weaknesses**: The homepage is out of step with the blog. Bitcoin-only. "No identity required" glosses over running a node, managing channels and providing liquidity. It attacks protocols that run "through a single company's infrastructure" without naming them. And the host still has to be reachable.

**Territory they own**: *Bitcoin as machine money, and talking straight to agents.*

---

### Interledger Foundation
*https://interledger.org*

**What they do**: A nonprofit that stewards the Interledger Protocol (packet-switched payments routed through connectors across ledgers), Open Payments, Rafiki and grants.

**Positioning**: Changing the financial system: open standards, governed independently.

**Target audience**: Financial institutions, regulators, grantees and students. Developers come second, and agents not at all.

**Core message**: Financial systems weren't built to work together, and open standards fix that.

**Tagline**: "Rewriting the rules that move money." **It works as a policy mission** and is strong and memorable, but it speaks to regulators, not builders. A section heading, **"Making Money Move like Data"**, is the nearest phrase anywhere in the category to TOON's thesis.

**Brand personality**: principled, movement-driven, institutional

**Voice & tone**: Mission-driven and inclusive, with a policy lens. "We see a world where money moves freely and opportunity follows." "Open standards only stay open if the organization behind them has no reason to close them."

**Visual identity**: A dark background (`#0d0d0d`), orchid purple (`#80409d` / `#662b81`), apricot (`#ffb259`), tangerine (`#ff8617`), red (`#FF334B`) and cream (`#fff8f0`). Poppins and Inter, with a photographic hero (the founder).

**Strengths**: TOON's design comes from Interledger: connectors, packets, and routing that changes currency hop by hop. It also has real standards credibility and "$21M+ in grants, 270+ projects".

**Weaknesses**: Web Monetization is "no longer being proactively developed" but is still promoted. Its proof is about grants, not payment volume. Open Payments has nothing on agents. It has little developer mindshare.

**Territory they own**: *Interoperability as systemic reform.*

---

### Cloudflare (Tunnel, pay per crawl, Monetization Gateway, x402 Foundation)
*https://cloudflare.com · developers.cloudflare.com*

**What they do**: Tunnel connects servers to Cloudflare without opening a port ("no publicly routable IP"). Pay per crawl (2025) and the **Monetization Gateway** (waitlist opened July 2026) charge "for any resource behind Cloudflare via x402". Cloudflare co-founded the x402 Foundation.

**Positioning**: The network between the internet and everything on it, now also the place where access is paid for.

**Target audience**: Publishers and enterprises (for payment), network and security teams (for Tunnel).

**Core message**: "Content for crawlers today, agents tomorrow." You can "charge for access."

**Tagline**: "Global Serverless Platform" (from the homepage title; may be a stripped-down fetch). **Functional and forgettable.** Cloudflare's real voice lives on the blog.

**Brand personality**: authoritative, visionary, platform-scale

**Voice & tone**: Technical and visionary, with a habit of reviving web standards. "a future where intelligent agents can programmatically negotiate access to digital resources."

**Visual identity**: Cloudflare orange (~`#F38020`, unverified) on white, the cloud logo and clean corporate illustration.

**Strengths**: It alone holds both halves, a no-open-port tunnel and a 402 charge, for its own customers. It sets the agenda through the blog.

**Weaknesses**: "Cloudflare acts as the Merchant of Record." Both sides need Cloudflare accounts, and all traffic runs through Cloudflare. Tunnel is never connected to earning in the branding. The monetization products are a beta and a waitlist, aimed at publishers.

**Territory they own**: *The toll booth of the web.*

---

### ngrok
*https://ngrok.com*

**What they do**: Developer infrastructure that routes traffic to apps, APIs and AI models. It began as a localhost tunnel and now includes an AI Gateway (ngrok.ai, July 2026) and MCP connectivity.

**Positioning**: One gateway to services running anywhere, from localhost to production.

**Target audience**: Individual developers first, then platform and enterprise teams (Databricks, Zendesk).

**Core message**: "Start on localhost, ship to prod."

**Tagline**: "Connect anything, anywhere." **Broad and nearly generic.** It gave up "your app's front door" specificity for platform breadth. "Way more than a tunnel to localhost" shows it is moving away from the tunnel use developers love it for.

**Brand personality**: cheeky, confident, developer-native

**Voice & tone**: Casual and spread by word of mouth. "Developers go on and on about us." It quotes users: "ngrok is so effing amazing." It also publishes a prompt for AI agents: "Read https://ngrok.com/agent-setup/prompt.md and follow it…"

**Visual identity**: Theme color deep purple `#4a3066`, with rose (`#F43F5E`), lime (`#84cc16`) and sky (`#38BDF8`) accents. Roobert and JetBrains Mono, likely with a terminal-led look.

**Strengths**: Developers love it, it has the best "one command" story in the market, and it was first to write onboarding for agents. It goes after Cloudflare openly ("Migrate to ngrok from Cloudflare Tunnels").

**Weaknesses**: There is **no way for users to charge their callers**. Agents appear as *users* of ngrok, never as businesses that earn. It needs an account, all traffic passes through ngrok, and the enterprise move blurs its indie appeal.

**Territory they own**: *Getting localhost onto the internet.*

---

### Stripe (agentic commerce, Machine Payments Protocol, Tempo)
*https://stripe.com*

**What they do**: Payments for businesses. At Sessions 2026 Stripe launched the Agentic Commerce Suite, the **Machine Payments Protocol (MPP)** with Tempo ("agents can now programmatically transact with your business via microtransactions…"), agent wallets in Link, and Issuing for agents. Tempo is the payments chain from Stripe and Paradigm (mainnet March 2026).

**Positioning**: "Building the economic infrastructure for AI." Agents are a new sales channel and a new kind of customer.

**Target audience**: Merchants, platforms, enterprises and AI companies.

**Core message**: "Monetize through agentic commerce." Make your products available to buy through AI.

**Tagline**: "Financial infrastructure to grow your revenue." **It works for merchants** and says nothing to someone running a service from home.

**Brand personality**: polished, authoritative, vast

**Voice & tone**: Precise, confident, large-scale. "The backbone of global commerce." "From your first transaction to your billionth."

**Visual identity**: Blurple `#635BFF`, Söhne and soft gradients (from memory, not checked this session). It is the benchmark for what "serious payments" looks like.

**Strengths**: Trust, craft and distribution ("$1.9T" volume, "50% of Fortune 100"). MPP now covers microtransactions in stablecoins too, which brings Stripe closer to per-request pricing.

**Weaknesses**: You still need a merchant account, KYC and a business setup. The "agentic" model is about agents buying from merchants. Stripe and the large platforms (Google, Meta, OpenAI) are always in the middle. The Agentic Commerce Protocol page has disappeared (404), so the agent naming is unsettled.

**Territory they own**: *Payments done properly, for businesses, now including agents.*

---

### Akash Network
*https://akash.network*

**What they do**: An open marketplace for compute, sold today mainly as cheap GPUs for AI. Providers lease out their hardware.

**Positioning**: "The Open Cloud for AI's Next Frontier." It is the cheaper alternative to AWS.

**Target audience**: AI/ML teams and Docker users, with GPU owners as providers in second place.

**Core message**: "Tap into global GPU power at a fraction of the cost."

**Tagline**: "Global Grid. No Off Switch." **The strongest line in the category**: it is short and physical, and implies sovereignty without crypto jargon. The rest of the page is about price.

**Brand personality**: direct, quantitative, rebellious-lite

**Voice & tone**: Numbers first and set against AWS. "Market-driven pricing vs. legacy markups." "If it runs in a container, it runs on Akash." Crypto vocabulary is mostly gone.

**Visual identity**: Near-black (`#030303`, `#0D0D0E`) with neon green (`#8BFE79`, `#A6FA99`). Instrument Serif and JetBrains Mono. The earlier red brand (~`#FF414C`, from memory) appears to have been replaced.

**Strengths**: Concrete price proof ("H100s for $1.33/hr vs AWS at $3.93/hr"), a well-executed rebrand and a crisp voice.

**Weaknesses**: It reads like a discount GPU reseller, and Fluence makes the same "up to 85%" pitch. Earning as a provider is barely mentioned. Your workload still runs on someone else's machine. "Public utility" sits awkwardly next to a token economy.

**Territory they own**: *Cheap open GPUs.*

---

### Skyfire
*https://skyfire.xyz*

**What they do**: Gives AI agents verified identity ("Know Your Agent") and payment credentials (KYAPay tokens over cards or USDC) so websites let them in and they can check out.

**Positioning**: "The Agent Trust Stack": the layer that lets merchants accept agents.

**Target audience**: Companies running agents, and merchants and publishers deciding whether to let agents in.

**Core message**: Verified agents get through. "No 403 errors, captchas or blocked checkouts."

**Tagline**: "Access. Identity. Checkout. The Agent Trust Stack." **It's clear about the product** but is a stack of nouns that sounds like enterprise security.

**Brand personality**: trustworthy, enterprise, gatekeeping

**Voice & tone**: Enterprise security marketing built on trust and scale claims. "One token, two surfaces." "Covering more than 60% of the Web" (no source given).

**Visual identity**: Ink `#28171B`, brand red `#C93C09`, teal `#1B7A69`/`#0F4A3F`, and a warm gradient from `#EE7843` through **`#D9A36A`** to `#B8C58E`. Geist, Inter and JetBrains Mono, mostly light. **Note**: this is the warmest palette in the category, and its tan is the closest any competitor gets to TOON's gold.

**Strengths**: A large wall of partner logos (Visa, Mastercard, Akamai, Okta, Fastly) and a clear KYA hook.

**Weaknesses**: Identity gatekeeping is the opposite of permissionless. Its claims have no sources. "KYA Pay" and "KYAPay" are spelled inconsistently. And a plain request to its site hit a Cloudflare bot block, the exact friction it promises to remove.

**Territory they own**: *Know Your Agent.*

---

> **Adjacent brands, not profiled in full**
> - **Holepunch / Pear** (holepunch.to, pears.com): "The Peer-to-Peer Company", meaning "apps that don't use any servers whatsoever." It owns *serverless P2P apps* and is backed by Tether. But it has **no earning story**, its brand is split across four sites, and pears.com is full of hype ("Empowering Developers, Disrupting the Norm!").
> - **Nostr DVMs (NIP-90) and zaps (NIP-57)**: the pitch closest to TOON's. A service runs on your own machine, is found through relays and is paid per job. It has **no brand owner**. Zaps present payment as a visible social act ("for fun or for spam deterrence"). TOON already speaks NIPs.
>
> **Profiled in part 2 ([competitors-more.md](competitors-more.md))**: Google AP2 · Visa Intelligent Commerce and Mastercard Agent Pay · Nevermined · Olas · Virtuals Protocol (ACP) · Tailscale Funnel · zrok · Tor onion services · Apify · OpenRouter. Short notes cover Payman, Crossmint and Fetch.ai.

---

## 03 — Competitive brand map

**Axis 1 (horizontal): Intermediated ← → Sovereign.** Is a company in the request path (an account, a facilitator, a merchant of record, a gateway), or does the operator own the endpoint?

**Axis 2 (vertical): Charges at the door ← → Hosts the door.** Does the brand only add payment to a server you already run, or does it make the service reachable as well?

Brands from part 2 are in CAPS.

```
                       HOSTS THE DOOR (reachability / compute)
                                    │
  ngrok ●                           │                     ● ZROK (self-hosted, no pay)
  Cloudflare Tunnel ●  ● TAILSCALE  │                     ● TOR ONION (no pay)
  Akash ●               FUNNEL      │          ● Holepunch (no pay)
                                    │                              ◎ TOON
  ● APIFY  (hosts + charges,        │      ● OLAS                  (hosts + charges,
     x402, but platform-run)        │       (own machine, earns;    sovereign)
                                    │        token + 15% fee)
                                    │                 ○ Nostr DVMs (unbranded)
  INTERMEDIATED ────────────────────┼──────────────────────────────────── SOVEREIGN
                                    │
  ● VISA / MASTERCARD   ● AP2       │      ● Lightning L402
  ● NEVERMINED   ● OPENROUTER       │   ● Interledger
  Stripe MPP ●  Skyfire ●  x402 ●   │
  ● VIRTUALS ACP (escrow)           │
  Cloudflare Monetization ●         │
                                    │
                       CHARGES AT THE DOOR (payment only)
```

- **Bottom-left (intermediated payment) is now crowded.** Stripe, Skyfire, Cloudflare and x402 (in practice through Coinbase's facilitator) are joined by AP2, both card networks, Nevermined, OpenRouter and Virtuals. The money, the institutions and the noise ("mandate", "credentialed agent", "agentic commerce at scale") are all here.
- **Bottom-right (sovereign payment)**: L402 and Interledger. They are principled but only handle payment, and their brands are tied to Bitcoin or to policy work.
- **Top-left (intermediated reachability)**: ngrok, Cloudflare Tunnel, Tailscale Funnel and Akash make you reachable or rent you compute, and they bill *you*. **Apify is the exception**: the first brand that both hosts *and* charges (x402, no buyer account), by being the platform in the middle. It is TOON's closest *functional* comparison.
- **Top-right (sovereign hosting)**: zrok, Tor and Holepunch show that "self-hosted, no open port" is well covered, but none of them pays. **Olas** sits nearest TOON: agents run on the user's own hardware and earn per request, but a token, on-chain contracts and a 15% fee sit in the middle, and it doesn't make an HTTP service reachable. DVMs have the income with no brand.

**Open territory**: *Sovereign, and both hosts and charges.* It is smaller than before but still empty. No branded player says **"your machine is the business"**: reachable with no open port, paid for each request, and no company in the middle. Apify has the first two only by being the middle. Olas earns only through a token marketplace. Tailscale has reachability but no payment. TOON's thesis, that sending a message and sending money are the same action, covers both halves at once. **Without "paid per request" in the same sentence, TOON sounds like a tunnel.**

**Threats to the open territory** (detail in [competitors-more.md](competitors-more.md)):
1. **Tailscale adding payment to Funnel.** This is the largest risk of a future move. Tailscale has the installs on home machines, TLS terminated on the user's own device, a developer brand people love, and a habit of billing AI usage through its Aperture gateway. TOON's defense is to be the open version with many connectors, and to own the sentence first.
2. **Apify as the easy version.** "Publish Actors. Get paid." plus "$1.7M paid out last month" is hard to beat for someone who doesn't care where the code runs. TOON has to make *where it runs* and *who holds the money* matter, using its own proof, not fear.
3. **Mastercard Agent Pay for Machines** takes "fractions of a cent". Sub-cent payments alone no longer set TOON apart. TOON's difference is *no credential, no directory, no issuer*.
4. **Olas's "agents you actually own"** already claims ownership of locally run agents. TOON should talk about being *reachable and paid*, not *owned*.
5. **Virtuals `acp serve`** turns handler functions into x402/MPP endpoints. Where they run isn't documented. If they run locally with reachability built in, ACP becomes a direct competitor.

---

## 04 — Messaging analysis

**What the category keeps saying** (table stakes, no longer differentiating):
1. **The HTTP 402 revival story**: "reserved for payments, finally used." x402, L402 and Cloudflare all tell it.
2. **"Agents are here and need to pay"**: "the agents aren't coming", "agentic commerce", "economic infrastructure for AI".
3. **"No signup, no API key, no identity"**: L402 says it word for word, and x402 says "no checkout page, card form, or signup flow". **"No account" alone no longer sets TOON apart.**
4. **The Zero list and the one line**: "zero fees / zero wait / zero friction", "a single line of code", "one command".

**Clichés to avoid**: "internet-native payments", "agentic commerce/economy", "economic infrastructure for AI", "single line of code", "zero fees" (gas and facilitator fees exist), "connect anything, anywhere", "unstoppable", "disrupting the norm", "the future of payments", "the agents are here", and noun stacks like "Access. Identity. Checkout." From part 2: "mandate", "a card and a budget", "agentic commerce, at scale", "trust is the infrastructure", "a new class of payments", "credentialed / verified agents", "agentic GDP", "society of agents", "agent app store / bazaar", "the front door for AI agents", "unified interface", "Zero Trust", "frictionless", the "first live agentic transaction in [country]" press release, and the "Are you an AI agent? Read our agents.md" onboarding move (now done by both ngrok and Apify).

**Phrases already owned**:

| Phrase | Owner |
|---|---|
| "Making Money Move like Data" | Interledger. It is close to TOON's thesis, so say it differently: a single packet *is* the message and the money. |
| "Global Grid. No Off Switch." | Akash |
| "Connect anything, anywhere" | ngrok |
| "Agents pay. Agents get paid. Autonomously." | Nevermined |
| "Publish Actors. Get paid." / "The front door to Apify for AI agents." | Apify |
| "Co-own AI" / "agents you actually own" | Olas |
| "A society of AI agents. With its own GDP." | Virtuals |
| "The Unified Interface For Every Model" | OpenRouter |
| "Agent Pay for Machines" / "fractions of a cent" | Mastercard |
| "Mandate" | Google AP2 |
| "Onion service" / "hidden service" | Tor. TOON's own audience language in context.md uses "hidden service". Keep it out of public copy, because it is Tor's term and reads as darknet. |
| "Aperture" | Both Lightning Labs (L402 proxy) and Tailscale (AI gateway) |

Don't lead with "agents get paid" (Nevermined) or "own your agent" (Olas). When TOON says it routes, say *what* it routes (payments, hop by hop), to stay clear of OpenRouter.

**What nobody is saying**:
1. **"You don't need a server, and you still get paid."** Every payment rail assumes the seller has public hosting. Holepunch, zrok, Tor and Tailscale say "no servers" or "no open port" but nothing about money. Only the combined sentence is free: **"Your machine answers the request and gets paid for it, with no open port and nobody in the middle."**
2. **"Your app never touches the money."** Payment works as a reverse proxy, the way nginx terminates SSL. Aperture does this technically, but nobody brands the idea.
3. **"Nobody in the middle, not even us."** Rivals hold the middle: Coinbase's facilitator, Cloudflare as merchant of record, the Stripe merchant account, ngrok's edge. TOON can say that peering connectors route payment hop by hop.
4. **"Every node can sell."** Stripe, Skyfire and ngrok cast agents as *customers*. Nevermined ("Agents get paid") and Olas do talk about agents earning, but through a platform or a token. Nobody casts agents *and people* as peers who earn directly over plain HTTP.
5. **"Here's what is live, and what isn't."** The category overclaims ("Zero centralization", "60% of the Web", "unstoppable"). Plain honesty would itself stand out.

---

## 05 — Visual identity patterns

**Color trends**: Purple keeps coming back: ngrok `#4a3066`, Lightning `#57038d`, Interledger `#80409d`, Nostr. Near-black backgrounds come with a single neon or warm accent: Akash green `#8BFE79`, Interledger apricot `#ffb259`. Warm oranges and reds are spreading as accents (Skyfire, Lightning, Interledger, Cloudflare). **Overdone**: purple, near-black with a neon accent, gradients. **Watch**: Skyfire's tan `#D9A36A` sits in a warm gradient and is near TOON's gold `#c9a24a`. Nobody uses a muted metallic as the *main* color with charcoal and cream, but TOON can't claim to be "the only warm brand".

Part 2 adds more pressure. **More purple**: Olas `#7e22ce`, Tor `#7D4698`, OpenRouter `#6467f2`/`#7624f4`, Fetch `#4a3aff`. **A new deep-teal cluster**: Nevermined `#0d3f48`, Virtuals `#168389`, Payman `#0e3d42`. **More gold and cream**: Nevermined uses a `#ffd700` gold glow, and Payman sets teal on cream `#f5f3eb`. **Warm charcoal**: Tailscale's `#232222`/`#181717` is close to TOON's charcoal. TOON's gold stays distinct only if it stays **flat** (no glow, no gradient), avoids teal, and leads ahead of the charcoal.

**Typography trends**: Two clusters.
1. **Instrument Serif with mono**: x402 and Akash. An editorial serif paired with JetBrains Mono is fast becoming the "credible protocol" look.
2. **Geometric or grotesk sans**: Inter, Geist, Work Sans, Poppins, Roobert, Söhne.

JetBrains Mono is nearly everywhere (Skyfire, ngrok, Akash), and Inter keeps reappearing (Olas, Apify, Tailscale). **Olas already uses Neue Machina**, a technical display face that looks almost monospaced, so "a mono with character as the main face" is no longer unclaimed. **Fresh space**: a strict, technical grotesk that looks like a spec sheet rather than a magazine, or a mono main face clearly different from Neue Machina.

**Imagery patterns**: Code-snippet heroes (x402, ngrok), logo walls and live stats (x402, Skyfire, Stripe), founder and people photography (Interledger), animated checkout demos (Skyfire), and price comparison tables (Akash). **Nobody shows the operator's machine**: the box under the desk, the home router, the terminal running the service. No one draws the real route a payment takes.

**Design differentiation opportunities**:
- **Warm metal as the main color**: keep the gold `#c9a24a`, charcoal `#2b2f36` and cream `#f3efe6` as the whole palette, not an accent. Don't add purple, neon or gradients. Flat fields will keep it distinct from Skyfire's gradient.
- **Hard pixel geometry**: the existing mark, a packet made of flat rectangles, is unlike every logo here. Carry that grid into diagrams and UI.
- **Draw the route**: literal packet paths through peered connectors, showing currencies changing along the way, as the main explainer graphic.
- **Terminal as hero**: show real `toon` CLI sessions and the branded spinner ("Routing", "Signing", "Settled"), with the machine visible.
- **Don't default to Instrument Serif with mono.** It is becoming the category's new uniform. Also avoid anything that reads like Neue Machina (Olas).
- **No glow on the gold.** Nevermined's `#ffd700` glow is exactly what TOON's gold must not look like.

---

## 06 — Differentiation opportunities

**Opportunity 1: "No server. No domain. No open port. Paid per request."**
- *Why it's available*: Every payment rail assumes public hosting. The brands that host for you are the middleman (ngrok, Cloudflare, Apify), or they never mention money (Holepunch, zrok, Tor, Tailscale).
- *How to take it*: Put the absence and the payment together on the first screen. Either half alone sounds like a tunnel or a payment rail. Prove it with a short, real demo: an app behind a home router answering paid requests. Move before Tailscale can add payment to Funnel.

**Opportunity 2: Payment as a reverse proxy**
- *Why it's available*: Aperture does it for Bitcoin only and nobody brands the idea. x402 and MPP ask the app to integrate middleware.
- *How to take it*: Own the line "*TOON terminates payment the way nginx terminates SSL. Your app gets plain HTTP that's already paid for.*" Make it the main diagram.

**Opportunity 3: Nobody in the middle**
- *Why it's available*: Each rival is the middle: Coinbase's facilitator, Cloudflare as "Merchant of Record", the Stripe merchant account, ngrok's edge, Skyfire's identity gate, Apify holding seller payouts behind KYC, Olas's 15% fee, and the card networks' credentials and directories.
- *How to take it*: Explain hop-by-hop routing between peered connectors that anyone can run, settling on more than one chain. Show the route, not a logo wall. Against Mastercard's "fractions of a cent", the difference is *no credential, no directory, no issuer*, not the price.

**Opportunity 4: Every node can sell**
- *Why it's available*: Agents are framed as shoppers (Stripe, Skyfire, AP2, the card networks) or users (ngrok). Those that let agents earn do it through a platform (Nevermined, Apify) or a token (Olas, Virtuals). L402 comes closest but stays inside Bitcoin.
- *How to take it*: Show agents and people *earning*, with examples like a model behind a router and a scraper agent selling to other agents. Write for operators, not merchants. Avoid "agents get paid" (Nevermined) and "own your agent" (Olas). Talk about being *reachable and paid*.

**Opportunity 5: The honest protocol**
- *Why it's available*: The category overclaims ("Zero centralization", "60% of the Web", "the internet's payment standard", "unstoppable").
- *How to take it*: Put a public "live / next" block on the homepage (devnet, mock USDC, Base Sepolia, Solana devnet), use no superlatives, and show real numbers only once they're real. Make honesty how the brand sounds, not a footnote.

**Opportunity 6: The coherent brand for what DVMs point at**
- *Why it's available*: The idea of running a service on your own machine for pay already has believers on Nostr and no brand.
- *How to take it*: Be its clear, HTTP-native, not-tribal face. Recruit Nostr builders without tying the brand to one currency.

---

## 07 — Strategic implications

**Positioning recommendation**: Stand alone in the **sovereign, both-hosts-and-charges** quadrant. TOON is not "another 402 rail" and not "another tunnel": it is the only option where the operator's own machine is both reachable and paid, with nobody in the middle. Acknowledge x402, L402 and MPP as neighbors, saying plainly how TOON relates to each, since x402 and MPP are now what people search for. Don't try to win their 402 story. Name the two nearest comparisons directly. **Apify** hosts and pays you, but on its servers and from its account. **Olas** runs on your machine, but pays through a token marketplace that takes a cut. The frame: *they charge at a door you rent; with TOON your machine is the door.*

**Messaging direction**: Lead with the operator's outcome and what's absent. *"Your app or agent runs on your machine and gets paid for every request. No server, no domain, no open port."* Then the mechanism (the reverse-proxy analogy), then the thesis, phrased in TOON's own words so it isn't mistaken for Interledger's "money move like data". For example: *"Every packet carries its own payment."* Don't lead with "no account", since L402 and x402 already say it. Don't lead with sub-cent pricing either, since Mastercard says it. Never separate "no open port" from "paid per request".

**Visual direction**: Gold, charcoal and cream as the whole palette, in flat fields with no gradients. Hard-edged pixel geometry from the mark. Literal route diagrams and real terminal sessions as imagery. A main face with a technical, spec-sheet character, avoiding the Instrument Serif and JetBrains Mono uniform and anything close to Olas's Neue Machina. Charcoal for dark mode, never purple, teal, or near-black with neon. Lead with gold so the charcoal doesn't read as Tailscale's.

**What to avoid**:
- Opening with the HTTP 402 origin story. It belongs to x402 and Cloudflare.
- "Internet-native", "agentic commerce", "single line of code", "zero fees", "the agents are here", "unstoppable".
- Purple, teal, neon-on-black, gradients, warm gradients that would look like Skyfire, and gold glow that would look like Nevermined.
- "Hidden service", "mandate", "agents get paid", "own your agent", "unified interface", "fractions of a cent". These are now other brands' words.
- Logo walls and big headline stats before there are real ones. One overclaim breaks the honesty position.
- Bitcoin-first or token-first framing (the L402 and Akash trap), or policy-mission framing (the Interledger trap).
- Competing on "cheaper". Sovereignty is the claim, not price.

---

## Sources

- x402: [x402.org](https://www.x402.org/) · [Coinbase x402 docs](https://docs.cdp.coinbase.com/x402/welcome) · [Linux Foundation launch](https://www.linuxfoundation.org/press/linux-foundation-announces-operational-launch-of-x402-foundation-to-standardize-internet-native-payments-for-ai-agents-and-applications)
- Lightning: [lightning.engineering](https://lightning.engineering) · [L402 docs](https://docs.lightning.engineering/the-lightning-network/l402) · [L402 for agents](https://lightning.engineering/posts/2026-03-11-L402-for-agents/) · [Lightning Agent Tools](https://lightning.engineering/posts/2026-02-11-ln-agent-tools/) · [NIP-57](https://github.com/nostr-protocol/nips/blob/master/57.md)
- Interledger: [interledger.org](https://interledger.org) · [openpayments.dev](https://openpayments.dev) · [webmonetization.org](https://webmonetization.org) · [rafiki.dev](https://rafiki.dev)
- Cloudflare: [Tunnel docs](https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/) · [Pay per crawl](https://blog.cloudflare.com/introducing-pay-per-crawl/) · [Monetization Gateway (RuntimeWire)](https://runtimewire.com/article/cloudflare-monetization-gateway-x402-ai-agents)
- ngrok: [ngrok.com](https://ngrok.com) · [ngrok blog](https://ngrok.com/blog)
- Stripe: [stripe.com](https://stripe.com/) · [Sessions 2026 recap](https://stripe.com/blog/everything-we-announced-at-sessions-2026) · [Tempo launch (Decrypt)](https://decrypt.co/361573/stripe-backed-tempo-network-launches-ai-agent-payments)
- Akash: [akash.network](https://akash.network) · [Q4 2025 report](https://akash.network/blog/q4-2025-report/)
- Skyfire: [skyfire.xyz](https://skyfire.xyz/) · [KYAPay launch](https://www.streetinsider.com/Business+Wire/Skyfire+Launches+Open+KYAPay+Protocol+With+Agent+Checkout/24981183.html)
- Holepunch: [holepunch.to](https://holepunch.to) · [pears.com](https://pears.com)
- Part 2 brands (AP2, Visa, Mastercard, Nevermined, Olas, Virtuals, Tailscale, zrok, Tor, Apify, OpenRouter): see the Sources list in [competitors-more.md](competitors-more.md).
