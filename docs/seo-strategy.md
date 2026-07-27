# Cypher — SEO Architecture & Keyword Map

**Status:** Draft for review
**Date:** 27 July 2026
**Domain:** getplatformone.com

---

## 1. The positioning rule this is built around

The brand surface stays geography-free. Regulatory search demand is captured by a
**sector-regulator layer** presented as *industry breadth*, not *market limitation*.

The regulators Cypher actually speaks to — NDPR/NDPA, CBN, PenCom, NAICOM, NHIA — are
all Nigerian, so a list of them cannot masquerade as international coverage. Do not
try. Instead, present the layer by **sector**: pensions, insurance, banking, health,
capital markets. That reads as "we cover every regulated industry," which is both true
and the thing a buyer self-identifies with. A PFA compliance officer searches for their
regulator's requirements, not for "AI governance."

The geography-free positioning is therefore carried by the **product surface**, which
is genuinely universal — monitor, enforce, and audit are not location-specific
capabilities. The regulator pages sit in a subdirectory a global visitor never has to
pass through.

> **Do not publish a compliance page for a framework the product has not been mapped
> against.** GDPR, POPIA, and the EU AI Act were in an earlier draft of this document
> and have been removed: there is no basis for the claim today, the pages would be thin,
> and unsupported compliance claims to a regulated buyer are a commercial risk, not just
> an SEO one. Add them if and when the mapping work is genuinely done.

### Geo guardrails — what may appear where

| Surface | "Nigeria" / "Africa" | Regulator names | BVN / NIN / NUBAN |
|---|---|---|---|
| Homepage (PlatformOne) | Never | No | No |
| `/cypher/` product home | Never | Named as sectors, not regulators | Yes — as capability examples |
| `/cypher/*` capability + use-case pages | Never | No | Yes — as capability examples |
| `/regulators/` hub | Never — frame by sector | Freely | Freely |
| `/regulators/<name>/` pages | Freely | Freely | Freely |
| `/resources/*` blog posts | Per post topic | Freely | Freely |

The hub is the hinge: it is reachable from the product surface, so it must read as
*"pensions · insurance · banking · health"* rather than *"Nigeria."* The individual
regulator pages beneath it are only ever reached by someone already searching for that
regulator, so they can be as specific as they need to be.

**Why BVN/NIN/NUBAN stay on the product pages:** they are unambiguous Nigerian
entities, so Google associates the page with Nigeria without the word appearing.
To a human reader they land as "it detects local identifiers" — capability, not
constraint. This is the single highest-leverage geo signal available at zero
positioning cost.

**Action required:** the hidden `.proof` section on the Cypher page
(`display:none`) currently contains *"African financial systems"* and *"in pilot
with regulated financial institutions in Nigeria."* It is simultaneously the
positioning the CEO doesn't want and worthless for SEO (hidden text is discounted).
Delete it or rewrite it as visible, geo-neutral copy.

---

## 2. Regulatory claims — what we can and cannot say

**No vendor certification exists for CBN, PenCom, NAICOM, or NHIA.** These bodies
regulate *licensed operators* — banks, PFAs, insurers, HMOs — not their technology
suppliers. There is no application to file and no certificate they issue to a software
company. The obligation sits with the customer and stays there: they cannot outsource
it to us, and no regulator's stamp on Cypher would relieve them of it.

So there is nothing to obtain — and nothing to claim.

### What "mapping" means, since it isn't certification

It is an internal documentation exercise, done without any external approval:

1. Read the regulator's published instrument (for CBN, the risk-based cybersecurity
   framework for banks and payment service providers; for PenCom, the guidelines
   applying to licensed pension operators).
2. Identify the specific clauses Cypher genuinely helps satisfy — access control,
   audit logging, data protection, third-party risk, incident evidence.
3. Produce a control-mapping table: *clause → Cypher capability → what the evidence
   looks like*.

Typically a few days per regulator for someone who can read the framework carefully.
The output is not primarily an SEO asset — it is the document a buyer's compliance
officer requests during procurement, so it has to be written to close deals anyway.
The regulator page is a by-product of it.

### The claim-language line

