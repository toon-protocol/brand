# Brand Story: TOON Protocol

*Drafted 2026-10-15 from [context.md](context.md), [positioning.md](positioning.md), [audience.md](audience.md), [messaging.md](messaging.md) and [voice.md](voice.md), plus the maintainer's answers: the origin is the moment "sending a message and sending money are the same action" clicked, the background is payment protocols (Interledger) and Nostr, and the story is told by the founder in the first person. Every product claim below is live unless it's labeled. The story contains no invented anecdotes, so personal detail is left to the maintainer (see "Details that would sharpen it" at the end).*

**Villain**: the middle. That's the stack of accounts and companies a small service has to pass through before anyone can pay it: a tunnel or a rented server, a domain, an open port, a payment processor, billing code and a payout schedule. Each piece is a reasonable product. Together they make charging for a small thing harder than building it, and none of them work when the caller is an agent with no card.

**Hero**: the operator, who already runs something useful on their own machine. TOON is the guide: it removes the middle and gets out of the way.

---

## Version 1: The long story (About page)

### Why I built TOON

I spent years in two worlds that didn't talk to each other.

In Interledger, a payment is a packet. A connector takes it, checks it and forwards it to the next hop, until it reaches whoever it was for. In Nostr, a note is a signed message. A relay takes it, stores it and passes it on to whoever asks. I worked on both, and for a long time I filed them in different drawers: one was money, the other was messages.

Then the drawers stopped making sense. A packet that carries a message can carry the payment for that message too. If every packet pays for itself, whatever answers it doesn't need an invoice, an account or a billing system. It checks the claim and answers. Sending a message and sending money are the same action.

That idea is the whole of TOON. Everything else is making it work on a real machine.

### What it actually takes today

Meanwhile, here's what it takes to charge for a small service. Say you've fine-tuned a model, or written a useful API, or built an agent that does one job well. It already runs on your machine. A few people want to use it.

To charge them, you rent a server or a tunnel. You buy a domain. You open a port on your router, or pay someone so that you don't have to. You sign up with a payment processor, write billing code and a pricing page, and wait for a payout. That's 3 products and a business, just to answer a request that someone wants to pay for. And if the caller is an agent, most of it falls apart, because the agent has no card, no email and no way to click "I agree".

None of those companies are doing anything wrong. They make money by being the middle. But for a small service the middle is bigger than the service, so most small useful things never get priced at all. They run for free, or they're switched off.

### What I built instead

So I put the two ideas together and built the piece that was missing.

A connector sits on your machine, in front of your app. It handles payment the way nginx handles SSL. An unpaid request is refused with the price, and a paid one is passed on as plain HTTP. Your app never touches the money: no SDK, no wallet and no billing code. It answers HTTP, like it always has.

Payments route hop by hop between peered connectors, the way Interledger routes packets, and they can change token along the way. Each packet carries its own claim, so there's no invoice and no settle round trip per request. Settlement runs on x402 channels, in USDC on Base and Solana. Interledger routes and x402 settles. I didn't invent either one. What TOON adds is putting them together on your own machine, as one binary.

By default a new TOON app is reachable as a hidden service, with no open port and no public address, so it can sit behind a home router. That's been shown on devnet: in a [public demo](https://github.com/toon-protocol/echo-merchant/tree/main/demo/behind-nat), an app in a VM behind NAT, with no port forwarded, answered a paid request from another network, and the payment [settled on Base Sepolia](https://sepolia.basescan.org/tx/0x4b7f7860e3485d438008c7abcc77286f80a18aba3645395adc66ff72b54ff21a). You set the price. Nobody takes a cut, because there's no protocol fee and no company you have to sign up with. Anyone can run a connector.

### Who it's for

TOON is for people who run their own stuff. You have a GPU in a closet, or a mini PC, or a Pi on a shelf. You'd never call yourself a business. You just want the thing you built to pay for its own power bill, without renting a server to put a paywall in front of it.

