---
name: china-sourcing-clusters
description: Helps overseas B2B buyers find the real county-level production cluster behind any Chinese product and reach source factories instead of tier-1-city trading companies. Use when a user asks where a product is made in China, which region or 产业带 / 生产基地 to source it from, how to find a Chinese manufacturer or factory for a product, how to tell a factory from a trading company, which sourcing channels to use, which Chinese search terms to paste, or how to prepare an RFQ for China sourcing. Also covers smart and connected goods whose customisation sits in firmware, voice, AI, app, SDK, backend platform, admin console, cloud service or data-hosting layers, where the whole-unit factory is not the party that owns the requested capability. Triggers also include backend, admin console, dashboard, transcription, SaaS and private deployment. Covers all product categories. Not for retail shopping, dropshipping, or single-unit consumer purchases.
license: MIT
compatibility: Agent Skills open format. Self-contained Markdown; the skill itself needs no API key, scripts, bundled database or network access. Optional public-record research uses the host agent's own tools. Compatible with Codex, OpenClaw, Claude Code, WorkBuddy, Cursor and other agents that load SKILL.md.
metadata:
  version: "0.3.1"
  docs-license: "CC BY 4.0"
  last-verified: "2026-11-10"
---

# China Sourcing Clusters

## Purpose

Turn a product description into a geographically grounded sourcing route: identify the county-level production cluster where that product is actually made in China, then supply the channels, Chinese-language search terms and verification steps needed to reach the factory rather than an intermediary.

## The problem this skill exists to solve

Chinese manufacturing is organised in dense county-level industrial clusters, known as 产业带 or 生产基地. A single town or county often concentrates one product category together with its raw materials, tooling, mould makers, subcontractors, surface treatment, packaging, testing and freight. A new specification can frequently be quoted and sampled within a few kilometres.

Overseas buyers usually never see these clusters. English search results, B2B platform rankings, paid placements and trade-show booths are dominated by export trading companies based in Shanghai, Shenzhen, Guangzhou, Beijing, Hangzhou and other first-tier cities. Those firms invest in English websites, SEO, platform advertising and English-speaking sales teams. The factories in cluster towns generally do none of this: many have no English website, no overseas marketing staff, and no incentive to learn overseas promotion. They sell through domestic wholesale markets, local agents, or as subcontractors to the trading companies.

The result is a structural information asymmetry, not a search-engine problem. A buyer who searches in English for "Chinese manufacturer of X" reliably reaches the intermediary, because the intermediary is the only party visible in English. **Fix the geography first.** Once the production county is known, the buyer can search in Chinese, filter by registered address, and approach suppliers on the factory's own terms.

## Scope

**In scope**, for any product category made in China:

- Locating the production region, cluster or 产业带 for a product or component
- Explaining the supply-chain structure of a cluster and why it is located there
- Choosing which sourcing channels are likely to surface cluster factories rather than intermediaries
- Building Chinese-language search queries, including local place names and factory-signalling terms
- Distinguishing a manufacturer from a trading company, and designing a route around the intermediary
- Preparing an enquiry, a verification checklist and a comparable supplier scorecard
- Advising on what to ask a supplier for, and what must be independently verified

**Out of scope — decline or redirect these requests:**

- Retail and consumer shopping: B2C marketplaces, "where can I buy one", single-unit or sample-only purchases, dropshipping, consumer arbitrage and resale-listing price checks
- Any request whose real goal is buying a finished consumer item for personal use
- Live company databases, named factory lists, contact details, current prices, MOQs, freight rates or stock availability
- Verification of a supplier's claims, certificates, licences or audit results
- Legal, contractual, customs, tariff, sanctions, export-control, IP or certification-validity determinations
- Sending enquiries, negotiating, placing orders, arranging payment or arranging inspection on the user's behalf

## Workflow

### Step 0 · Screen the request

Determine whether this is a B2B sourcing question about a product made in China. If the request is retail, consumer, dropshipping or single-unit in nature, state plainly that the skill does not cover retail sourcing and stop. Do not stretch the workflow to fit.

### Step 1 · Resolve the product into a category and a production process

Extract from the user's input: what the item is, its main material, the manufacturing process it implies, whether it is a finished good or a component, and the intended order type (stock item, private label, custom/OEM, or industrial specification). Ask for the missing minimum rather than guessing. Note that an industrial component is often best matched by process capability, while a consumer good is best matched by product category; use whichever gives a cleaner cluster match.

