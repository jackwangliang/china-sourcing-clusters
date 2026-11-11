# Verification, enquiry and comparison

Last verified: 2026-11-10. Document requirements, certification schemes, platform policies and trade terms change. Confirm current requirements with a qualified adviser and with the counterparty.

## Fix the specification before collecting quotations

No two quotations are comparable until the specification is fixed. Draft it before approaching suppliers, and send the identical specification to every candidate.

| Field | Applies to | Note |
| --- | --- | --- |
| Product name and intended use | All | Include a photo or drawing where possible |
| Material, grade, composition | All | Use the standard designation, not a marketing name |
| Dimensions and tolerances | All | Numbers plus units; repeat critical values in Chinese and in figures |
| Surface finish / colour / artwork | Most | Reference a physical sample or a signed artwork file |
| Process and in-house vs subcontracted steps | All | Ask which steps the entity performs itself |
| Quantity, target MOQ and annual volume | All | State trial quantity and expected repeat volume separately |
| Packaging, labelling, barcodes | All | Include inner and outer pack, carton markings |
| Technical standard | Industrial / regulated | Name the standard and edition only after checking the current version |
| Testing and inspection requirements | All | Define acceptance criteria and who pays for inspection |
| Tooling / mould ownership | Custom / OEM | State who owns, stores and may move the tooling |
| Samples | All | Sample charge, lead time, courier, and whether the sample matches production |
| Delivery term and destination | All | Name the Incoterm and the named place; do not leave it implied |
| Payment terms | All | Deposit, balance trigger, and the exact contracting entity |
| Warranty and defect remedy | All | Agree in writing before the first order |

Machine translation garbles dimensions, tolerances and grades. Keep critical values in Chinese plus numerals plus the standard designation, and confirm them with the supplier in writing.

## Software, service and data fields

When the purchase includes a backend, cloud service, app or managed service, these fields are as binding as the hardware specification. Quote them separately — a hardware unit price and a service subscription are not comparable line items.

| Field | What to fix | Why it matters |
| --- | --- | --- |
| Delivery model | Off-the-shelf device with the vendor's SaaS; custom hardware integrated into the buyer's backend; or a full hardware-plus-software package with private deployment | Determines the lead supplier, the contracting party and who carries data liability |
| Backend function list | Device management, recording files, real-time / offline transcription, speaker diarisation, minutes, search, account roles, audit log, open API | Prevents "has a backend" from meaning three different things |
| Deployment and data | Public cloud / private deployment / fully offline intranet; who owns the servers; data location; cross-border transfer; retention and deletion; encryption; voiceprint or other biometric handling | Ask, never assert a compliance conclusion |
| Third-party dependencies | Which ASR / LLM / cloud services are used, who contracts with them, who pays usage fees, and what happens if a service is discontinued | Exposes hidden continuing costs and single points of failure |
| IP and deliverables | Source code, deployment package, SDK licence, admin account ownership, right to modify, tooling ownership | The core of any "custom" claim |
| Continuing commercial terms | Subscription or licence, API usage, updates and maintenance, SLA, support, and data export / business continuity on termination | A one-off unit price hides these |
| Service-side compliance | Which schemes apply, who holds them, who is responsible | Ask; do not certify |

## Enquiry structure

Use `assets/rfq-template.md`. A workable enquiry has five parts:

1. **Who you are and what the order is** — company, market, expected volume, trial quantity
2. **The fixed specification** — the table above, sent as an attachment or inline
3. **The role question** — are you the manufacturer; what is the producing entity's legal name and registered address; which processes are in-house
4. **The quote request** — unit price at each quantity break, tooling, sample, packaging, lead time, delivery term, payment terms, quote validity
5. **The verification request** — business licence, production scope, equipment list, certificates (as claims), sample and pre-shipment inspection acceptance

Send the same text to every candidate. Do not send it on the user's behalf; produce the draft only.

## Documents to request

Separate a **claim** (the supplier says so) from **evidence** (independently checked).

| Request | What it is | Status |
| --- | --- | --- |
| 营业执照 / business licence, with 经营范围 | Registered legal name, address, scope | Claim until checked in a public registry |
| Production / environmental / discharge permits where the process requires them | Legal ability to operate that process | Claim until the issuing authority is checked |
| Equipment list, workshop layout, capacity, headcount | Capability evidence | Claim; verify on a site visit or live video walk |
| ISO, product, safety or test certificates | Scheme documents | Claim; check issuer, scope, holder name and validity |
| Export records, references, tender or patent records | Track record | Public signals, not certification |
| Sample and QC report | Product evidence | Verify by independent testing where risk justifies it |
| 软件著作权 / software copyright, deployment package and interface documents | Evidence of a real software deliverable | Claim until checked against the contracting entity |
| Data handling description: hosting, retention, deletion, third-party processors | Where recordings and transcripts actually go | Claim; obtain competent compliance advice |
| Service level, update and termination terms | Continuing obligation, not a one-off shipment | Contractual claim; read before comparing prices |

Never state that a named supplier holds any of these. State that they are the documents to request.

## Capability verification sequence

1. Confirm the legal entity in a public company registry; compare name, address and business scope with the contract counterparty.
2. Confirm whether the address is a production site or an office, and whether it sits in the cluster named in `cluster-map.md`.
3. Request a dated live video walk of the raw-material area, production line, QC station and warehouse. A showroom tour is not a factory audit.
4. Cross-check capacity claims against equipment, staffing and lead time.
5. Order a sample before a bulk order; test it against the fixed specification.
6. Agree pre-shipment inspection and a written defect remedy.
7. For higher-value or regulated orders, commission an independent audit. This skill names no provider.

## Comparable quotation rules

A cheaper quote is not comparable if the scope differs. Normalise these before ranking:

- Same specification ID, quantity breaks and currency
- Same Incoterm and same named place; freight, insurance, duty and tax treatment stated separately
- Tooling / mould cost separated from unit price, with ownership stated
- Sample charge, packaging, artwork and testing separated
- MOQ, lead time, quote validity and warranty stated
- Whether the quote comes from a factory, an agent or a trading company stated, because their service scope differs
- Payment terms and the contracting entity stated

`assets/supplier-scorecard.csv` provides fields for this. It does not compute a winner; the user decides the weighting.

## Red flags

- Price far below every comparable quote without a stated reason
- Refusal to give the producing entity's legal name or registered address
- Registered scope limited to 销售 / 贸易 / 货物进出口 while claiming to manufacture
- Certificate holder, invoice party and bank account holder are different entities
- Payment requested to a personal account, or a change of bank details late in the process
- Pressure to pay in full before verification, samples or a written specification
- Only catalogue or stock imagery; no dated evidence of a production line
- "Factory direct, no MOQ" combined with a very broad catalogue
- Vague or shifting answers on which processes are subcontracted

## Payment and risk reminder

Verify the counterparty before paying. Use a sample order before a bulk order, keep the contract party, invoice party and bank account holder consistent, avoid personal-account transfers for a first order, and agree inspection and defect remedies in writing. A platform badge or a "verified" label is a claim, not a guarantee.

## Boundaries

This file produces drafts, checklists and comparison structures. It gives no legal, contractual, customs, tariff, sanctions, export-control, certification-validity or IP advice, no supplier names or contact details, no current prices, and no guarantee of any supplier's reliability or any transaction outcome.
