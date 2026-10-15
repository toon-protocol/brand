# Brand Guidelines: TOON Protocol

*Compiled 2026-10-15 from [context.md](context.md), [positioning.md](positioning.md), [messaging.md](messaging.md), [voice.md](voice.md), [identity.md](identity.md), [architecture.md](architecture.md), [audience.md](audience.md) and [story.md](story.md). This file collects decisions; it doesn't make new ones, except where a rule was missing and is marked **set here**. When this file and a source file disagree, the source file wins and this file gets fixed. Product terms in `toon_cli/CONTEXT.md` win over both.*

---

# Part 1 — Brand foundation

## 01 — About this guide

This is the one page to open before you design, write or name anything for TOON. It's for anyone who makes something public with TOON's name on it: designers, people writing the website, docs or READMEs, people posting for the project, maintainers naming a new repo, and agents doing any of that. Each section gives the rule and the reason in a line, then links to the full decision. If a rule here doesn't cover your case, follow the source file it links to. If that doesn't cover it either, open an issue on `toon-protocol/brand` before you ship.

## 02 — Brand essence

**Mission**: Make getting paid as simple as answering a request, so anyone, person or agent, can run a service from their own machine and earn from it directly.

**Vision**: The default way to run a paid service from your own machine. *(Assumed in positioning.md section 03; not yet confirmed.)*

**Values**

| Value | What it means in practice |
|---|---|
| **Sovereignty** | Your machine, your price, nobody's permission. TOON never holds the money. |
| **Openness** | Open protocol, MIT-licensed code, no protocol fee, free reads. Anyone can run a connector. |
| **Honesty** | Say what is live and what is next in the same breath as the claim. Let the node describe itself. |
| **Simplicity** | Plain HTTP at the edge, one binary, one config file. |

**Personality**: direct · exact · independent · unhyped · practical

**Positioning statement**
> For independent developers and agent builders running services on their own machines, **TOON** is the open network that makes those services reachable and paid for every request, with no server, no open port and no company in the middle, because the connector on your machine terminates payment the way nginx terminates SSL and routes it hop by hop between peers anyone can run.

**In one sentence**: TOON makes the app or agent on your own machine reachable and paid for every request, with no server, no open port and no company in the middle.

**The test every page has to pass** (internal): *Your machine is the business.* If a page drops *reachable* or drops *paid*, it reads as a tunnel or a payment rail and loses the position.

**What TOON refuses to be**: a host for other people's code, a cheaper option, a holder of anyone's money, an "agentic commerce" brand, a token, a marketplace. See [positioning.md](positioning.md) section 06.

**Origin story**: told by the founder in the first person, in three lengths, in [story.md](story.md). The thesis it carries: *sending a message and sending money are the same action.*

---

# Part 2 — Visual identity

Full brief: [identity.md](identity.md). Files: [`assets/`](assets/).

## 03 — Logo

**Primary mark: the packet symbol.** Two upright bars on a thin line. The Ink bar with a small Paper square is the message header, the Gold bar is the value, and the Wire-grey line is the route it travels on. It means exactly one thing: a packet that is the message and the money at once. Don't redraw it.

**Wordmark**: `TOON` in capitals, IBM Plex Sans Condensed Bold, outlined to paths, tracking −1%, one O outline used twice. "Protocol" is never part of the logo. Where it's needed, set it separately in Plex Mono Regular at 40% of the wordmark's cap height, in Wire.

**Approved variations**

| Variation | Use | Light | Dark |
|---|---|---|---|
| Full mark | 64px and larger | `toon-icon.svg`, `toon-icon-tile.svg` | `toon-icon-dark.svg`, `toon-icon-tile-dark.svg` |
| Two-bar mark (no wire) | 24–48px, avatars | `toon-icon-small.svg`, `toon-icon-small-tile.svg` | `toon-icon-small-dark.svg`, `toon-icon-small-tile-dark.svg` |
| Pixel mark | 16px favicon, always on a tile | `toon-icon-16.svg` | `toon-icon-16-dark.svg` |
| Wordmark | Text-only placements | `toon-wordmark.svg` | `toon-wordmark-dark.svg` |
| Horizontal lockup | Headers, README, OG image | `toon-lockup.svg` | `toon-lockup-dark.svg` |
| Stacked lockup | Square avatars only | not drawn yet | not drawn yet |