**Split the capability stack for smart or connected goods.** When the request contains a functional or software requirement — custom voice dialogue, wake words, firmware, an app, SDK or API access, AI features, a backend, an admin console, a cloud service, private deployment, a wireless protocol, a voice-assistant ecosystem, or a named certification — the finished-good factory usually does not own that capability. Routing by the product name alone will land on an assembly plant that can only subcontract it. Decompose the product into the layers below, as detailed in `references/cluster-map.md`:

| Layer | Who owns it | How to route it |
| --- | --- | --- |
| Functional solution (firmware / voice / AI / SDK) | Solution house, module maker, 机芯 or board supplier | Route by capability; often an R&D district in a first-tier city, sometimes outside the product's cluster |
| Backend platform, cloud service and data hosting | Software vendor, system integrator or service operator | **No cluster answer** — select by delivery model, data location, IP ownership and service terms |
| Chipset and module selection | Usually specified by the solution house | Do not route by cluster; ask who selects it |
| Key components | Component specialists | Their own cluster, which may differ from assembly |
| Whole-unit ODM (tooling, moulding, SMT, assembly, certification) | Assembly factory | The county-level production cluster |

Identify the layer carrying the buyer's differentiating requirement and route it **first**; give the other layers as separate targets with their own Chinese queries. Ask which layer each candidate performs in-house — "we can customise" often means subcontracting. Prefer a two-sided reverse lookup: ask the solution house which factory runs its volume production, and ask the assembly factory who supplies its firmware or backend; when both answers meet, the real chain is visible.

**Say plainly when the cluster map does not apply.** Backend platforms, admin consoles, cloud services, ASR / LLM APIs, transcription dashboards, data hosting, private deployment, ongoing subscriptions and the compliance of a *service* rather than a device are not manufactured in a county-level cluster. Never force a county or town name onto them. State that the geography layer cannot source them, and switch the selection criteria to: what is actually delivered (software, source, deployment package, API, SLA), who operates the service, where data is stored, who owns accounts and IP, and what the continuing commercial terms are. Keep these as questions and verification items in the Route Card. The skill's value here is honesty about its own boundary, not an invented location.

**Reverse the order when software decides the purchase.** When the differentiating requirement is a backend, deployment model or data-handling rule, fix that specification first, select the software / system supplier on capability, and only then source the hardware layer through the cluster route — or ask the selected supplier which factory builds its hardware. The "fix the geography first" rule applies to the hardware layers, not to the whole purchase. Do not let the cluster map pretend to answer the part it cannot answer.

**Do not equate a first-tier-city address with an intermediary.** For R&D-intensive goods, genuine solution houses, software firms and ODM headquarters do sit in first-tier cities while their production lines sit in surrounding industrial districts or neighbouring cities. Decide from the registered business scope and the production-site address, never from the city name. The tier-1-city pattern describes where export marketing concentrates; it is a strong prior, not a verdict.

**Ask which technical route and delivery model is meant before naming suppliers.** "Custom voice dialogue" may mean offline wake words and fixed commands, cloud ASR plus an LLM, or customisation inside an existing voice-assistant ecosystem. A "backend" may mean device management, transcription and minutes, or a full private deployment. Delivery may be an off-the-shelf device with the vendor's SaaS, custom hardware integrated into the buyer's own backend, or a full hardware-plus-software package with source / deployment-package handover. These lead to different lead suppliers, contracts, data liability and IP ownership. Present the options and ask, rather than guessing.

### Step 2 · Locate the cluster

Load `references/cluster-map.md` and match the category or process to a production region at province / city / county or town level. Record the primary cluster, one or two alternative clusters, and the reason the cluster exists there (raw material, historical specialisation, upstream supply, port access or a local wholesale market).

Distinguish three things that are routinely confused: a **production cluster** (where goods are made), a **wholesale market** (where goods are traded, often from many regions) and a **showroom or export office** (where goods are displayed). Yiwu, Huaqiangbei and Lecong are primarily trade and distribution hubs; naming them as "the factory location" is a common and costly mistake. Flag this explicitly whenever such a hub appears in the answer.

If no entry matches, use the fallback procedure in `references/cluster-map.md` and label the result **inferred**, not verified. Never present a guess as a known cluster.

### Step 3 · Rank the channels