| Safe | Not safe |
|---|---|
| "Supports your CBN cybersecurity obligations" | "CBN-certified" |
| "Maps to PenCom guidelines on X" | "CBN-approved" / "PenCom-approved" |
| "Helps you evidence compliance with…" | "Licensed by NAICOM" |
| "Built for CBN-regulated institutions" | "Makes you CBN-compliant" |

Everything on the left describes what the product does. Everything on the right claims
a regulatory status we do not hold. In a market this small, a compliance officer who
spots an overclaim will kill the deal and tell their peers. **This table governs all
website copy, sales decks, and pitch material — not just the regulator pages.**

### Certifications that do exist, if a badge is wanted

None of these are held today, and none are required at this stage:

- **ISO 27001** — the general-purpose credential enterprise procurement asks for. Real
  audit, real cost, roughly 6–12 months.
- **SOC 2 Type II** — same role, more common with US buyers.
- **NDPC registration** as a data controller/processor — a genuine Nigerian filing under
  the NDPA, and inexpensive. **This one may be an obligation rather than a marketing
  choice; check whether PlatformOne is required to register regardless.**

## 3. URL architecture

Cypher sits on a **subpath, not a subdomain**. Subdomains split link equity; every
backlink Cypher earns should strengthen the whole domain. Revisit only if Cypher
is ever spun out onto its own domain.

```
getplatformone.com/
│
├── /                                  PlatformOne — company / thesis
├── /cypher/                           Cypher product home  ◄ primary commercial page
│   ├── /cypher/monitor/               Capability: discovery & monitoring
│   ├── /cypher/enforce/               Capability: policy enforcement
│   ├── /cypher/audit/                 Capability: evidence & audit trail
│   ├── /cypher/shadow-ai-discovery/   Use case: unapproved AI
│   ├── /cypher/ai-data-leak-prevention/  Use case: sensitive data
│   └── /cypher/ai-agent-governance/   Use case: agents (ships with the feature)
│
├── /regulators/                       Sector-regulator hub  ◄ geo carrier layer
│   ├── /regulators/ndpr/              Data protection — all sectors
│   ├── /regulators/cbn/               Banking & payments
│   ├── /regulators/pencom/            Pensions (PFAs, PFCs)
│   ├── /regulators/naicom/            Insurance
│   └── /regulators/nhia/              Health insurance (formerly NHIS)
│
├── /resources/                        Blog / link-earning content
│   └── /resources/<post-slug>/
│
└── /legal/
    ├── /legal/privacy/
    ├── /legal/terms/
    └── /legal/data-protection/
```

### Build order — do not ship this all at once

Thin, half-written pages actively hurt a young domain. Ship in tiers, each page
carrying 800–1500 words of genuine substance before it goes live.

- **Tier 1 (launch):** `/`, `/cypher/`, `/regulators/`, `/regulators/ndpr/`, `/legal/*`
- **Tier 2 (+4–6 weeks):** `/cypher/monitor/`, `/cypher/enforce/`, `/cypher/audit/`
- **Tier 3 (+8–12 weeks):** `/regulators/cbn/`, then the use-case pages
- **Tier 4 (ongoing):** `/regulators/pencom/`, `/regulators/naicom/`, `/regulators/nhia/`, `/resources/*`

Sequence the regulator pages by where the pipeline actually is. CBN first if banking
is the beachhead; PenCom first if pensions is. Each one requires real mapping work
against that regulator's guidelines before it can be written — this is a compliance
exercise with an SEO by-product, not the other way round.

---

## 4. Keyword map

One page owns one keyword cluster. A page cannot rank for six unrelated things,
and two pages targeting the same term compete with each other (cannibalisation).

> **Volumes are not included deliberately.** I have no keyword-tool access, and
> inventing numbers would be worse than omitting them. Validate every row in Ahrefs
> or Semrush, and cross-check against Search Console once Phase 1 is indexed. The
> difficulty ratings below are directional judgements from SERP composition, not
> measured scores.

### The six CEO targets, and which page wins each

