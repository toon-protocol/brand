# Brand Architecture: TOON Protocol

*Drafted 2026-10-15 from [context.md](context.md), [positioning.md](positioning.md), [messaging.md](messaging.md), [identity.md](identity.md), [voice.md](voice.md), and a survey of the 35 repositories in the `toon-protocol` GitHub org. Product terms come from `toon_cli/CONTEXT.md` and `TOON_Network/CONTEXT.md` and constrain the names below. Three open questions were decided by the maintainer on 2026-10-15 (see "Decisions" at the end).*

---

## 01 — Portfolio audit

The org holds about 35 repositories. Most of them are parts of one product, a few are products with their own audience, and the rest are demos, experiments or internal tools. They're grouped here by how they relate to the master brand today.

### The protocol stack (what an operator or payer touches)

| Name (repo) | Audience | Positioning | Current relationship | Equity |
|---|---|---|---|---|
| **TOON** (`toon_cli`, binary `toon`) | Primary: developers and agent builders | The agent node: connector, supervisor and CLI in one binary | Uses the parent name, and *is* the parent in practice | Developing (v0.1.0) |
| **connector** | Same, plus connector operators | "A paid reverse proxy" | Descriptor, "the TOON connector" | Developing. Its line ("terminates payments the way nginx terminates SSL") is the brand's best proof |
| **relay** | Same, plus Nostr builders | "A Nostr relay you get paid to write to" | Descriptor, "the TOON relay" | Developing |
| **store** | Same | Paid Arweave blob store, and the worked example | Descriptor | Developing (priced on mainnet) |
| **swap** (npm still `@toon-protocol/mill`) | Same | Cross-chain swap through a relay | Descriptor, mid-rename | None yet |
| **gas-station** | Same | "A TOON app that pays other people's gas" | Descriptor | None yet |
| **toon-client** (`@toon-protocol/client`, `client-mcp`) | Payers: developers and agents | Pay for an HTTP request per request | Descriptor | Developing |
| **toon** (`@toon-protocol/core`, `sdk`) | Builders of TOON apps | Library layer | Descriptor | Internal |
| **echo merchant** (`echo-merchant`) | Payers testing a payment flow | A route that "sells nothing, on purpose" | Unclear: own name, no TOON prefix | None yet |

### Products with their own name

| Name (repo) | Audience | Positioning | Current relationship | Equity |
|---|---|---|---|---|
| **spaceturtle** (+ `spaceturtle-panel`) | Primary audience, on Omarchy desktops | "An agent that serves your apps from your own machine, and is paid for each request" | Stands alone: own name, own navy banner (`#0b1020`, `#5b6b9a`), Gold release badge, "runs a node on the TOON network" in its body | Developing. It says the positioning sentence more clearly than any other repo |
| **TOON Network** (`TOON_Network`, `provider`, `gateway`, `console`) | A different audience: compute **providers** and **tenants** | "A decentralized compute marketplace built on TOON" | Uses the parent name as a proper noun | Spec and code; stage not recorded in this package |
| **Rig** (`rig`, "The Rig") | Developers publishing git to TOON | Git-to-TOON write path and forge-like UI | Stands alone, with a definite article | None yet |

### Built on TOON (apps and experiments)

| Name | What it is | Current relationship |
|---|---|---|
| **vibe_station** | Pay-per-segment broadcasting, two TOON apps | Own name, "behind the TOON connector" |
| **fractal** | "Agent-grown dimensions on TOON" | Own name |
| **slop_machine** | Experiment ("Make money shipping slop") | Own name |
| **anytoon** | Sells Anyone Protocol credentials behind the connector | Own name containing "toon" |
| **tuzzy** | Buys those credentials, for a crawler | Own name |
| **buzz** | "A hive mind communication platform" | Own name, relation not stated |

### Not brands

`infra` (dev sandbox), `simulation`, `toon-meta`, `toon-agent-native`, `omarchy`, `distribution`, `toon-demo`, `toon-rust-demo`, `toon_world` (private), `website`, `brand`, `toon-spinner` (brand mod). Archived: `hub`/`townhouse`, `town`, `Town-Frontend`, `swarm`, `capability-market`, `slopmachine`.

### What the audit shows

