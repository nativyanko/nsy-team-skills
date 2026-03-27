---
name: nsy-proposal-builder
description: Build complete client audit and creative strategy proposals for NSY Digital in Notion, including pricing tables. Use this skill whenever the strategist says "build a proposal", "create a proposal", "start the proposal", "proposal for [client]", "build the pitch", "create the pitch doc", "pitch for [client]", "pricing section", "add pricing", "build pricing tables", or any variation of wanting to create or update a client-facing audit and proposal document. Also triggers when the strategist mentions needing to scope out deliverables, build a pricing page, structure a pitch, or set up a proposal page for a new client. This skill handles the full proposal lifecycle from page creation through pricing tables and next steps. Always use this skill for proposal work - do not attempt to build proposals from scratch without it.
---

# NSY Proposal Builder

Build complete client audit and creative strategy proposals in Notion for NSY Digital.

## Template Reference

The canonical template is the Mission proposal: `https://www.notion.so/326df9f700e58061a877d73abec72178`

**IMPORTANT**: This page contains embedded images, videos, and visual assets that Claude cannot see or replicate. When building a new proposal, Claude should create the text/table structure and remind the strategist to manually add images, videos, logos, and visual assets afterwards.

---

## Phase 1: Discovery — Ask Before Building

Before writing anything, Claude MUST gather the following from the strategist. Use these questions as a checklist:

### About the Client
1. **Client name** and website URL
2. **What products/SKUs** are we focusing on?
3. **What's their current Meta spend** (monthly)?
4. **What's their current Google spend** (if any)?
5. **Key data points** — new customers/month, CAC, ROAS, LTV, repurchase rate, subscription rate, AOV
6. **Who are the key contacts** (names, roles)?
7. **Who referred them** (for the "Who We Are" logo swap)?

### About the Scope
8. **What are we pitching?** Choose all that apply:
   - Video ad creative only
   - Video ad creative + Meta ads management
   - Meta ads management only
   - Google Ads (ongoing management or one-off audit/restructure)
   - Static ad creative
9. **How many video concepts per month** are we proposing? (This determines the tier structure)
10. **What's their budget range** from the discovery call?
11. **Are we including in-person creative planning sessions?**
12. **What agreement length** — 3 months (default) or other?

### About the Pitch
13. **When is the pitch meeting?** (date, time, location)
14. **What case studies** should we include?
15. **Any specific creative observations** from the ad account audit?

---

## Phase 2: Proposal Page Structure

Create a Notion page inside the "Audits and Proposals" database. The page follows this exact section order:

### Section Order
1. **What's Inside** — Gray callout block listing all sections
2. **Partnership Goals** — 3-column layout (Scale TOF Creative, Make Meta Scalable, Own the Category)
3. **Who We Are** — Blue callout + logo grid (strategist adds logos manually)
4. **Creative Strategy Audit**
   - Reviewing Your Top Ad (2-column: metrics left, video embed right)
   - Key Observations (numbered H3 headings, typically 8-11 observations)
   - What's Missing (numbered H3 headings, typically 6-8 gaps)
   - The Fix (3 bold levers summary)
   - Why More Creative Volume (with Meta Andromeda reference)
5. **Angles/Concept Ideas** — 3-column layout, each concept has:
   - Purple callout: Messaging / Frame
   - Blue callout: How the video will look (full script breakdown)
   - Green callout: Core Message
6. **Video Examples** — 3-column layout (strategist embeds videos manually)
7. **Quick Wins — Offer and AOV Optimisation**
8. **Meta Ads Management** (if applicable)
9. **Google Ads Opportunity** (if applicable)
10. **How We Work**
11. **Roadmap** — Month 1, 2, 3
12. **Case Studies** (strategist adds screenshots manually)
13. **Pricing and Deliverables** (see Phase 3)
14. **Next Steps**

---

## Phase 3: Pricing Section — The Critical Part

This is the most important section to get right. The pricing section is structured into **separate sections** based on what's being offered, NOT combined into one table.

### Tier Structure

All creative packages use three tiers displayed in a 3-column layout:

| | Platinum (left) | Gold (middle) | Silver (right) |
|---|---|---|---|
| Purpose | Anchor high | Target tier | Entry point |
| Color | blue_bg | yellow_bg | gray_bg |

The strategist provides the monthly prices and concept counts. Claude calculates the per-ad price:

```
Per-ad price = Monthly price ÷ (concepts × 4 variations)
```

Example: £7,000 ÷ 56 ads = £125 per ad

**Display per-ad price prominently** under each tier heading (e.g., "### £125 per ad"). This shows value scaling — more volume = lower per-ad cost.

### Section 1: Video Ad Creative Only

**Header:** `# Video Ad Creative Pricing`
**Subheader:** `3-month agreement.`

Each tier column contains a table with these rows:
- **Header row**: Deliverable | What's Included | Price
- **Video Concepts row**: Lists concept count, total ad count (concepts × 4), and full deliverables list:
  - ✅ [X] video ads ([Y] Concepts x 4 variations)
  - ✅ Research
  - ✅ Angle Hypothesis and Strategy
  - ✅ Scriptwriting
  - ✅ Briefing
  - ✅ Creator Sourcing
  - ✅ Creator management and communication
  - ✅ Editing
  - ✅ Full usage rights in perpetuity
  - ✅ Access to all raw content files
- **In-Person Creative Planning row** (if applicable):
  - ✅ Monthly in-person creative planning sessions
  - ✅ Persona and script pitches for [client contacts] to feedback on