| # | Target query | Owner page | Difficulty | Realistic timeline |
|---|---|---|---|---|
| 1 | AI governance nigeria | `/regulators/ndpr/` | Low | 2–4 months |
| 2 | monitor AI africa | `/resources/` post — see note | Low | 3–5 months |
| 3 | enforce ai policy | `/cypher/enforce/` | High | 9–18 months |
| 4 | monitor AI in organization | `/cypher/monitor/` | High | 9–18 months |
| 5 | track AI use | `/cypher/monitor/` (secondary) | High | 9–18 months |
| 6 | sensitive data protected | **retarget** → `/cypher/ai-data-leak-prevention/` | Medium | 6–12 months |

**On #2:** with POPIA removed there is no product page that can honestly carry
"Africa," and the CEO's rule keeps it off the brand surface anyway. Put it in an
editorial post — *"The state of AI governance for African financial institutions"* —
where a continental framing is natural and commits the product to nothing. Lower
commercial intent than #1, so treat it as secondary.

**On #6:** "sensitive data protected" is not a query anyone with a budget types.
The commercial-intent versions are *prevent data leaks to ChatGPT*, *stop employees
pasting customer data into AI*, *DLP for AI tools*. Target those; the phrase itself
should be abandoned.

**On #3–#5:** these SERPs are held by funded US vendors (Witness AI, Prompt
Security, Nightfall, Zscaler, Netskope) with years of domain authority. Page
quality alone does not displace them — the deciding factor is backlinks. Treat
these as the 12-month goal that the Tier-1 wins fund, not as launch targets.

### Per-page detail — Tier 1 and 2

Titles are written to sit under ~60 characters (they truncate in the SERP beyond
that); meta descriptions under ~155.

---

#### `/cypher/` — product home

- **Primary:** AI governance platform
- **Secondary:** AI governance software, AI control plane, enterprise AI governance
- **Intent:** commercial investigation
- **Title:** `Cypher — AI Governance Platform for Regulated Institutions`
- **Meta:** `Monitor, enforce, and audit every AI tool and agent your organization uses — across the browser, endpoint, and gateway. See Cypher in action.`
- **H1:** See every AI in use. Govern every one.
- **Geo:** none. Framework names permitted only inside a multi-framework list.

#### `/cypher/monitor/` — capability

- **Primary:** monitor AI use in organization
- **Secondary:** track AI usage, AI usage monitoring software, discover AI tools employees use
- **Owns CEO targets:** #4, #5
- **Intent:** solution-aware
- **Title:** `Monitor AI Use Across Your Organization | Cypher`
- **Meta:** `See every AI tool and agent in use — who is using it, from which account, and at what risk. Browser, endpoint, and gateway sensors in one dashboard.`
- **H1:** Monitor every AI tool and agent your organization uses
- **Must cover:** shadow AI discovery, per-user attribution, risk scoring, the three sensor surfaces, dashboard for security/compliance/board

#### `/cypher/enforce/` — capability

- **Primary:** enforce AI policy
- **Secondary:** AI policy enforcement software, AI acceptable use policy enforcement, block unapproved AI tools
- **Owns CEO target:** #3
- **Intent:** solution-aware
- **Title:** `Enforce AI Policy in Real Time | Cypher`
- **Meta:** `Write a policy once and it runs the moment a prompt is sent — allow, warn, redact, or block, scoped to the people, apps, and agents you choose.`
- **H1:** Turn AI policy into live enforcement
- **Must cover:** the four actions, scoping model, real-time enforcement, agent permission changes, worked policy examples

#### `/cypher/audit/` — capability

- **Primary:** AI audit trail
- **Secondary:** AI compliance evidence, prove AI usage to auditor, append-only AI log
- **Intent:** solution-aware, compliance buyer
- **Title:** `AI Audit Trail & Compliance Evidence | Cypher`
- **Meta:** `Every AI decision and policy change written to an append-only, hash-referenced record — evidence you can export for a regulator, not just a log line.`
- **H1:** Prove what happened, long after it happened

#### `/regulators/` — sector hub

- **Primary:** AI compliance for regulated industries
- **Secondary:** AI governance banking, AI governance insurance, AI governance pensions
- **Strategic job:** this is the page a homepage visitor sees, so it must read as
  **sector coverage** — pensions, insurance, banking, health, capital markets — with
  the regulator named as a subheading inside each card, not as the card's headline.
  Do not put "Nigeria" on this page.
