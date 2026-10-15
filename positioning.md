# Brand Positioning: TOON Protocol

*Drafted 2026-10-15 from [context.md](context.md), [competitors.md](competitors.md) and [competitors-more.md](competitors-more.md). Stage: live on Base and Solana mainnet through the project's node, with devnet for testing. Brand ambition was not captured anywhere, so section 03 assumes it: in five years, TOON should be the default way to run a paid service from your own machine. Correct this if it's wrong. This package is the source of truth for the brand. The current website's copy is a draft to be rewritten from it, but the product facts and the terms defined in `toon_cli/CONTEXT.md` constrain it.*

---

## 01 — Category definition

**Stated category**: An open payments and hosting protocol for apps and agents. That's how context.md puts it, and it's accurate, but it's two categories joined with "and".

**Actual category**: A developer comparing options sees two separate shelves:
- *"How do I charge per request?"* compares TOON with x402, L402, Stripe MPP and Apify. In 2026 that shelf is the most crowded and best-funded in infrastructure.
- *"How do I make my local thing reachable?"* compares TOON with ngrok, Cloudflare Tunnel, Tailscale Funnel and zrok. On that shelf TOON looks like a tunnel with extra steps.

TOON loses on either shelf alone. Against x402 it has no traction and no Linux Foundation. Against ngrok it has no install base and no "one command" fame.

**Opportunity category**: **Paid self-hosting**, meaning a service on your own machine that is reachable and paid for per request, with no company in the middle. Today people build this from three products: a tunnel, a payment rail and a public server. Nobody sells it as one thing. The nearest attempts each give up something the category needs. Apify gives up *self*, because it runs your code on its servers. Olas gives up *direct*, because it pays through a token and takes 15%. Nostr DVMs give up *brand*: nobody owns them.

**Recommendation**: Position in **paid self-hosting**. It's the only framing where both halves of TOON count *for* it instead of splitting it. Don't let it read as "agent payments", which is a shelf TOON can't win yet. x402 is part of how TOON works: every TOON channel is an x402 batch-settlement channel on x402's own audited contract, and a stock x402 client can open one. So x402 is a layer TOON builds on, not a rival, and TOON's difference is everything x402 assumes away (reachability, routing, the operator's own machine). Mention L402 as a relative. Neither is the frame. In copy, say what the category does rather than its name: *"Run it on your machine. Paid for every request."* A category label works internally, but a new category label on a homepage is jargon.

---

## 02 — Competitive landscape mapping

This uses the same axes as competitors.md section 03, because they're the axes the decision actually turns on.

**Axis 1 (horizontal)**: Intermediated ← → Sovereign. *Is a company in the request path or holding the money?*
**Axis 2 (vertical)**: Charges at the door ← → Hosts the door. *Does it only add payment to a server you already have, or does it also make you reachable?*

