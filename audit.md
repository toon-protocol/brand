# Brand Audit: TOON Protocol

*Run 2026-10-15. This is the audit [guidelines.md](guidelines.md) asks for at each minor release of `toon`: v0.2.0 shipped on 2026-10-12. It scores **what the market sees today**, and the brand package counts only as declared intent. Sources checked: the live site at `toon.ar.io` (ArNS `toon` → `52X09AnoSDh-nCSg59Sy759IR0uLsYXREhr1pn0JKdA`), the website repo's `main` (merged in PR #31, not yet published), the GitHub org profile, the `toon_cli` and `connector` READMEs, the description of the npm package `@toon-protocol/client`, the OG card, and open website issues #32–#35. Not checked: the X account `@toonprotocol` and the Discord, because both need a login. There is no customer or perception data yet, so audience scores rest on fit, not on research.*

---

## Headline finding: production is behind the docs

The brand package and the website's `main` agree. The site the market reaches doesn't. That's **documentation ahead of production**, so the problem isn't drift and the brand doesn't need rework. The rewrite is done. It just hasn't shipped.

| Touchpoint | What it says | Status |
|---|---|---|
| `toon.ar.io` title and hero (live) | "Value, routed. Host it from home. Get paid by anyone." | **Retired** copy |
| `toon.ar.io` meta description (live) | "An open network of hidden services where agents talk, work together and pay each other." | **Retired**, and it breaks two rules |
| OG card image (live, served from github.io) | "Your machine. Paid per request." | New. It's paired with the old `og:title`, so link previews mix the two |
| Website `main` (merged 2026-10-15 11:55, unpublished) | "Your machine. Paid per request." + live/next chip + route diagram | **On brand** |
| GitHub org description | "An open network of hidden services where agents talk, work together and pay each other." | **Retired** |
| `toon_cli` README | "Give your agents a machine of their own: a place to post and reply, and any HTTP service you choose, sold per request." | A fourth pitch |
| `connector` README | "Put a price on any HTTP app and get paid per request, in USDC, with no protocol fee and no change to your app." | Close to brand. Product-level, which is fine |
| npm `@toon-protocol/client` | "pay for HTTP requests per request over ILP, with EVM and Solana payment channels" | Accurate. Caller side, which is fine |

Publishing the site is a paid Arweave write through the live node (website README, "Publishing"), so it doesn't happen when code merges. Until someone does it, every visitor sees the retired brand.

---

## Brand health scorecard

Scored on the live touchpoints. The declared score shows where the package and `main` would land once published.

| Dimension | Live | Declared | Status |
|---|---|---|---|
| Positioning clarity | 3/5 | 5/5 | 🟡 Developing |
| Visual identity | 3/5 | 5/5 | 🟡 Developing |
| Messaging consistency | 2/5 | 4/5 | 🔴 Needs work |
| Voice and tone | 4/5 | 5/5 | 🟢 Strong |
| Audience alignment | 4/5 | 4/5 | 🟢 Strong |
| Competitive differentiation | 3/5 | 4/5 | 🟡 Developing |
| **Overall** | **19/30** | **27/30** | |

**Positioning (3).** The live hero still holds both halves ("Host it from home. Get paid by anyone."), so it's in the paid-self-hosting space. But the meta description and the org bio lead with "an open network of hidden services where agents talk", which is agent-first and puts "hidden service" in the lead. That's the shelf [positioning.md](positioning.md) says TOON can't win. Could it apply to a competitor? "Get paid by anyone" sits close to Apify's "Get paid."

**Visual (3).** The packet mark, the favicon and the Paper/Ink/Gold palette are right on the live site. Type is not: the live site runs Archivo 800, Inter and JetBrains Mono, all three on the identity brief's avoid list, and it still carries the retired dark accent `#d9b65c`. The `toon_cli` and `connector` READMEs use a **different logo** (`docs/assets/toon-logo.png`, four dark maze tiles), so two marks are in active use. The README badges include a blue MIT badge and a Rust-orange badge, against "never blue".

**Messaging (2).** Four first lines across five surfaces: "Value, routed." (site), "open network of hidden services where agents…" (org, meta), "Give your agents a machine of their own" (CLI README), "Your machine. Paid per request." (OG card). Someone who meets TOON on GitHub, then on the site, then in a link preview sees three different products. The live page also has no **live/next** label, which [messaging.md](messaging.md) requires on any page that says "paid".