- **Strategic Direction row**:
  - ✅ Bi-weekly syncs and updates
  - ✅ Slack + Notion communication
- **Total row**: `**Total = £[X]/month**`

Price column is left EMPTY for all rows except Total in the creative-only section.

### Section 2: Video Ad Creative + Meta Ads Management

**Only include this section if Meta management is being offered.**

**Header:** `# Video Ad Creative + Meta Ads Management`
**Subheader:** `3-month agreement.`
**Spend cap note:** `Meta Ads Management: £[X]/month up to £[Y]/month ad spend. £[Z]/month for ad spend above £[Y]/month.`

Each tier heading shows: `### £[per-ad price] per ad + £[Meta price] Meta Management`

Same table structure as Section 1, but with these differences:
- **Video Concepts row**: Price column shows the creative price (e.g., `£7,000`)
- **Strategic Direction row** gets extra bullets:
  - ✅ Offer architecture guidance
  - ✅ End-to-end support across ads and creative
- **Meta Ads Management row** (NEW — added between Strategic Direction and Total):
  - ✅ Creative testing framework
  - ✅ Weekly performance reporting
  - ✅ Strategic scaling plan
  - ✅ Managed by senior media buyer
  - ✅ Daily optimisation and scaling
  - Price column: `£[Meta price]`
- **Total row**: Creative + Meta combined (e.g., `**Total = £8,500/month**`)

**CRITICAL**: The creative price and Meta price must be shown as separate line items in the Price column. Do NOT use "Bundled Price". The total must equal creative + Meta added together. Be transparent.

### Section 3: Google Ads (if applicable)

**For a one-off audit and restructure:**

**Header:** `# Google Ads - One-Off Audit and Restructure`
**Subheader:** `Priced separately from creative and Meta. One-time project fee.`

Single table (NOT 3-column), green_bg rows:
- **Full Account Audit row**: Campaign structure review, keyword performance analysis, negative keyword gap analysis, search term report review, landing page alignment assessment, competitor ad landscape review, written audit report
- **Account Restructure and Build row**: New campaign structure, keyword research and grouping, ad copy written and launched, negative keyword lists, bid strategy configured, landing page recommendations, conversion tracking verified
- **Handover row**: Full walkthrough with client, documentation of campaign logic, 2 weeks post-launch monitoring
- **Total row**: `**Total = £[X]**`

**For ongoing Google management** (if offered instead): Structure similarly to Meta management with monthly pricing.

### Pricing Calculation Reference

Standard NSY pricing logic:
- **Per-ad price decreases with volume** — this is the incentive to go higher tier
- **Meta management is a flat monthly fee** — does not change per tier
- **Meta spend cap**: Set a threshold (e.g., £50k/month) with a defined price increase above it
- **Google one-off**: Typically £1,000-£2,000 depending on account complexity
- **Agreement length**: Default 3 months

### Next Steps Section

Always end with a clean Next Steps section:

```
## Next Steps
**1. Pick your tier** - Choose from the creative packages above, and let us know if you want to add Meta management and/or the Google audit
**2. We send the agreement** - Once confirmed, we'll send a simple [X]-month services agreement for signature
**3. Kick-off call** - We align on KPIs, LTV targets, creative direction, and schedule the first in-person creative planning session
**4. We get to work** - Research, persona mapping, scripting, creator sourcing, and first batch production begins immediately
Any questions on pricing, scope, or anything in this document - just shout. Looking forward to getting started.
```

---

## Phase 4: Notion Formatting Reference

### Table Syntax for Pricing
```
<table header-row="true">
<colgroup>
<col width="123.4375">
<col width="436.9715881347656">
<col width="123.9801025390625">
</colgroup>
<tr color="blue_bg">
<td>Deliverable</td>
<td>What's Included</td>
<td>Price</td>
</tr>
<tr color="blue_bg">
<td>**[Deliverable Name]**</td>
<td>✅ Item 1<br>✅ Item 2<br>✅ Item 3</td>
<td>[Price or empty]</td>
</tr>
</table>
```

### Color Coding
- Platinum tier: `blue_bg`
- Gold tier: `yellow_bg`
- Silver tier: `gray_bg`
- Google section: `green_bg`
- "Who We Are" callout: `blue_bg`
- "What's Inside" callout: `gray_bg`
- Concept scripts — Messaging/Frame: `purple_bg`, How video looks: `blue_bg`, Core Message: `green_bg`

### Column Layout
Use Notion `<columns>` for side-by-side content. Each pricing tier is one column in a 3-column layout.

---

## Key Principles

1. **Data before narrative**: Every claim must be validated against actual account data. Never include ungrounded statistics.
2. **Funnel-level framing**: Frame creative observations as funnel insights, not criticisms of the client's current agency.
3. **Concise over comprehensive**: Sections should be tight enough for the strategist to riff on in person, not exhaustive.
4. **Proof stack activation**: Always identify and surface the client's underused credibility assets.
5. **Pricing transparency**: Show per-ad prices, separate line items for each service, and clear totals. No "bundled price" hiding.
6. **The strategist reviews everything**: Claude writes, the strategist validates. Never publish without review.

---

## Workflow Summary

1. **Ask discovery questions** (Phase 1)
2. **Create Notion page** in Audits and Proposals database
3. **Build sections top-to-bottom** (Phase 2) — strategist reviews each section
4. **Build pricing tables** (Phase 3) — most critical section, get the maths right
5. **Add Next Steps** section
6. **Strategist manually adds** images, videos, logos, embedded content
7. **Final review** before sending to client