`toon-wordmark-squared-o.svg` is a rejected exploration (it reads as "T00N" at 24px). Don't use it.

**Dark backgrounds**: use the `-dark` files. On Night, the header bar turns Paper and its square turns Night. The Ink bar is 1.23:1 on Night and disappears.

**Single colour** (stamp, emboss, terminal): all Ink on light, all Paper on dark, with the header square knocked out.

**Clear space** (**set here**): at least one bar width on every side of the mark or lockup. That's the same unit as the gap between symbol and wordmark in the lockup, so nothing else gets closer to the mark than the wordmark does.

**Minimum size**

| Asset | Minimum |
|---|---|
| Full mark | 64px. Below that, switch to the two-bar mark |
| Two-bar mark | 24px |
| Favicon | 16px, the pixel-placed file only, never a scaled-down larger mark |
| Wordmark and lockup | 24px tall on screen (**set here**, from the 24px legibility test in identity.md) |

**Incorrect usage**
- Don't stretch, skew, rotate or redraw the mark.
- Don't add drop shadows, glow, gradients or metallic shading, especially on the Gold bar.
- Don't outline the mark or wordmark.
- Don't put it inside a circle, hexagon or any other container shape (a square tile from `assets/` is the only container).
- Don't recolour it outside Ink, Paper, Gold and Wire, and don't use the light file on a dark background.
- Don't scale the full mark below 64px; the wire and the gap between the bars disappear.
- Don't place it on a busy photo without a Paper or Night tile behind it.
- Don't add "Protocol", a tagline or a product name inside the lockup.
- Don't give a core component (connector, relay, store) its own logo. Name it in Plex Mono beside the master mark instead.
- Don't let a built-on-TOON app use the symbol as its logo. It may use the "runs on TOON" badge.
- Don't draw a mascot. "TOON" invites one, and saying no is a positioning choice.

## 04 — Colour palette

The four brand colours are Gold, Ink, Paper and Wire. Night, Gold text and the state colours are functional. CMYK and Pantone values haven't been chosen yet (see section 22).

**Primary**

| Name | Hex | RGB | CMYK | Pantone |
|---|---|---|---|---|
| Settlement gold | `#c9a24a` | 201 162 74 | not set | not set |

**Secondary**

| Name | Hex | RGB | Role |
|---|---|---|---|
| Ink | `#2b2f36` | 43 47 54 | Text and the header bar on light. Raised surfaces in dark mode |
| Wire | `#6b6f76` | 107 111 118 | Lines, rules, diagram wires, secondary labels |
| Gold text | `#7d5f17` | 125 95 23 | Gold when it has to be text on Paper or white: prices, links |

**Backgrounds**

| Name | Hex | RGB | Role |
|---|---|---|---|
| Paper | `#f3efe6` | 243 239 230 | Primary background. Text on dark |
| Night | `#1c1f24` | 28 31 36 | Dark mode and terminal background |

**State colours** (UI and terminal only, never in marketing graphics)

| State | On Night | On Paper |
|---|---|---|
| Running / ok | `#6cc08a` | `#2f7a4c` |
| Error | `#e07067` | `#b23b32` |
| Paid / settled | Gold `#c9a24a` | Gold text `#7d5f17` |
| Refused (with price) | Ink-dim `#9aa0ab` | Wire `#6b6f76` |

A refusal is a value, not a failure, so it's never red.

