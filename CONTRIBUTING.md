# Contributing

Corrections to production clusters, Chinese terminology and channel mechanics are welcome. This is a knowledge project; accuracy matters more than volume.

## What to contribute

- A missing or misattributed county-level cluster entry in `references/cluster-map.md`
- A corrected administrative division (province / city / county / town)
- Better Chinese search terms actually used in that trade
- A note that a place is a **wholesale market** rather than a production base
- A correction to a channel description in `references/channel-matrix.md`
- A clearer diagnostic signal in `references/bypass-trading-companies.md`

## What not to contribute

- Company names, supplier lists, contact details, prices, MOQs, stock or current quotations
- Market-share, output-volume or "X% of the world's..." claims
- "Capital of X" style promotional titles stated as fact
- Hardcoded exchange rates, freight rates, platform fees, badge names as facts, trade-show dates or standard edition numbers
- Scraping instructions, login / CAPTCHA / paywall / anti-bot bypass, or private data
- Retail, dropshipping or consumer-shopping use cases — they are out of scope by design
- Legal, customs, sanctions, export-control or certification-validity conclusions

## Source requirements

For a new or changed cluster entry, cite at least one of:

1. 工信部《中小企业特色产业集群名单》(MIIT national county-level cluster lists) or a provincial equivalent
2. A provincial / municipal / county industry and information technology department publication
3. A local government industry page or an industry association description
4. A public cluster directory, used as a **lead only** (commercial directories are not authoritative)

Prefer two independent sources for a new entry. State the source name in the PR description; do not paste long quotations. Keep the `Note` column short and structural (why the cluster exists), not promotional.

## Entry format

Each row in `cluster-map.md` keeps four fields: category, primary cluster(s) at county/town level, a short structural note, and Chinese seed terms. Keep the province prefix. Mark entries drawn from MIIT lists with `(MIIT)`.

## Before opening a PR

- Update the `Last verified` line at the top of the file you changed
- Keep `SKILL.md` lean; put detail in `references/`
- Keep file references one level deep from `SKILL.md`
- Do not add dependencies: no API keys, no network calls, no scripts, no telemetry
- Validate the skill frontmatter still matches the [Agent Skills specification](https://agentskills.io/specification)
- Check that `name` still matches the directory name and that the `description` is a single line without angle brackets

## Reporting a problem

Open an issue with the product category, the place name in question, and the source that contradicts the current entry. Do not include supplier enquiries, contracts, credentials or personal contact lists in issues.
