# China Sourcing Clusters

**Find the county where it is actually made — not the office that answers in English.**

An open-format Agent Skill for overseas B2B buyers who need to source any product from China and keep ending up talking to export trading companies in Shanghai, Shenzhen, Guangzhou, Beijing or Hangzhou instead of the factory.

[简体中文说明](README.zh-CN.md)

---

## The problem

Chinese manufacturing is organised in dense county-level industrial clusters (产业带 / 生产基地). One town often holds the raw material, tooling, mould makers, subcontractors, finishing, packaging and freight for a single product category, all within a few kilometres.

Overseas buyers rarely see any of it. English search results, B2B platform rankings, paid placements and trade-show booths are dominated by export trading companies in first-tier cities, because those firms invest in English websites, SEO, platform advertising and English-speaking sales teams. The factories in cluster towns generally do none of this. Many have no English website at all and sell through domestic wholesale markets, local agents, or as subcontractors to the very trading company the buyer just contacted.

This is a structural information asymmetry, not a search problem. **Fix the geography first.** Once the production county is known, the buyer can search in Chinese, filter by registered address, and approach the producer directly.

## What this skill does

For **any product category** made in China:

- Identifies the production cluster at province / city / **county or town** level, and explains why it formed there
- Splits smart or connected products into solution, component and whole-unit layers, so a firmware, voice or AI requirement goes to the party that actually owns it
- Distinguishes a production cluster from a wholesale market, a showroom and an export office — a costly and very common confusion
- Ranks sourcing channels by how likely they are to surface a cluster factory rather than an intermediary
- Produces **paste-ready Chinese search queries** with place names, process words and factory-signalling terms
- Diagnoses factory vs trading company, and gives concrete, legitimate routes to the producer
- Drafts an enquiry, a verification checklist and a like-for-like supplier scorecard

Every substantive answer is structured as a **Sourcing Route Card** with an explicit confidence and unknowns section.

## What it does not do

| Excluded | Why |
| --- | --- |
| **Retail, consumer shopping, B2C marketplaces, dropshipping, single-unit or sample-only purchases** | Out of scope by design. The skill will decline these requests |
| Named factory lists, contact details, live prices, MOQs, stock, freight rates | No database, no live data, no invented company records |
| Supplier verification, certificate validation, audit conclusions | These are claims to check, never facts to assert |
| Legal, contract, customs, tariff, sanctions, export-control, IP or certification advice | Requires qualified professional advice |
| Sending enquiries, ordering, paying, arranging inspection | Produces drafts only |
| Scraping, login / CAPTCHA / paywall / anti-bot bypass | Public entry points and manual steps only |

No API key. No scripts. No bundled database. No telemetry. The skill itself makes no network requests — it is plain Markdown any compatible agent can read offline. Optional public-record research is done with the host agent's own tools, at the user's discretion.

## Install

The **repository root is the skill folder**: `SKILL.md` sits at the top level. Copy the whole folder into your agent's skills directory so that `<skills-dir>/china-sourcing-clusters/SKILL.md` exists.

| Agent | Skills directory | How to invoke |
| --- | --- | --- |
| OpenAI Codex | `~/.codex/skills/` (user) or `.codex/skills/` (project) | `$china-sourcing-clusters` |
| OpenClaw | `~/.openclaw/skills/` or the agent workspace skills folder | auto-trigger or by name |
| Claude Code | `~/.claude/skills/` or `.claude/skills/` | `/china-sourcing-clusters` |
| WorkBuddy | `~/.workbuddy/skills/` | auto-trigger; SKILL.md can also be imported directly |
| Cursor / other Agent Skills clients | the client's skills folder, commonly `.agents/skills/` | client-specific |

**One-line install:**

```bash
npx skills add jackwangliang/china-sourcing-clusters
```