1. **The stack is already a branded house, informally.** Repos name themselves by what they do (connector, relay, store, swap) and lean on "TOON" in prose. That's right, and it only needs writing down.
2. **"TOON Network" collides with "the TOON network".** spaceturtle's README says it "runs a node on the TOON network", meaning the payment network. `TOON_Network` means a compute marketplace with its own parties (provider, tenant) and its own glossary. One spoken phrase now names two things.
3. **TOON Network pulls against the positioning.** positioning.md section 06 says TOON is *not for people who want someone else to run their code*. A tenant leasing a workload on a provider's hardware is exactly that person. From the provider's side it *is* paid self-hosting, but with a different audience and a different promise.
4. **Names keep changing.** `mill` → `swap` and `townhouse` → `hub` (now archived). "The network's hub" is still how `toon_cli`'s README names the project-run connector that devnet nodes peer toward. It's a different thing from the archived `hub` product, and the glossary bans "hub" only as a word for an agent node, but one word now means two things. Repo casing is mixed (`toon_cli`, `TOON_Network`, `vibe_station`, `gas-station`, `echo-merchant`).
5. **The most on-message product has its own name.** spaceturtle carries the positioning sentence almost word for word, and its personality (a turtle in the bar) is something voice.md forbids the master brand ("no cartoons"). That's a reason to keep it separate, not to absorb it.

---

## 02 — Architecture recommendation