**Usage rules**
- **Light leads.** Homepage, social cards and decks default to Paper. Night is for terminals, the CLI and docs in dark mode.
- **Gold means paid**, everywhere in the architecture, endorsed products included. Use it on 10–20% of a layout at most, as flat fills: the value bar, a price, the active route, one key number.
- **Gold is never text on Paper or white** (2.09:1). Use Gold text `#7d5f17` instead. Gold on Ink or Night is fine for text.
- **One gold.** The website's old dark-mode accent `#d9b65c` and the spinner's old `#a8842c` are retired.
- **Never add** purple, teal, neon green, blue links, gradients or a second gold.
- Core components get no colour of their own. Colour-coding the stack would teach readers that it's a dozen separate products.

**Contrast** (WCAG 2.x, measured)

| Pair | Ratio | Allowed for |
|---|---|---|
| Ink on Paper | 11.71:1 | All text |
| Paper on Night | 14.40:1 | All text |
| Gold on Night | 6.89:1 | All text |
| Gold on Ink / Ink on Gold | 5.60:1 | All text, e.g. a price chip |
| Gold text on Paper | 5.20:1 | All text |
| Ink-dim on Night | 6.29:1 | All text |
| Wire on Paper | 4.40:1 | Large text (24px+, or 19px bold) and graphics only |
| Wire on Night | 3.27:1 | Graphics only |
| Gold on Paper | 2.09:1 | Fills only, never text |

Body text needs 4.5:1. Large text and meaningful graphics need 3:1.

## 05 — Typography

**Primary typeface: IBM Plex Sans**, with **IBM Plex Sans Condensed** for display. A grotesk drawn for engineering documents: it reads like a datasheet. Free under SIL OFL. Weights used: Regular 400, SemiBold 600, Bold 700.

**Secondary typeface: IBM Plex Mono.** Every command, flag, path, address, hash, price, amount and status label. Weights used: Regular 400, Medium 500.

**Type hierarchy** (web)

| Level | Typeface | Weight | Size | Usage |
|---|---|---|---|---|
| Display / H1 | Plex Sans Condensed | Bold 700 | 56–72px, line-height 1.0 | Hero headline. Sentence case, tracking −1% |
| H2 | Plex Sans Condensed | SemiBold 600 | 32–40px | Section headlines |
| H3 | Plex Sans | SemiBold 600 | 20–24px | Subheads |
| Body | Plex Sans | Regular 400 | 17–18px, line-height 1.55 | Prose. 68 characters per line at most |
| Code and numbers | Plex Mono | Regular 400 / Medium 500 | 0.92em of body | Commands, prices, amounts, addresses |
| Label | Plex Mono | Medium 500 | 12–13px, uppercase, tracking +6% | Eyebrows, live/next chips, mainnet/devnet tags. The only uppercase text |
| Caption | Plex Sans | Regular 400 | 14px, line-height 1.45 (**set here**) | Figure captions, footnotes, source lines. In Wire only at 24px+; otherwise Ink |

**Rules**
- Sentence case for every headline, button and nav item.
- Emphasis comes from weight or Gold, never italics in marketing.
- Prices and amounts are always set in Plex Mono, with their unit or token.
- **Fallback stack** (**set here**):
  - Sans: `"IBM Plex Sans", system-ui, -apple-system, "Segoe UI", Roboto, sans-serif`
  - Condensed: `"IBM Plex Sans Condensed", "IBM Plex Sans", system-ui, sans-serif`
  - Mono: `"IBM Plex Mono", ui-monospace, "SFMono-Regular", Menlo, Consolas, monospace`
- **Never use**: Instrument Serif or any editorial serif, JetBrains Mono, Inter, Geist, Söhne, Space Grotesk, Archivo Black, Neue Machina, Poppins, Circular.

## 06 — Imagery

**Photography**: Documentary, like a hardware review. Natural light, a real desk, nothing staged. Subjects are the operator's own machine (a mini PC under a desk, a laptop on a shelf, a Raspberry Pi beside a home router with its lights on), real terminal sessions, and optionally hands at a keyboard with no faces. The home router is the hero object, because it's the thing TOON says you don't have to open. Colour is natural and slightly warm, with lifted blacks and no teal/orange grade.

**Terminals**: Real `toon` sessions with real output, in Plex Mono on Night. Never a mock-up with invented output.