| Brand | Position | Territory it owns |
|---|---|---|
| **x402** (Coinbase → LF) | Intermediated (in practice, Coinbase's facilitator) · charges only. TOON settles on x402 channels, so this is a layer under TOON as much as a competitor | *The HTTP 402 standard* |
| **Stripe MPP / Tempo** | Far intermediated · charges only | *Payments done properly, for businesses* |
| **Cloudflare** (Tunnel + Monetization) | Far intermediated · both, but as merchant of record and on a waitlist | *The toll booth of the web* |
| **ngrok / Tailscale Funnel** | Intermediated · hosts only, and bills *you* | *Getting localhost onto the internet* |
| **Apify** | Intermediated · both, on its servers, with its payouts | *Publish Actors. Get paid.* |
| **Lightning L402** | Sovereign · charges only, Bitcoin only | *Bitcoin as machine money* |
| **Olas** | Mostly sovereign · runs on your machine and earns, through a token with a 15% fee, and isn't HTTP-reachable | *Agents you actually own* |
| **zrok / Tor / Holepunch** | Sovereign · hosts only, with no payment | *Self-hosted, no open port* |

**Where TOON sits**: Far top-right, sovereign *and* both. It's the only branded position there.

**Unclaimed territory**: The corner where the operator's own machine is both the endpoint and the business. Each neighbour has one edge of it. L402 has sovereign payment, zrok has sovereign reachability, Apify has hosting plus payment, and Olas has on-device earning. Nobody has all four.

**Who could move in**: Tailscale is the most likely. Adding payment to Funnel would be a single product step, and it already has the home-machine installs. Second is Virtuals `acp serve`, if its endpoints turn out to run locally. TOON's window is the time before either of them states the sentence.

---

## 03 — Positioning territory

**The Space**: Your machine is the business. Whatever you run on it can be reached and gets paid, with no one standing between you and the person or agent paying.

**The Audience Owned**: Independent developers and agent builders who already run something useful on their own hardware, like a model, a scraper or a small API, and want it earning per request without renting a server, opening a port or signing up with a payment company.

**The Competitive Moat**: The incumbents can't take this position without dropping their business model. Coinbase, Cloudflare, Stripe, ngrok and Apify make money by *being* the middle, and "nobody in the middle, not even us" contradicts their revenue. The technical moat is the combination: payment terminated in a proxy the operator runs, packets that carry their own claims, and hop-by-hop routing across peered connectors that changes token on the way. Each piece has prior art (Aperture, Interledger), but assembling them behind a home router as one binary is the hard part. Tailscale is the exception. It *could* take the position, which is why TOON has to own the sentence and the open, multi-connector version first.

---

## 04 — Positioning statement

**Framework version**
> For independent developers and agent builders running services on their own machines, **TOON** is the open network that makes those services reachable and paid for every request, with no server, no open port and no company in the middle, because the connector on your machine terminates payment the way nginx terminates SSL and routes it hop by hop between peers anyone can run.

**Strategic version (internal)**
> TOON owns *paid self-hosting*: the only position where the operator's machine is both the endpoint and the business. We beat payment rails by also solving reachability, and we beat tunnels by also solving revenue. We beat the platforms that do both (Apify, Cloudflare, Olas) by not being the middle. Every decision should make "your machine, paid directly" more true, and it should never make TOON a party to the money.

**Human version (public)**
> Run your app or agent on your own machine. TOON gets every request to it and makes sure each one is paid. You don't need a server, a domain, an open port or anyone's permission. Your app just sees ordinary HTTP that's already been paid for.

---

## 05 — Positioning proof points

Each proof is marked **live** (true today, on mainnet unless it says devnet) or **owed** (still has to be shown). Under the honesty value, only the live ones go in public copy.

- **Proof 1: Payment terminates in a proxy, and the app is plain HTTP.** The connector checks payment before forwarding, so the app has no SDK, no wallet and no billing code. *Live* (the connector design). This supports "your app never touches the money."
- **Proof 2: One binary runs the whole node.** `toon` *is* the connector (ADR 0001). `toon up` starts it as a supervised `systemd --user` service, and every command is non-interactive and returns `--json`. *Live* (toon_cli v0.1.0 release for Linux x86_64/aarch64). This supports "from your own machine" without an ops burden, and "agents can operate it."
- **Proof 3: Packets carry their own claim.** No invoice, no settle round trip and no facilitator call per request. *Live* in the protocol. This supports "no company in the middle" for each request.
- **Proof 4: Multi-hop, multi-token routing on more than one chain.** Settlement runs in USDC on Base mainnet and Solana mainnet, with Base Sepolia and Solana devnet for testing. *Live on mainnet.* The site's own Arweave write was bought through the mainnet node over two paid hops, and its receipts are on the proof page. Token conversion along the route is shown on devnet. This supports "not tied to one chain or one company," which separates TOON from L402 (Bitcoin only) and x402 (in practice, Coinbase).
- **Proof 5: A paid request answered from behind a home router.** *Live, shown on devnet.* A new TOON app is a hidden service by default, at an `.anyone` address inside the Anyone overlay, so it needs no open port. A public, reproducible demo shows it: an app in a VM behind NAT, with no port forwarded and every listener on loopback, paid from a Linode on another network through the devnet relay. The claim settled on Base Sepolia ([demo](https://github.com/toon-protocol/echo-merchant/tree/main/demo/behind-nat), [settlement tx](https://sepolia.basescan.org/tx/0x4b7f7860e3485d438008c7abcc77286f80a18aba3645395adc66ff72b54ff21a)). It's one run, on devnet with test USDC, through a relay the project runs. Say "shown on devnet" where it matters.

---

## 06 — What this brand refuses to be

- **TOON is not for people who want someone else to run their code.** If you'd rather upload and forget, Apify is the honest recommendation. TOON is for people who want the machine to be theirs.
- **TOON will never compete on price or on "zero fees".** There's gas, and operators set their own prices. The claim is *sovereignty*, not cheapness. That's also the Akash trap.
- **TOON will never hold the money.** No custody, no merchant of record, no payout schedule, no take rate on the protocol. If a product decision needs TOON in the middle, it's the wrong decision.
- **TOON does not try to be the HTTP 402 standard or an "agentic commerce" brand.** It settles on x402 and doesn't retell x402's or L402's story. It isn't a token, a marketplace or an "agent app store".

---

## 07 — Positioning in one sentence

> **TOON makes the app or agent on your own machine reachable and paid for every request, with no server, no open port and no company in the middle.**

*(25 words.)*

---

## Red flags

1. **"No company in the middle" needs care.** Connectors *are* in the path, and on devnet a new agent node peers toward the project's connector, and the live mainnet node is the one the project runs. If that connector, the mainnet node and today's other connectors are all run by the TOON team, a critic will say so. Each packet still carries its own claim and the protocol takes no fee, but that's an argument, not an absence. Channel deposits are also relayed through an x402 facilitator (`facilitator_url` in the connector config), so "no facilitator" is only true per request, not per channel. The defensible wording is *"no company you have to sign up with, and anyone can run a connector."* Put the number of independent operators in the live/next block once it's above zero.
2. **"No open port" is shown on devnet, not on mainnet** (Proof 5 above). The [public demo](https://github.com/toon-protocol/echo-merchant/tree/main/demo/behind-nat) is one run with test USDC, through the project's relay. It's the headline differentiator, so link the demo wherever the claim leads, and say it's devnet.
3. **"Gets paid" is true, on one node.** Mainnet settlement is live on Base and Solana, and the proof page has real receipts. But the live node is the project's own, and four priced apps aren't a market. Public copy can say "paid" in the present tense with a visible **live: Base and Solana mainnet · devnet for testing** label and a link to a receipt. It must not imply traffic, earnings or operators that aren't shown, or it breaks the honesty value it relies on. That's especially true because overclaiming is the category's main weakness and TOON's chance to stand out.
4. **Either half on its own is a table stake.** "No account" belongs to L402 and x402, "no open port" to zrok and Tor, and "sub-cent" to Mastercard. The position only holds when *reachable* and *paid* appear in the same sentence. Any page or tagline that drops one half falls back into a crowded shelf.
5. **The audience is narrow on purpose, but check it.** "Already runs something useful on their own hardware" is a small group today. That's acceptable for an early protocol. If growth needs a wider audience later, widen to *what people run*, not to *where it runs*.