- **Title:** `AI Compliance for Regulated Industries | Cypher`
- **H1:** Govern AI against the rules your sector runs on
- **Structure:** short intro + card grid, one card per sector, linking down to the
  regulator page

#### `/regulators/ndpr/` — geo carrier ★ highest-priority ranking page

- **Primary:** NDPR AI compliance
- **Secondary:** AI governance nigeria, NDPR data residency, NDPR compliance software, NITDA AI guidance
- **Owns CEO target:** #1
- **Intent:** problem-aware, high commercial intent
- **Title:** `NDPR Compliance for AI Tools | Cypher`
- **Meta:** `Meet NDPR obligations when your team uses AI: in-region data residency, native BVN, NIN, and NUBAN detection, and an exportable evidence trail.`
- **H1:** NDPR compliance for every AI tool your team uses
- **Must cover:** what the regulation requires of AI processing, data residency,
  BVN/NIN/NUBAN as regulated personal data, evidence and breach-reporting obligations,
  how Cypher maps to each. This is the page that earns Nigerian backlinks and press
  coverage.
- **Terminology — verify before writing:** the site currently says NDPR throughout.
  The NDPR (2019) was issued by NITDA, but the Nigeria Data Protection Act 2023 is now
  the governing statute and the Nigeria Data Protection Commission (NDPC) is the
  regulator. Check which term your buyers actually search — "NDPR" may still have the
  larger search volume through sheer familiarity even where "NDPA" is the correct
  citation. Likely answer: target NDPR in the URL and title, use NDPA/NDPC accurately
  in the body, and say plainly how they relate. Getting this wrong in front of a
  compliance officer costs more than the ranking is worth.

#### `/regulators/cbn/` — sector page

- **Primary:** CBN cybersecurity framework AI
- **Secondary:** AI governance for Nigerian banks, CBN risk-based cybersecurity compliance
- **Sector:** banking, payments, OFIs
- **Title:** `AI Governance for CBN-Regulated Institutions | Cypher`
- **Prerequisite:** the internal control mapping described in §2. No CBN approval is
  involved or available — cite the specific instrument and stay on the safe side of the
  claim-language table.

#### `/regulators/pencom/` — sector page

- **Primary:** PenCom data security guidelines
- **Secondary:** AI governance pension fund administrators, PenCom IT risk compliance
- **Sector:** pensions (PFAs, PFCs)
- **Title:** `AI Governance for PenCom-Regulated Operators | Cypher`
- **Prerequisite:** same as CBN — internal mapping per §2, no PenCom approval involved.

#### `/regulators/naicom/` and `/regulators/nhia/` — sector pages

Same pattern, for insurance and health insurance respectively. NHIA is the successor
to NHIS under the NHIA Act 2022; use the current name and note the former one once, so
searches for either term land here.

#### `/cypher/ai-data-leak-prevention/` — use case

- **Primary:** prevent data leaks to AI
- **Secondary:** DLP for ChatGPT, stop employees pasting customer data into AI, AI data loss prevention
- **Owns CEO target:** #6 (retargeted)
- **Title:** `Stop Sensitive Data Leaking Into AI Tools | Cypher`
- **Meta:** `Catch customer records, IDs, and internal documents the moment someone pastes them into an AI tool — and block or redact before they leave.`

#### `/cypher/shadow-ai-discovery/` — use case

- **Primary:** shadow AI discovery
- **Secondary:** unapproved AI tools, discover AI in SaaS, block unsanctioned AI
- **Title:** `Shadow AI Discovery | Cypher`

---

## 5. Internal linking rules

Link equity should flow *toward* the pages that must rank, and the compliance layer
should feed the product layer.

- Every `/regulators/*` page links to `/cypher/` and to the two most relevant
  capability pages, in body copy, with descriptive anchor text.
- Every `/cypher/*` capability page links to `/regulators/` — **the hub only, never a
  specific regulator page.** This is what keeps the product surface geo-free: the link
  reads "for regulated industries," not "for Nigerian banks."