**Illustration: the route diagram.** It replaces all abstract "network" imagery. One packet travels from payer to app, hop by hop. Agent nodes are small Ink blocks, wires are Wire grey, and the packet is drawn as the mark itself. A token change shows as a new label on the value bar, in Plex Mono. A hop fee shows as a sliver of Gold left at the connector. Routing is orthogonal (horizontal, vertical, 45°), flat and unshaded.

**Iconography**: 24×24 grid, 2px stroke at 24px and 1.5px at 16px, square caps, mitred joins, only 0° and 90° angles (45° for arrowheads). Filled rectangles for things that hold value (channel, wallet), outlines for everything else. Until the custom set of about 20 icons exists, use Lucide with `stroke-linecap: square; stroke-linejoin: miter`, and no second icon library.

**Avoid**: glowing globes and data streams, robot hands, humanoid AI, server aisles with blue LEDs, hooded hackers, matrix rain, 3D coins or tokens, `$` signs, lightning bolts, clouds, tunnels, chain links, circuit traces, hexagons, constellation-of-nodes graphics, AI-generated "futuristic" scenes, beach-laptop lifestyle shots, logo walls.

## 07 — Design principles

1. **Show the machine.** Open on something real: the box, the router, the terminal. If the design could illustrate any cloud company's page, it's wrong.
2. **Draw the route, not the network.** One exact path with its price and token beats a thousand implied ones.
3. **Flat and exact.** Flat fills, hard edges, one gold. No gradients, glow, blur, glass or shadows.
4. **State is part of the design.** Live/next chips, mainnet/devnet tags and real prices are set in Plex Mono uppercase, in a Wire-outlined chip, placed prominently.

---

# Part 3 — Verbal identity

Full guide: [voice.md](voice.md).

## 08 — Brand voice

**Voice essence**: TOON sounds like an engineer who runs the thing they're describing: direct, exact and unhyped.

**Tone dimensions**

| Dimension | Where TOON sits |
|---|---|
| Formality | Slightly casual, never loose. Plain words, spec-level precision about names and numbers |
| Energy | Calm. Confidence comes from specifics, not intensity |
| Humour | Serious, with at most one dry line per page. Funny only by being exact |
| Expertise | Authoritative about the mechanism, plain in the words. One familiar comparison, then the exact term |
| Warmth | Second person and respectful. "Your machine, your price." On the operator's side, never chummy |

**Voice qualities**

| Quality | Do | Don't |
|---|---|---|
| **Direct** | "`toon up` installs a `systemd --user` service, so your agent node keeps running after you close the terminal." | "To make things easier for you, we've built a handy way to keep your node running in the background!" |
| **Exact** | "Every command that pays states its amount and needs `--yes`." | "Payments are safe and you're always in control." |
| **Honest about state** | "Mainnet on Base and Solana. Devnet for testing; the faucet funds it with test tokens." | "Start earning today." |
| **Unhyped** | "No protocol fee." | "Zero fees, zero friction, unlimited potential." |
| **Independent** | "No cloud · no domain · no open port." | "Unlike greedy Big Tech platforms…" |
| **Practical** | "Your agent node is peered. Next, put an app behind it:" and the command | A paragraph about the open economy with no command in sight |

## 09 — Writing style

- **Sentences**: 8–15 words, one fact each. A longer sentence may walk through a sequence; follow it with a short one.
- **Punctuation**: Periods do the work. Colons introduce a definition or consequence. Middle dots (`·`) separate items in labels and footers. Oxford comma, yes. **No em dashes, no exclamation marks, no ellipses** (except in literal terminal output).
- **Capitalisation**: Sentence case everywhere. **TOON** always in capitals; `toon` only for the binary and in code. Never "Toon" or "the TOON". "TOON Protocol" only for the org, licence and footer. Commands, flags and paths exactly as typed, in code formatting.
- **Numbers**: Numerals for every quantity, price, version and count. Spell out "one" only when it means "a single". Prices carry their unit or token. Never round up.
- **Contractions**: Yes in marketing, social and email. Optional in docs (match the page). Never in CLI output or error codes.
- **Voice**: Active, with the actor named: the connector refuses, you set the price.
- **Claims**: Every claim is live or labelled with when it will be. If you can't show it in a terminal or point to it in the source, cut it.
- **Humour**: Rare, dry, from exact understatement. No puns on "toon", no emoji, no memes.