Repository: [github.com/jackwangliang/china-sourcing-clusters](https://github.com/jackwangliang/china-sourcing-clusters). For a repository containing several skills, add `--skill china-sourcing-clusters`.

**Manual install from the zip:**

Download `china-sourcing-clusters.zip` from the [Releases page](https://github.com/jackwangliang/china-sourcing-clusters/releases).

```bash
unzip china-sourcing-clusters.zip
cp -R china-sourcing-clusters ~/.codex/skills/
```

For a Claude web upload, the zip must contain the `china-sourcing-clusters/` folder at its root with `SKILL.md` inside — this package has exactly that layout. Do not upload GitHub's auto-generated source zip, which wraps files in an extra folder.

Compatible with the [Agent Skills open specification](https://agentskills.io/specification): `SKILL.md` with `name` and `description` frontmatter, optional `references/` and `assets/`.

## Test prompts

Use these to check the skill in any agent. The last two should be declined; prompts 9 and 10 test capability-stack routing.

1. `Where in China are stainless steel flanges actually made? I need the factory, not a trading company in Shanghai.`
2. `I want 5,000 custom ceramic mugs with our logo. Which production region should I look at and why?`
3. `Why do the top Alibaba results for LED pendant lights all seem to be in Shenzhen? Where are the real factories?`
4. `Give me Chinese search terms to find a source factory for socks in Zhejiang.`
5. `Is this supplier a factory or a trader? Here is their company description: ... What should I check?`
6. `Which channels should I use to reach a mould maker near Ningbo for an injection-moulded part?`
7. `Draft an RFQ for CNC-machined aluminium parts, including tooling ownership and a first-article check.`
8. `Where are cosmetic brushes produced in China, and is Yiwu the production base?`
9. `I want a smart speaker with custom voice dialogue. Which manufacturers in China can actually change the wake words and the conversation logic?` → should split the capability stack, ask which of the offline / cloud-LLM / voice-assistant routes is meant, and route the solution layer first
10. `I need a batch of meeting recording hardware with a backend. Where are the manufacturers?` → should state that the backend / cloud / data layer has **no cluster answer**, ask which delivery model is meant (vendor SaaS / buyer's own backend / full private deployment), reverse the order to fix the software specification first, and only then route the hardware layers to a production cluster
11. `Where can I buy one espresso machine cheapest for my kitchen?` → should decline: retail
12. `What is the current 40ft container rate from Ningbo to Rotterdam?` → should decline: live data

A good answer names a **county or town**, separates cluster from market, gives Chinese strings verbatim, labels cluster attribution as **indicative**, and ends with a confidence / unknowns section. For smart or connected goods it must also split the capability stack, identify which layer owns the requested customisation, and not treat a first-tier-city R&D address as automatic proof of an intermediary. When a backend, cloud service, deployment model or data rule is involved, it must say plainly that the cluster map does not apply to that layer, switch to delivery / data / IP / service criteria, and never invent a county for it. It should never invent a company name, a price or a percentage.

## A worked example

**Buyer prompt** (illustrative):

> "We need 20,000 makeup brushes with private-label packaging. Where are they actually produced, and is Yiwu the production base?"

**Sourcing Route Card (abridged):**

| Field | Output |
| --- | --- |
| Production cluster | Anhui · Anqing · Qianshan (MIIT) — brush-making chain; Henan · Zhoukou · Luyi — makeup brushes. Two different chains, stated separately. |
| Is Yiwu the base? | No. Yiwu International Trade City is a **wholesale market**, not a production base. Useful for discovery, weak for identifying a factory. |
| Layer check | Brush head, ferrule, handle and packaging may come from different suppliers; the card names which layer is being sourced. |
| Paste-ready Chinese terms | `制刷 潜山 化妆刷 鹿邑` |
| Channel order | Ranked by how likely each channel surfaces a cluster factory rather than a first-tier-city export office. |
| Confidence | **Indicative.** Cluster attribution must be confirmed against public registration records. |
| Unknowns | No company names, MOQs, prices or certificates asserted — those are verification tasks, not facts. |

The skill then drafts a bilingual RFQ, a factory-vs-trader verification checklist and a like-for-like supplier scorecard. It never invents a supplier name, a price or a percentage.

Sources for the cluster entries are listed in [`references/cluster-map.md`](references/cluster-map.md); the blank templates are in [`assets/`](assets/).

## Repository layout

```
china-sourcing-clusters/
├── SKILL.md                          # routing logic, scope, hard boundaries
├── references/
│   ├── cluster-map.md                # all-category county-level cluster map
│   ├── channel-matrix.md             # channel ranking by factory density
│   ├── chinese-search-terms.md       # paste-ready Chinese query building blocks
│   ├── bypass-trading-companies.md   # diagnosis, evidence and bypass routes
│   └── verification-rfq.md           # enquiry, verification, comparable quotes
├── assets/
│   ├── rfq-template.md               # blank bilingual RFQ draft
│   ├── supplier-scorecard.csv        # like-for-like comparison fields
│   └── shortlist-template.csv        # candidate records with provenance
├── README.md / README.zh-CN.md
├── CONTRIBUTING.md
└── LICENSE
```

`SKILL.md` stays lean; reference files are loaded only when a step needs them. Grep `cluster-map.md` by product word, Chinese place name or province.

## How this compares

Existing open projects solve adjacent problems. This one is deliberately the **geography and intermediary layer**.

| Project | Focus | Needs API / key | Gap relative to this skill |
| --- | --- | --- | --- |
| `1688-sourcing-agent`, `1688-procurement-agent` | Tutorial for one domestic platform | No | Single platform; no cluster geography, no trader-vs-factory routing |
| `china-factory-search` | Searchable factory database with MCP tools | Yes, commercial API | Data product with a specific backing service; not a neutral method |
| `ali1688-sourcing`, `1688-product-find`, linkfox skills | Price / image / listing lookup on 1688 | Yes, data source | Platform tooling, not county-level cluster reasoning |
| `china-{tools,luggage,industrial-machinery,...}-sourcing` | Industry-specific cluster intel | No | One industry per skill, static datasets, no cross-category routing |
| `anythingchina-sourcing` | RFQ, quote comparison, evidence records | No | Excellent later-stage workflow; does not identify the production region |
| `source-scout`, `supplier-sourcing-workflow` | Product-link reverse lookup / heavy multi-stage research | Needs live web search | Different entry point and much heavier runtime |

This skill is vendor-neutral, covers all product categories, works offline, and can be combined with any of the above.

## Design decisions

- **Zero dependency.** Pure Markdown, so it behaves identically in Codex, OpenClaw, Claude Code and WorkBuddy.
- **No invented data.** No company names, contacts, prices, MOQs, badges or market-share figures. Example rows are labelled `synthetic`.
- **Stable vs time-sensitive.** Geography, cluster specialisation and channel mechanics are written down. Prices, exchange rates, freight, platform badges, policies and event dates are deliberately never hardcoded; each reference carries a `Last verified` line.
- **Cluster ≠ market.** Yiwu, Huaqiangbei and Lecong are trade hubs, not factory locations. This is stated everywhere it matters.
- **Capability stack before product name.** Firmware, voice, AI, app and backend customisation usually belong to a solution house, not the assembly factory. The skill routes those layers separately, asks which technical route and delivery model is meant, and never treats a first-tier-city R&D address as automatic proof of an intermediary.
- **Say when geography cannot answer.** Backend platforms, cloud services, transcription dashboards, data hosting and private deployment are not made in a county-level cluster. The skill states this plainly, switches those layers to delivery-model / data / IP / service-term criteria, and reverses the order: fix the software specification first, then source the hardware layers through the cluster route. It never invents a county for a layer that has none.
- **Trading companies are not the enemy.** They add real service. The skill makes their role explicit and only routes around them when direct contact is worth the effort.
- **Retail excluded.** B2B sourcing of goods made in China only.

## Contributing

Cluster boundaries shift and platform labels change. Corrections are welcome — see [CONTRIBUTING.md](CONTRIBUTING.md). Please cite an official cluster list or a local government / industry source, avoid percentage claims, and update the `Last verified` date.

## Disclaimer

Cluster attribution is indicative and must be independently verified. Nothing here is legal, customs, tariff, sanctions, export-control, certification or investment advice, and nothing here guarantees a supplier's reliability or the outcome of a transaction. Verify counterparties, use sample orders and pre-shipment inspection, and obtain competent advice where regulated products or cross-border compliance are involved. Only public entry points and manual steps are described; this project does not scrape or bypass access controls.

## License

Code and skill structure: MIT. Documentation (`README*`, `references/`, `assets/`): CC BY 4.0. See [LICENSE](LICENSE).