- `/cypher/` links to all three capability pages and to `/regulators/`.
- The homepage links to `/cypher/` prominently.
- **Anchor text:** descriptive, varied, never "click here" and never the same exact
  phrase site-wide. Match the target page's primary keyword loosely, not exactly.

---

## 6. Technical requirements (blocking — Phase 1)

None of the above ranks until these are done. The current build serves all pages
from inside `<script type="text/plain">` blocks injected into `iframe.srcdoc` with
`#hash` routing, which means Google sees one URL containing `<div>Loading</div>`.

- [x] Un-bundle into real static HTML files at real URLs
- [x] `robots.txt`
- [x] `sitemap.xml` written — **still to be submitted in Search Console**
- [x] `rel="canonical"` on every page
- [x] Open Graph + Twitter Card tags — currently **zero** across the entire site
- [x] JSON-LD: `Organization` + `WebSite` (/), `SoftwareApplication` + `BreadcrumbList`
      (/cypher/), `WebPage` (/legal/). **`FAQPage` deliberately omitted** — Google requires
      the Q&A to be visible on the page, and no page has real question/answer content yet.
      Add it if a genuine FAQ section is written.
- [ ] Google Search Console verified
- [x] Images extracted to `/assets/`, WebP + responsive `<picture>` srcset added.
      Console screenshot 153KB → 24KB. **Hero photo barely improved (321KB JPEG → 318KB
      WebP)** — it is grainy, already-compressed source material that WebP cannot help;
      the 1200px variant (126KB) is what actually cuts LCP on smaller screens. Consider
      re-exporting the hero from the original at a lower resolution.
- [x] One `<h1>` per page; heading hierarchy not skipping levels

---

## 7. Off-page — the part that decides #3–#5

Domain authority, not page quality, is what stands between you and the generic
global keywords. Ranked by leverage:

1. **Link-earning asset:** a genuinely definitive *AI compliance checklist for Nigerian
   regulated institutions*, covering NDPR/NDPA plus the sector regulators. Nobody has
   written it. It is the single most linkable thing this company can publish, and it
   doubles as sales collateral.
2. **Tech press:** TechCabal, Techpoint Africa, BusinessDay — a funding or launch
   announcement is a legitimate link, and these publications rank well.
3. **Software directories:** G2, Capterra, Product Hunt.
4. **Google Business Profile** — improves local-intent visibility without adding a
   single geographic word to the website itself.
5. **Founder-led content:** conference talks, podcasts, guest posts on security blogs.

---

## 8. Measurement

Review monthly:

- Search Console: impressions and average position per target query, per page
- Indexation: pages submitted vs. pages indexed (should be ~100% at this size)
- Referring domains, tracked over time — the leading indicator for #3–#5
- Conversions: demo requests attributed to organic

**Set expectations now:** nothing moves for the first 6–8 weeks after Phase 1;
that's indexation lag, not failure. The NDPR page should show first movement.

---

## Open questions

1. Does Cypher stay on `getplatformone.com/cypher/` long-term, or is a dedicated
   domain planned? Changing later costs a redirect migration and some ranking.
2. Who writes the 800–1500 word pages? This is the real constraint on the timeline,
   not engineering.
3. Is the Nigerian pilot referenceable by name? A named regulated-institution logo
   is worth more than any of the above.
4. **Who does the control mapping, and when?** None has been done yet, and it gates the
   whole Tier 3–4 build. Not an external process (see §2) — but it needs someone who can
   read the framework and say which control Cypher satisfies. Days, not months, per
   regulator. **Decide this before promising any Tier 3 date.**
5. Do we say NDPR or NDPA? See the terminology note on `/regulators/ndpr/`.
6. **Is the near-term market financial services only?** ← *decides the architecture.*
   If yes, CBN and PenCom are the only regulator pages worth writing this year, and
   NAICOM and NHIA come out entirely rather than sitting as empty stubs.
7. Is PlatformOne required to register with the NDPC as a data controller/processor
   under the NDPA? This is a legal question, not a marketing one — answer it
   independently of anything in this document.
8. Does the CEO want to pursue ISO 27001 or SOC 2? Neither is needed now, but both are
   long lead-time, so the decision is worth making deliberately rather than at the
   moment a procurement team first asks.