Load `references/channel-matrix.md`. Rank two or three channels by their ability to surface a factory inside the identified cluster, and state the trade-off for each. Prefer channels that allow filtering by registered address, production scope or domestic-market presence. Explain why generic English-language search and top-ranked B2B listings tend to return intermediaries.

### Step 4 · Build Chinese-language queries

Load `references/chinese-search-terms.md`. Produce queries the user can paste directly, combining the product term with the cluster place name, process words and factory-signalling terms. Keep the Chinese terms verbatim and give a short English gloss for each. Also provide the reverse-lookup queries used to check whether a named company is registered in the cluster. When a backend, cloud or data layer is present, produce a **separate** query set for it without county names and say explicitly that this layer is not selected by production geography.

### Step 5 · Separate factories from trading companies

Load `references/bypass-trading-companies.md`. Apply the diagnostic signals to any supplier the user is already considering, and give the concrete route for bypassing the intermediary where appropriate. Present working with a trading company as a legitimate option for small or mixed-category orders, not as a fraud; the skill's job is to make the choice explicit.

### Step 6 · Deliver the enquiry and verification pack

Load `references/verification-rfq.md`. Produce an enquiry draft and a verification checklist, and point to the templates in `assets/`. Include the specification fields that must be fixed before any quotation is comparable, and list the documents to request rather than asserting that any supplier holds them.

## Output contract · Sourcing Route Card

Structure every substantive answer with these sections. Omit a section only when genuinely not applicable, and say why.

1. **Product and category** — what is being sourced, the material/process it implies, and for smart or connected goods the capability-stack split with the layer that owns the buyer's custom requirement, flagging any layer for which the cluster map does not apply
2. **Primary production cluster** — province, city, county/town, plus the reason it clustered there
3. **Alternative clusters** — one or two, with the different order type each suits
4. **Cluster vs market** — an explicit note if a trade hub is involved
5. **Ranked channels** — two or three, with the trade-off of each
6. **Chinese search terms** — paste-ready, with English glosses
7. **Factory-or-trader signals** — what to check, and the concrete bypass route
8. **Enquiry and verification** — the specification fields, documents and checks to run
9. **Confidence and unknowns** — what is a stable geographic fact, what is indicative, what must be verified, and what this skill cannot know

## Non-negotiable rules

- Never invent company names, factory names, URLs, contact details, prices, MOQs, capacities, certifications or market-share figures. All illustrative data must be labelled `synthetic`.
- Never quote percentage claims such as "X% of the world's supply" unless the user supplies a source. Cluster attribution is **indicative** and must be labelled as such.
- Never hardcode exchange rates, freight rates, platform fees, platform policies, trade-show dates or standard version numbers into an answer. Point to the need for a current check instead.
- Separate stable facts (geography, cluster specialisation, channel mechanics) from time-sensitive facts (prices, rankings, badges, policies, event dates). Include a `Last verified` line when citing a reference file.
- Never treat a supplier's self-description, platform badge or uploaded certificate as verified fact. State that these are claims requiring independent confirmation.
- Use only public entry points and manual, human-executable steps. Do not instruct scraping, bypassing logins, CAPTCHAs, paywalls, anti-bot controls or platform access restrictions.
- Never guarantee a supplier's reliability, a product's compliance, or the outcome of a transaction. Add a short plain-language risk reminder on payment, samples and pre-shipment inspection.
- State that the skill provides no legal, customs, tariff, sanctions, export-control, certification or data-compliance advice, and that the buyer must obtain competent advice where those apply.
- Keep the answer in the user's language; keep Chinese terms verbatim because they are search strings, not prose to translate away.

## Reference index

| File | Load when |
| --- | --- |
| `references/cluster-map.md` | Locating a production region, splitting a smart product into capability layers, or no direct match exists |
| `references/channel-matrix.md` | Choosing where and how to search |
| `references/chinese-search-terms.md` | Building paste-ready Chinese queries, including solution-layer and platform-layer terms |
| `references/bypass-trading-companies.md` | Diagnosing an intermediary, or routing around one |
| `references/verification-rfq.md` | Drafting an enquiry, verification checklist or scorecard, including software / service / data fields |
| `assets/rfq-template.md` | Producing an enquiry document |
| `assets/supplier-scorecard.csv` | Comparing suppliers on like-for-like terms |
| `assets/shortlist-template.csv` | Recording candidates with provenance |

Keep file references one level deep. Load a reference only when the step calls for it.