**Recommended model**: **Hybrid, led by a branded house.** TOON is the master brand. The protocol stack takes descriptor names under it. A small number of finished products carry their own name, **endorsed** by TOON. Apps that others (or the project's own experiments) build on TOON keep their own names and say they run on TOON, an ingredient-brand relationship and not part of the house.

**Why this model**: The brand's whole claim is that reachable and paid are *one thing* (positioning red flag 4), so the stack must read as one product and not as a shelf of separate tools. A branded house keeps the equity in one name while the project is small and can't afford to market more than one. But two parts of the portfolio need room the master brand doesn't give them. spaceturtle needs a character the master voice refuses, and the ecosystem must stay visibly *not TOON's*, because "TOON never holds the money" and "anyone can run a connector" are only believable if other people's apps don't wear TOON's name.

**What this means in practice**:
- Say "TOON" for the network and the protocol, always in caps. Say `toon` only for the binary and in code.
- Every stack component is a lowercase noun after TOON: the TOON connector, the TOON relay, the TOON store. There are no invented names inside the stack.
- spaceturtle stays spaceturtle, endorsed as "an agent on TOON".
- Third-party and experimental apps never take the TOON prefix. They say "runs on TOON".
- TOON Network is renamed **TOON Compute**, so the payment network keeps the word, and it stays off the master brand's front door until its promise is reconciled with the positioning (see Decisions).

---

## 03 — Brand hierarchy map

```
TOON  ·  the open network: your machine, paid per request
│
├── Core stack ─────────────────────────────── branded house (descriptor)
│   ├── toon          the agent node: connector, supervisor, CLI
│   ├── connector     the paid reverse proxy at the front of every TOON app
│   ├── relay         the Nostr relay app, paid to write to
│   ├── store         paid Arweave blob store
│   ├── swap          cross-chain swap through a relay
│   ├── gas station   pays other people's gas
│   ├── client        the payer: @toon-protocol/client, client-mcp
│   ├── core / sdk    libraries for building TOON apps
│   └── echo          a route that mirrors what arrived (test merchant)
│
├── Endorsed products ──────────────────────── own name, "on TOON"
│   ├── spaceturtle           an agent on TOON
│   │   └── spaceturtle panel   (descriptor under spaceturtle)
│   └── rig                   git on TOON
│
├── Compute marketplace ────────────────────── descriptor, held off the front door
│   └── TOON Compute (was "TOON Network"): provider, gateway, console
│
└── Built on TOON ──────────────────────────── ingredient, "runs on TOON"
    vibe_station · fractal · anytoon · tuzzy · slop_machine · buzz · any third-party app
```

### Relationships

| Level | Naming | Visual | Messaging |
|---|---|---|---|
| **Core stack** | Lowercase descriptor. In prose, "the TOON connector" on first use, then "the connector". Package `@toon-protocol/<descriptor>`, image `ghcr.io/toon-protocol/<descriptor>` | The master identity, unchanged. Packet symbol, Plex, Paper/Ink/Gold. A component may add a line icon from the identity.md set, never its own logo | Inherits fully. Each README opens on the component's job in one bold line, then the nginx analogy where it applies |
| **Endorsed** | Own name, always set as the brand writes it (spaceturtle is all lowercase). Endorsement line: "an agent on TOON" / "git on TOON" | Its own symbol and palette are allowed. It must share **Gold `#c9a24a` as the only accent for paid/settled state** and **Plex** for type, and carry the TOON symbol small in its footer or about screen | Inherits the positioning and the honesty rules (live/owed, mainnet label). It may have its own personality: spaceturtle can be a turtle, TOON cannot |
| **Compute marketplace** | "TOON Compute", parties named as in its glossary (provider, tenant, workload, lease) | Master identity | Its own promise, which must not contradict "TOON never holds the money" |
| **Built on TOON** | Its own name. May say "runs on TOON", "built on TOON" or "behind the TOON connector". Never "TOON <X>", never the TOON symbol as its logo | Independent. May use an approved "runs on TOON" badge (symbol + wordmark, Ink or Paper, no Gold) | Independent. Must not imply TOON operates, endorses or holds funds for it |

---

## 04 — Naming system

### Naming convention

- **Master brand**: **TOON**. "TOON Protocol" only where the full legal or org name is needed (the GitHub org, the license, the footer). Never "Toon", never "the TOON".
- **Core stack**: `[TOON] + [plain descriptor]`. The descriptor is the glossary noun for the thing (`connector`, `relay`, `store`). If the glossary has no noun for it, define one in `toon_cli/CONTEXT.md` first, then name it.
- **Endorsed**: `[Own name], [a/an] [descriptor] on TOON`. Example: *spaceturtle, an agent on TOON*.
- **Built on TOON**: independent name, `runs on TOON` as the only allowed link.

### Naming rules

**Use**
- The glossary noun, in lowercase, for every core component. The glossary already decided these: *agent node* (always two words), *TOON app* (a connector and its apps), *connector*, *app*, *relay*, *hidden service*.
- Kebab-case lowercase for every new repo, package and image (`gas-station`, `echo-merchant`). Existing `toon_cli`, `TOON_Network`, `vibe_station` and `slop_machine` keep their names until there's another reason to rename them, since renames break links and installs.
- Verbs that are literally true ("pay", "route", "settle") in endorsed and ecosystem names.

**Avoid**
- "hub", "node" alone, "stack", "full node" for the agent node (glossary).
- "Hub" for the project-run connector that devnet nodes peer toward. Say "the project's connector": it's accurate, and "hub" makes the network sound centralized. The brand docs use this; `toon_cli`'s README and `docs/end-to-end.md` still say "hub".
- "gateway", "proxy" or "terminator" for the connector (glossary). The Workload Gateway is a different thing and keeps its name only inside the compute marketplace.
- The TOON prefix on anything the project doesn't maintain, and "toon" inside the name of new projects (`anytoon` is grandfathered).
- Category clichés from messaging.md section 07 in any product name: "agentic", "pay", "402", "zap", "mint", "chain", "hub", "router" on its own.
- Puns on "toon" or cartoons (voice.md). Endorsed products can be playful in their *own* name, as spaceturtle is, but never by bending the word TOON.
- Definite-article product names. "The Rig", "The Workload Gateway" and "The TOON Console" become "rig", "the gateway" and "the console" in running text.

### Tiers and variants

- **No product tiers.** There is no TOON Pro, Plus or Enterprise. Prices belong to operators, not to TOON, and a paid tier would make TOON a party to the money (positioning section 06).
- **Networks, not regions.** The only variants are where it settles: **mainnet** (Base, Solana) and **devnet** (Base Sepolia, Solana devnet). Write them as labels, not product names: *"live: Base and Solana mainnet · devnet for testing"*. Never "TOON Testnet" or "TOON Devnet" as a brand.
- **Versions** are plain semver on the binary (`toon v0.1.0`). No codenames.

### Decision tree for something new

1. **Does TOON stand in the middle of the money, hold funds, or run someone else's code for them?**
   Yes → stop. It doesn't ship under TOON at all until that's resolved (positioning section 06).
2. **Is it a part of the stack an operator or payer needs to run, reach or pay a TOON app?**
   Yes → **core**. Glossary noun, TOON prefix in prose, master identity.
3. **Is it a finished product, maintained by the project, with an audience or a personality the master voice can't carry?**
   Yes → **endorsed**. Own name, "on TOON", shared Gold and Plex.
4. **Is it built by someone else, or a project experiment with no maintenance commitment?**
   Yes → **built on TOON**. Own name, "runs on TOON", no prefix.
5. **Does it serve a different audience *and* make a different promise?** (The compute marketplace is the test case.)
   Yes → it needs its own architecture decision before it's named or marketed. Don't default it into the house.

---

## 05 — Visual identity system

- **Logo**: One master mark, the packet symbol and wordmark from identity.md. Core components never get their own logo. They're identified by name, set in Plex Mono beside the master mark, or by an icon from the identity.md set (connector, relay, packet, channel). Endorsed products have their own logo with a small TOON symbol in the footer, README badge row or about screen. Built-on-TOON apps may use only the "runs on TOON" badge.
- **Color**: The core stack uses the master palette (Paper, Ink, Night, Wire, Gold, Gold text) with no per-product colors, because color-coding a dozen components would teach the reader they're separate. **Gold means paid** at every level of the architecture, the endorsed products included. spaceturtle's navy is fine as its ground, but its paid/settled state and its release badge stay Gold (it already does this for the badge). Status colors (running, error, refused) are shared across core and endorsed.
- **Typography**: IBM Plex (Sans Condensed for the wordmark, Sans for text, Mono for code and labels) for core and endorsed. Ecosystem apps are free.
- **Tone of voice**: Core speaks in the master voice from voice.md, with no exceptions. Endorsed products inherit its *rules* (honesty, live/owed, no hype, no clichés) but may have their own *personality*. spaceturtle can be gentle and a little odd, and TOON stays dry. Ecosystem apps have their own voice, but any sentence they write *about TOON* must be true by the master brand's standards.

---

## 06 — Governance rules

**Brand decision owner**: The maintainer of this brand package (the `toon-protocol/brand` repo). Product terms stay with the glossaries: `toon_cli/CONTEXT.md` for the agent node and `TOON_Network/CONTEXT.md` for the compute marketplace. A name that needs a new term gets the term there first.

**Rules for a new repo or launch**
- [ ] Run the decision tree in section 04 and state the level (core / endorsed / built on TOON) in the repo's first PR.
- [ ] Core: the name is a glossary noun, and the repo is kebab-case.
- [ ] Endorsed: the endorsement line and the shared Gold/Plex rule are in the README header.
- [ ] Built on TOON: no TOON prefix, no TOON symbol as its logo.
- [ ] Positioning check: does the README's first line keep *reachable* and *paid* together and avoid implying TOON holds money?
- [ ] Add the repo to section 01 of this file in the same PR that makes it public.

**Review cadence**: Look at this file whenever a repo is created or archived in the org, and audit it fully at each minor release of `toon` (v0.2.0 is the next), or every quarter, whichever comes first. The audit checks section 01 against `gh repo list toon-protocol`.

---

## Decisions

Decided by the maintainer on 2026-10-15.

1. **TOON Network becomes TOON Compute.** "The TOON network" now means one thing, the payment network. TOON Compute stays off the master brand's front door (homepage, tagline, social bio) until its promise is reconciled with "TOON is not for people who want someone else to run their code." Revisit if compute becomes the project's next core bet. The rename covers prose, UI strings and package descriptions in `TOON_Network`, `provider`, `gateway`, `console` and `rig`. Identifiers keep their names: the `TOON_Network` repo, the spec's file name, the `toon.network` event label, and crate and package names.
2. **rig is endorsed:** "rig, git on TOON". It has a UI and an audience of its own (people publishing repos). Written lowercase; "The Rig" in its README becomes "rig".
3. **spaceturtle's endorsement line is "an agent on TOON".** It's literal, keeps TOON in the sentence, and matches the README's existing first line.

## Red flags

1. **The name collision is live now.** spaceturtle's README and `TOON_Network` already use the same words for two different things. Every week it stays, more docs and posts repeat it.
2. **Endorsing spaceturtle means spaceturtle's claims are TOON's claims.** "No open port" sits in its README header, and messaging.md marks that claim live but [shown on devnet](https://github.com/toon-protocol/echo-merchant/tree/main/demo/behind-nat) only, so spaceturtle carries the same scope. An endorsed product doesn't get a looser honesty rule than the master brand.
3. **Experiments with jokey names sit in the same org.** `slop_machine` ("Make money shipping slop") lives under `toon-protocol`. Built-on-TOON status separates it in copy, but a reader browsing the org sees one project. Consider moving experiments to a separate org or marking them clearly as experiments in their descriptions.
4. **Most repos have no description on GitHub** (`toon_cli`, `connector`, `TOON_Network`, `anytoon`, `tuzzy`, `vibe_station` and others). The org page is often the first thing a developer sees, and an empty description there wastes it. Each core repo should carry its one-line job from section 03.