**Voice (4).** This is the brand's strongest asset, and it's already live. Short declarative sentences, real commands, numbers with units, and lines like "A refusal comes back as a value, not an exception." Remove the logo and you'd still know it's TOON. Three words for how it writes today: **exact, plain, literal**. It loses a point for "Value, routed" (a slogan the voice guide wouldn't write) and for "the network's hub", which the brand replaced with "the project's connector" in `64edcdf`.

**Audience (4).** Developer language throughout: a one-line install, `systemd --user`, `--json` on every command, a TypeScript snippet for callers. The agent surface is real and stated plainly, without the "Hi agents 👋" cliché. It loses a point for leading with agents in the meta and org copy, which the messaging file warns against ("don't make agents the whole story").

**Differentiation (3).** "ILP routes · x402 settles · no fee" and "the app knows nothing about payment" are distinct and true. But the live page says "no open port" without linking the behind-NAT demo, and it has no route diagram, so the strongest differentiator is asserted rather than shown. The number of independent operators is still **owed**, so "nobody in the middle" can't yet be backed with a count.

---

## What's working

1. **The voice is already distinctive and in production.** The live landing page reads like a well-written man page: real output from `toon status`, prices with units ("$0.000001 lowest price you can set"), and honest stage labels ("Devnet · free"). In a category full of "agentic economy" copy, this is the clearest thing that sets TOON apart, and it costs nothing to keep.
2. **The packet mark works and is used consistently on the site.** The favicon, the inline `svg.mark` and the OG card all use the same two-bar packet in Ink, Gold and Wire. It holds at 16px and carries the thesis (message plus value) without needing explanation.
3. **The brand package is unusually complete and self-consistent.** Positioning, messaging, voice, identity and guidelines all point at one sentence, and each has a proof bank marked live or owed. The website's `main` was rebuilt from it and has a CI gate (`check.py`) that enforces contrast pairs. The system for staying on brand already exists.
4. **Honesty shows in the product's own output.** "Shown on devnet", "Until now the node reaches nobody", a receipt-backed proof page, and the site itself bought as a paid TOON write. This is the asset competitors can't copy, because their overclaiming is structural.

---

## What's not working

**1. The rewritten site is merged but not published.**
- *Evidence*: `toon.ar.io` serves the retired title, hero and meta. Website `main` (PR #31, 2026-10-15) has the new brand. ArNS `toon` still resolves to the old revision.
- *Impact*: Every first impression, search snippet and link preview carries the retired positioning. This one action moves about 8 points of the score.

**2. Four different first lines across the touchpoints.**
- *Evidence*: The table above. The GitHub org bio and the `toon_cli` README sit outside the website pipeline, so publishing the site won't fix them.
- *Impact*: The positioning only holds when *reachable* and *paid* sit in one sentence (positioning red flag 4). Each surface splits them differently, and the agent-first ones drift onto the crowded "agent payments" shelf.

**3. Two logos in active use.**
- *Evidence*: The site, OG card and favicon use the packet mark. The `toon_cli` and `connector` READMEs use `toon-logo.png`, a four-tile maze mark that isn't in `assets/` or the identity brief.
- *Impact*: GitHub is where the primary audience meets TOON first, and it shows a mark that appears nowhere else. That undoes the "mark as a diagram element" system.

**4. The strongest claim isn't proven on the page where it's made.**
- *Evidence*: The live page says "behind your home router, with no domain and no open port", with no demo link and no "shown on devnet" label. Website issues #32/#34 (show the behind-NAT demo) and #33 (keep "hidden service" out of headings) are open. PR #35 is in flight.
- *Impact*: The message's own rule says this claim never appears without the demo link. Unproven, it reads like every tunnel's marketing.

**5. The brand package itself is a little stale (documentation debt).**
- *Evidence*: `messaging.md`, `positioning.md`, `guidelines.md` and `architecture.md` cite `toon` **v0.1.0**. The release is **v0.2.0** (2026-10-12), and the website's `main` already shows 0.2.0 output. "The network's hub" also survives on the merged `main` (step 05), against `64edcdf`.
- *Impact*: Small, but it's the honesty value. The source of truth has to be the most current document.

---

## Priority recommendations

**Immediate (do now)**
1. **Publish website `main` to Arweave** and repoint ArNS `toon`. Ideally merge PR #35 first so the behind-NAT demo ships in the same paid write. Check `og:title` and `og:image` together afterwards so link previews agree.
2. **Change the GitHub org description** to "Your machine. Paid per request. Open protocol, settling on Base and Solana." (the social bio in [messaging.md](messaging.md) 06). Rename the display name "Toon Protocol" → "TOON Protocol".
3. **Replace "the network's hub"** with "the project's connector" in website step 05 and across `src/docs/` (67 lines mention "hub", so review each, because some may be correct).
4. **Bump v0.1.0 → v0.2.0** in messaging, positioning, guidelines and architecture.

**Short-term (next 30–60 days)**
1. **Bring the repo READMEs onto the brand.** Swap `toon-logo.png` for the packet mark (`assets/toon-icon-tile.svg` / the dark variant). Give `toon_cli` the README/docs line from messaging ("Every request arrives paid.") instead of "Give your agents a machine of their own". Recolour the badges to Ink, Wire and Gold. The `toon-readme-style` skill already defines the house layout. Apply it to `toon_cli`, `connector`, `toon-client`, `relay` and `store` together.
2. **Add a brand-copy check outside the website.** `check.py` guards the site only. A small CI check (or a task on the release checklist) that diffs each org-facing first line against `brand.yaml`'s `tagline` and `one_liner` would have caught problems 2 and 3.
3. **Check X and Discord** (bio, avatar, banner) against [guidelines.md](guidelines.md) 08. They weren't audited here.

**Long-term (strategic)**
1. **Turn "owed" into numbers.** The position's weakest point is "no company in the middle" while every visible connector is the project's own. Put the first independent mainnet operator, and paid packets per day, in the live/next block as soon as they exist. That's the proof that moves differentiation from 4 to 5.
2. **Get the first external perception data.** Five conversations with people who ran `toon init`, asking what they think TOON is, in one sentence. Score positioning against their words next audit, not ours.
3. **Watch Tailscale.** [positioning.md](positioning.md) names it as the most likely to move into paid self-hosting. Rerun [competitors.md](competitors.md) at v0.3.0.

---

## Open questions for the next audit

- What prompted this one beyond the v0.2.0 trigger, if anything?
- Is there any user feedback (Discord, issues) on how people describe TOON?
- Who decides when a merged site revision gets bought and published, and should the release checklist include it?

*Next audit: at `toon` v0.3.0 or 2027-01-15, whichever comes first.*