## 10 — Vocabulary

**We say**
- your machine, your app, your price, your own hardware
- paid, already paid for, every request, per request
- price, refuse, refusal ("refuses an unpaid request with the price")
- route, hop by hop, packet, channel, peer, settle
- plain HTTP, ordinary HTTP
- reads are free, writes are paid
- live, next, mainnet, devnet, test tokens
- no cloud · no domain · no open port (as a set)
- no protocol fee
- anyone can run a connector
- the project's connector (not "the hub")
- ILP routes, x402 settles

**We don't say**
- revolutionary, game-changing, seamless, frictionless, effortless, unlock, empower, supercharge, next-gen, world-class, unstoppable
- internet-native, agentic commerce, the future of payments, the agents are here, single line of code
- zero fees (there's gas), trustless, fully decentralized, 100% private, web3
- solution, platform, ecosystem, leverage, robust, powerful, "simply" or "just" in instructions
- "Get paid." as a sentence on its own, "agents get paid", "own your agent", "mandate", "unified interface", "money moves like data"
- onion, .onion (the address is `.anyone`)
- gateway, proxy, terminator (say connector); backend, service (say app); user, admin, customer, merchant (say operator)
- hub, stack, full node, "node" alone in docs (say agent node)
- global network, thousands of nodes, or any size claim not yet sourced
- passive income, get rich, make money while you sleep
- WAGMI, gm, to the moon, 🚀
- "Hi agents! 👋" or any performance aimed at agents

**Defined terms** (from `toon_cli/CONTEXT.md`, which wins)

| Term | Means |
|---|---|
| **Operator** | Whoever runs an agent node, human or agent |
| **Agent node** | Everything one operator runs on one machine. Two words in docs; "Run a node" is fine in a CTA |
| **TOON app** | A connector plus the apps behind it |
| **Connector** | The paid reverse proxy in front of a TOON app |
| **App** | The payment-oblivious HTTP service behind a connector |
| **Hidden service** | The default reachability mode, an `.anyone` address. Gloss it on first use; keep it out of headlines and ads |
| **Clearnet** | Reachable at an ordinary public hostname, only by request |
| **Spending limit** | The most a wallet pays per command and per day |

## 11 — Naming

Full system: [architecture.md](architecture.md).

| Level | How it's named | Example |
|---|---|---|
| Master brand | TOON | "TOON settles on Base and Solana." |
| Core stack | Lowercase glossary noun after TOON | the TOON connector, then "the connector" |
| Endorsed product | Own name + "on TOON" | spaceturtle, an agent on TOON · rig, git on TOON |
| Compute marketplace | TOON Compute (was "TOON Network"), kept off the front door | |
| Built on TOON | Own name, "runs on TOON", no prefix, no symbol | vibe_station runs on TOON |

No tiers (no Pro, Plus or Enterprise). Mainnet and devnet are labels, never product names. Versions are plain semver, no codenames. New repos are kebab-case. Before naming anything new, run the decision tree in architecture.md section 04.

---

# Part 4 — Messaging

Full framework: [messaging.md](messaging.md).

## 12 — Core message

> **TOON helps developers and agent builders earn from what already runs on their own machines by making it reachable and charging for every request, with no server, no open port and no company in the middle.**

Keep *reachable* and *paid* in the same sentence, always above the fold.

## 13 — Value proposition

TOON is an open network that lets an app or agent on your own machine take paid requests from anyone, person or agent. A connector on your machine checks payment the way nginx terminates SSL, so your app receives ordinary HTTP that has already been paid for. You set the price, and there's no platform taking a cut or holding your money.

## 14 — Tagline

**Your machine. Paid per request.**

- Use it as the brand headline: homepage hero, social bio, banners, deck title slide.
- In technical contexts (README, docs hero), put the product line under it or in its place: **Every request arrives paid.**
- Retired, don't use: "Value, routed." and "Host it from home. Get paid by anyone."
- Any page that says "paid" carries the label **live: Base and Solana mainnet · devnet for testing**.

## 15 — Key messages

| Message | Proof | Status |
|---|---|---|
| **Reachable from anywhere, with no open port.** Your service can sit behind a home router and still answer the internet. | A new TOON app is a hidden service by default, at an `.anyone` address | **Live, shown on devnet** with test USDC ([demo](https://github.com/toon-protocol/echo-merchant/tree/main/demo/behind-nat), [settlement tx](https://sepolia.basescan.org/tx/0x4b7f7860e3485d438008c7abcc77286f80a18aba3645395adc66ff72b54ff21a)). Link the demo wherever the claim leads, and say it's devnet |
| **Your app never touches the money.** The connector terminates payment; your app gets plain HTTP that's already paid for. | The connector design. The app is any HTTP service | **Live** |
| **Nobody you have to sign up with.** Payment routes hop by hop between peered connectors, and anyone can run one. | Packets carry their own claim. No protocol fee. MIT licence | **Live.** Don't imply many independent operators until there are some |
| **One binary, built to be run by people and agents.** | `toon` v0.1.0 for Linux x86_64/aarch64, `--json` on every command, stable exit codes | **Live** |

The strongest live proof: the website's own Arweave write was bought through the mainnet node over 2 paid hops, and the receipts are on the proof page. Link the receipt.

---

# Part 5 — Brand in use

## 16 — Website

- **Light-first** on Paper. Docs follow the reader's system theme; dark mode is Night with Paper text and the dark mark.
- **Hero**: "Your machine. Paid per request." in Plex Sans Condensed Bold, Ink. Then the supporting statement, the install command in a Night terminal panel, and a live/next chip.
- **Below the hero**: the route diagram as the main explainer, then real terminal sessions, one per step.
- **CTAs**: sentence case, Plex Sans SemiBold, Ink fill with Paper text, square corners, no shadow (**set here**). The label says what happens: "Install `toon`", "Run a node", "See the receipts". Secondary CTA: Ink outline, no fill.
- **Links**: Gold text `#7d5f17` on Paper, Gold on Night, underlined. Never blue.
- **Gold in UI**: only prices, the active route and the paid/settled state.
- The current site's Archivo, JetBrains Mono and `#d9b65c` go when the site is rewritten from this package.

## 17 — Social media

- **Avatar**: the two-bar mark on a Paper tile, or on Night for dark-first platforms (GitHub org, Discord).
- **Banner**: one route diagram on Paper with "Your machine. Paid per request." in Plex Sans Condensed Bold, Ink.
- **Bio**: "Your machine. Paid per request. Open protocol, settling on Base and Solana."
- **Posts**: changelog format, one shipped fact per post, with a command or number. 1200×675 Paper card, 64px margin, one Ink headline, one real command or output on a Night panel, Gold on the number that matters, symbol bottom-right at 48px.
- **Captions**: dry, no emoji, at most one hashtag. Example: "Every `toon` command now takes `--json` and prints exactly one JSON document."

## 18 — Email

- **Header**: the horizontal lockup on Paper, left-aligned, nothing else.
- **Subject**: the change, not a hype line. "The store is priced on mainnet."
- **Body**: newsy and short. What changed, then the one command to run.
- **Signature** (**set here**):
  ```
  Name
  TOON Protocol · toon.ar.io
  github.com/toon-protocol
  ```
  Plex Sans or the system sans, Ink, no logo image, no quote line.

## 19 — Print

- **Business cards** (only if needed): Paper stock. Front: the full mark. Back: name, then a key fingerprint or `.anyone` address in Plex Mono. No job-title flourishes.
- **Letterhead** (**set here**, not yet needed): the lockup top-left on Paper, `toon.ar.io` in Plex Mono at the foot, Ink text throughout. The digital equivalent is a Paper-background PDF exported from the same layout.
- **Stickers**: die-cut full mark, Ink, Gold and Paper on a Paper backing.
- Print colour values aren't set (section 22), so check a proof before any run.

## 20 — Presentations

- Paper slides, Ink text, one Gold element per slide at most.
- Titles in Plex Sans Condensed Bold at 40–56pt, body in Plex Sans at 20–28pt, code in Plex Mono (**set here**, scaled from the web hierarchy).
- Structure: the three-product problem (tunnel + payment rail + public server), then one network, then the route diagram built up hop by hop, then a live terminal, then live/next.
- Every claim slide cites its source in Plex Mono in the footer.

## 21 — Terminal and CLI

TOON's real packaging.
- State colours: Gold for paid or settled, green for running, red only for errors, dim for refused.
- Status and spinner words are single real states: "Routing", "Signing", "Settled". Spinner mod: [`mod/toon-spinner`](mod/toon-spinner), primary `#c9a24a`, desktop word `#7d5f17`.
- Error messages say what happened, the number, and what to do next. No apology, no blame. "Refused: this command pays 1,200,000 and today's spending limit has 400,000 left."
- OG image and README header: the full mark on Paper with the wordmark, nothing else.

---

## Brand don'ts

- [ ] Never use the full mark below 64px, the two-bar mark below 24px, or anything but the pixel file at 16px.
- [ ] Never add a gradient, glow, shadow or outline to the mark, or put it in a circle or hexagon.
- [ ] Never use colours outside Gold, Ink, Paper, Wire, Night, Gold text and the state colours. No purple, teal, neon or blue.
- [ ] Never set Gold `#c9a24a` as text on Paper or white. Use `#7d5f17`.
- [ ] Never use a typeface outside IBM Plex Sans, Sans Condensed and Mono.
- [ ] Never say "paid" without the live label, or claim traffic, operators or network size that isn't shown.
- [ ] Never say "no open port" without linking the demo, or as if it were shown on mainnet. It's shown on devnet.
- [ ] Never imply TOON hosts your code, holds your money or takes a cut.
- [ ] Never separate *reachable* from *paid* above the fold.
- [ ] Never use hype, exclamation marks, em dashes or emoji in product copy.
- [ ] Never put the TOON prefix or symbol on something the project doesn't maintain.
- [ ] Never show invented terminal output.

---

# Part 6 — Contacts and assets

## 22 — Ownership, files and open items

**Brand guardian**: the maintainer of this package, the `toon-protocol/brand` repo. Product terms belong to `toon_cli/CONTEXT.md` (agent node) and `TOON_Network/CONTEXT.md` (TOON Compute).

**Asset location**: [`assets/`](assets/) in this repo, SVG only. The spinner mod is in [`mod/toon-spinner`](mod/toon-spinner). Fonts: IBM Plex from Google Fonts or `github.com/IBM/plex`.

**Questions and approvals**: open an issue or PR on `toon-protocol/brand`. A new repo or launch states its architecture level (core, endorsed, built on TOON) in its first PR; see the checklist in architecture.md section 06.

**Review**: at each minor release of `toon` (v0.2.0 is next) or every quarter, whichever comes first. Run a brand audit against this file then.

**Open items** (not decided anywhere yet)

| Item | Why it matters |
|---|---|
| CMYK and Pantone values for Gold, Ink, Paper and Wire | Needed before any print run. Pick them from a printed proof, not a formula |
| Stacked lockup | Allowed for square avatars, but not drawn |
| "Runs on TOON" badge | Approved in architecture.md, not drawn |
| Custom icon set (about 20 icons) | Lucide is the interim |
| Home-router demo on mainnet | Key message 1 is shown on devnet only, with one run through the project's relay |
| Brand vision | Assumed in positioning.md, not confirmed |
| Social, email and deck templates | Specs are above; no files yet |