It's also for agents. They read the docs, run the CLI and pay other agent nodes. Every `toon` command is non-interactive and prints JSON, so an agent can operate an agent node as easily as you can.

### Where it is now

TOON is live on mainnet. The project's agent node settles in USDC on Base and Solana, and 4 apps are priced on it. The site you're reading is stored on Arweave, and that write was paid for through the mainnet node. The receipts are on the proof page and check against a public chain. Devnet runs on test tokens for anyone who wants to try it first.

What isn't there yet: independent operators on mainnet. Right now the live mainnet node is the one the project runs. That's the next thing, and when there are more I'll give you the number, not an adjective.

### What I'll keep doing

Here's what you can hold TOON to:

- **Say what's live and what isn't.** Mainnet is mainnet. Devnet is devnet. If I can't show it in a terminal or point to it in the source, it doesn't go on this site.
- **Stay out of the middle.** TOON doesn't host your code, hold your money or take a cut. It's MIT licensed with no protocol fee, and anyone can run a connector.
- **Keep your app plain.** Your app speaks HTTP. It should never need to know it's being paid for.
- **Build for agents as well as people.** Every command takes `--json`, prints one JSON document and exits with a documented code.

Your machine, your price. Every request that reaches your app is already paid for.

*Jonathan Green*

---

## Version 2: The short story (homepage or pitch)

I worked on Interledger, where a payment is a packet that connectors forward hop by hop, and on Nostr, where a note is a signed message that relays pass on. One day they stopped looking like two things. A packet can carry a message and the payment for it at once. Sending a message and sending money are the same action.

Meanwhile, charging for a small service still takes a rented server, a domain, an open port, a payment processor and billing code. For most small things the middle is bigger than the service, and none of it works for an agent with no card.

So I built TOON. A connector on your machine handles payment the way nginx handles SSL: unpaid requests are refused with the price, and paid ones reach your app as plain HTTP. Payments route hop by hop between connectors and settle in USDC. There's no protocol fee and no company to sign up with.

It's live on Base and Solana mainnet, with devnet for testing. Your machine, your price.

---

## Version 3: The one-liner origin

> "I built TOON because, after years on Interledger and Nostr, I saw that sending a message and sending money are the same action, so getting paid for a request should take no more than answering it."

*(36 words.)*

---

## Usage notes

- **Where each version goes**: Version 1 is the About page. Version 2 is a homepage section below the hero, a pitch opener or a talk intro. Version 3 is for podcasts, bios, the first reply in a thread and the opening line of a talk.
- **Live label**: Any page carrying Version 1 or 2 also carries **live: Base and Solana mainnet · devnet for testing** (see [messaging.md](messaging.md)).
- **Paid channels**: "behind a home router" and "no open port" describe the live mechanism, and the [home-router demo](https://github.com/toon-protocol/echo-merchant/tree/main/demo/behind-nat) shows it on devnet. They can lead in ads and headlines if the demo is linked and the copy says devnet. "Hidden service" stays out of headlines, and in body copy it's glossed on first use, as [voice.md](voice.md) requires.
- **Update triggers**: when independent mainnet operators exist, replace the "Where it is now" paragraph with their number. When the home-router demo runs on mainnet, drop "on devnet" from "What I built instead" and update the link.
- **Third-person adaptation**: for press or partner pages, change "I" to "Jonathan Green" on first mention and use the pronouns Jonathan states after that. Don't guess them.

## Details that would sharpen it

The story uses only facts in this package and the maintainer's answers. These specifics would make Version 1 stronger, and only the maintainer can supply them:

1. **The actual moment.** Where were you, and what were you building when message and money merged? A specific project, a bug or a conversation would replace "Then the drawers stopped making sense" with a real scene.
2. **What you worked on.** Name the Interledger and Nostr work (projects, roles, years) in one sentence. It's the earned confidence.
3. **The first paid request.** What was the first thing priced on TOON, and what did the first real payment feel like? That's the strongest possible "where it is now" detail.
4. **Sign-off.** Confirm the name and title, for example "Jonathan Green, maintainer".
