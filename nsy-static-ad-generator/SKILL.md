---
name: nsy-static-ad-generator
description: Generate AI-powered static ad image prompts for NSY Digital clients
  using Nano Banana 2 / Higgsfield. Use when the strategist says "generate statics",
  "static ads", "create static prompts", "image ad prompts", "Higgsfield prompts",
  "Nano Banana prompts", "generate image ads", "static ad batch", "run statics for
  [client]", or any variation of wanting to create AI-generated static ad creatives
  for a client. Also triggers when the strategist mentions needing image ads, static
  creative, or wants to supplement video concepts with static formats. This skill
  handles brand visual identity research, template selection, copy collaboration with
  the strategist, and outputs ready-to-paste prompts for Nano Banana 2 / Higgsfield
  image generation. It produces a Brand DNA document and client-specific prompts
  saved to Notion.
---

# NSY Static Ad Generator

## Purpose

This skill generates ready-to-paste image generation prompts for Nano Banana 2 / Higgsfield that produce high-quality static ad creatives for NSY Digital clients. It handles everything the strategist shouldn't have to think about (brand visual research, template formatting, prompt structure) and leaves them with the parts that require human judgment (copy direction, template selection, strategic angle).

The output is two things:
1. A Brand DNA document (Organised-quality standard) that captures the brand's visual identity for image generation
2. A complete set of client-specific prompts for every template in the NSY Static Ad Template Library, ready to paste into Higgsfield with product images attached

## Before You Start

Read the reference files before beginning:

- `references/brand-dna-template.md` - The exact structure and format for the Brand DNA document (matches the Organised standard)
- `references/template-prompts.md` - All template prompts from the NSY Static Ad Template Library with their bracket variables

## How It Works

### Mode Detection

When the strategist triggers this skill, determine the mode:

**Full Run (New Client or First Time)**
- Produces the Brand DNA document from scratch
- Generates all client-specific prompts
- Used when no Brand DNA exists for this client yet

**Prompt Generation Only (Existing Brand DNA)**
- Brand DNA already exists in the client's Claude project or Notion
- Skip straight to generating client-specific prompts
- Used for subsequent batches, new products, or refreshing copy

Ask: "Does a Brand DNA document already exist for this client, or do I need to build one?"

### Phase 1: Gather Context

Before doing any visual research, pull everything available about the client. The more context you have, the better the copy in the prompts will be.

**From the Client Claude Project (knowledge files already loaded):**
- Research documents (customer avatars, review mining, competitor analysis, awareness stages)
- Previous scripts and briefs (for tone, angles that work, language patterns)
- Any existing Brand DNA or visual identity notes

**From Notion (pull via MCP):**
- Onboarding Response data (product details, USPs, target audience, pain points, competitors, review links, best-performing ad links, key offers, landing pages, compliance restrictions)
- Context Library documents (any additional research, notes, or context the team has added)
- Meeting notes (onboarding calls, strategy calls for any relevant context)

**How to find onboarding data in Notion:**
1. Search Team Projects for the client brand name
2. Navigate to the brand's Team Projects page
3. Look for "Onboarding Response" sub-page
4. Fetch the Product 1 database inside it to get all form fields

**What to extract and hold for later use:**
- Product name, URL, price, key offers, landing pages
- Main USPs (verbatim from onboarding)
- Target audience demographics and psychographics
- Specific pain points solved
- Desired outcomes / transformations
- Competitors (names and positioning notes)
- Review links (Trustpilot, Amazon, on-site)
- Best-performing ad links
- Compliance restrictions
- Existing brand assets (Google Drive link)

### Phase 2: Brand DNA Document (Full Run Only)

This phase produces the Brand DNA document that ensures every static ad matches the brand's visual identity. The output must match the Organised standard in `references/brand-dna-template.md`.

**Step 2a: Web Research**

Run the Master Brand Research logic. Use web search and web fetch to:

1. Visit the brand's website. Analyze: hero copy, tone, photography style, typography, color application, layout density, packaging details.
2. Search for design credits: "[Brand] design agency", "[Brand] rebrand"
3. Search for brand assets: "[Brand] brand guidelines", "[Brand] press kit", "[Brand] style guide"
4. Search for typography: "[Brand] font", "[Brand] typeface"
5. Search for colors: "[Brand] brand colors", "[Brand] hex codes", "[Brand] color palette"
6. Search for packaging: "[Brand] packaging design", "[Brand] unboxing"
7. Search for ad creative style: Check Meta Ad Library for current ad formats
8. Search for press coverage: "[Brand] brand story", "[Brand] founding story"
9. Identify 2-3 direct competitors and note visual differentiation

**Step 2b: Combine with Onboarding Data**

Merge the web research findings with the onboarding data pulled in Phase 1. The onboarding data gives you competitive positioning, USPs, and audience context that the website alone won't reveal.

**Step 2c: Build the Brand DNA Document**

Structure the output exactly as specified in `references/brand-dna-template.md`. Use tables for structured data. Include precise hex codes (estimate from website if not publicly available). Write the Image Generation Prompt Modifier paragraph (50-75 words) that gets prepended to every prompt.

Also include these NSY-specific sections that the standard Master Brand Research prompt doesn't produce:
- Key Stats and Proof Points (from reviews, website, onboarding data)
- Key Customer Language (verbatim phrases from reviews - the gold for ad copy)
- Key Pain Points (specific, emotional, from onboarding + reviews)
- Desired Outcomes (the transformation language)
- Compliance Restrictions (what claims to avoid)
- Hero Offer (the primary acquisition offer for ads)

**Step 2d: Present to Strategist for Review**

Show the Brand DNA document to the strategist before proceeding. Ask:
- "Does this visual identity feel right? Anything off about the colors, typography, or photography direction?"
- "Any stats, proof points, or review language I'm missing?"
- "Is the Image Gen Modifier paragraph capturing the brand feel?"

Refine based on feedback before moving to Phase 3.

### Phase 3: Copy Workshop (Strategist-Led)

This is the most important phase. The strategist drives the creative direction here. Copy gets locked BEFORE prompts are assembled. The skill does not generate prompts with placeholder copy and ask the strategist to fix them afterwards. Instead, the copy is a collaborative creative exercise that happens first.

**Step 3a: Present the Copy Brief**

Using everything gathered from research, onboarding, and the Brand DNA, present the strategist with a structured copy brief organized by copy type:

**Headlines (for templates 1, 21, 30, 35, 37):**
Draft 5-8 headline options grounded in the research. Pull from pain points, desired outcomes, and the strongest USPs. Present them and ask: "Which of these hit? Want to rework any? Add your own?"

**Testimonial / Review Quotes (for templates 3, 11, 13, 15, 16, 17, 19, 24, 38):**
Pull the strongest real customer language from review mining docs, onboarding review links, and any review data in the project. Present 5-8 of the most emotive, specific, authentic-sounding quotes. Ask: "Are these real quotes from the client's reviews? Do you have stronger ones? Should I rework any to feel more natural?"

**Comparison / Us vs Them Copy (for templates 7, 25, 31):**
Draft the specific strengths vs weaknesses using competitor research from onboarding. Present the comparison points. Ask: "Are these competitor claims accurate? Anything we can't say? What would you change?"

**Stat Callouts (for templates 6, 13, 18, 26, 27, 34, 35):**
List all verifiable stats from research: customer counts, ratings, percentages, ingredient claims, clinical references. Ask: "Which stats are current and approved? Any we need to update or remove?"

**Hooks / Scroll-Stoppers (for templates 9, 16, 20, 29, 39):**
Draft 5-8 provocative hooks and curiosity gaps based on pain points and customer language. These need the strategist's creative judgment the most. Ask: "Which of these would stop the scroll for this audience? Too aggressive? Not aggressive enough?"

**Long-Form / Manifesto Copy (for templates 23, 40):**
Draft the full body copy using the brand's voice, pain points, proof points, and positioning. Present the full text. Ask: "Does this sound like the brand? What lines need to change?"

**CTAs and Offer Copy (for templates 2, 14, 27, 28, 37):**
Confirm the current hero offer, any active promotions, and the exact CTA language the brand uses. Ask: "Is [offer] still the active acquisition offer? Any seasonal promos running?"

**Step 3b: Iterate Until Approved**

The strategist rewrites, swaps, adds their own lines, removes what doesn't work. This is a back-and-forth conversation, not a one-shot review. The skill helps by suggesting alternatives, pulling more review language, or reworking lines based on feedback.

Do not move to Step 3c until the strategist explicitly approves the copy brief.

**Step 3c: Template Selection**

With copy locked, recommend which templates to prioritize for this batch. Consider:
- Market awareness stage (unaware audiences need curiosity gaps and educational content; product-aware need social proof and comparison)
- What's performing in the ad account (if social proof ads are winning, lean into review-based templates)
- What hasn't been tested yet
- The client's strongest assets (great reviews = testimonial templates; strong stats = stat-driven templates; clear competitor differentiation = us-vs-them)

Present recommendations with reasoning. The strategist makes the final selection.

**Step 3d: Assemble Prompts**

Only now, with approved copy and selected templates, assemble the final prompts.

Fetch the latest template prompts from the Notion Template Prompts page (ID: af8df9f700e58348a03a01bfd1424fa3). Fill bracket variables using:
- Brand DNA visual details (colors, typography, photography style, product description)
- The approved copy from Step 3b (headlines, quotes, hooks, stats, CTAs)
- Product details and compliance restrictions from onboarding

Generate prompts for ALL templates (not just the selected ones) so the strategist has the full library available. But flag which ones were recommended in Step 3c.

Present the final prompts to the strategist for a quick visual check before saving.

### Phase 4: Save Outputs

**Brand DNA Document:**
1. Save to Notion inside the client's **Context Library** section within their Team Projects page as "[Client Name] - Brand DNA for Image Gen"
2. Tell the strategist to also upload it as a knowledge file in the client's Claude project so future runs can skip Phase 2

**Client-Specific Prompts:**
1. Save to Notion inside the client's **Context Library** section within their Team Projects page as "[Client Name] - Static Ad Prompts [Product Name]"
2. The strategist copies prompts from this page directly into Higgsfield

### Phase 5: Post-Generation

After the strategist has generated images in Higgsfield:

**If they want to add a new template to the library:**
Walk them through the Template Expansion process:
1. They describe or paste the winning static
2. You reverse-engineer it into a standardized template prompt with bracket variables
3. They add it to the Ad Creative Templates database in Notion (Name, Prompt, Output columns)
4. It becomes available for all future client prompt generation runs

**If they want to generate prompts for a different product:**
Re-run Phase 3 only with the new product details. The Brand DNA stays the same (brand identity doesn't change per product), but the copy elements update for the new product's USPs, claims, and use case.

## Rules

1. Never guess brand visual details. Research the website and verify.
2. Never use generic copy. Every headline, quote, and stat must be grounded in real client data.
3. Always present the Brand DNA to the strategist for review before generating prompts.
4. Always flag copy elements that need strategist input. Don't assume your first draft is final.
5. Respect compliance restrictions from the onboarding data. If the client says "don't claim it cures insomnia," none of the prompts should claim it cures insomnia.
6. The strategist selects which templates to generate. You recommend, they decide.
7. Remove aspect ratio from the end of prompts if the strategist says they're setting it in Higgsfield's settings instead.
8. For product images, tell the strategist to grab them from the client's website. The skill doesn't handle image sourcing.
9. Run multiple web searches per topic during brand research. Don't stop at one search.
10. When in doubt about visual identity details, show the strategist what you found and ask them to confirm rather than guessing.
11. Never use em dashes in any output.
12. The Brand DNA document format must match the Organised standard with tables. Not paragraphs, not bullet lists. Tables.

## Notion Integration

**Pulling data:**
- Onboarding responses live inside each client's Team Projects page, under "Onboarding Response"
- Search Team Projects for the brand name, navigate to Onboarding Response, fetch the Product 1 database
- Also check "Context Library" and "Meeting Notes" for extra context
- Team Projects data source: `collection://1d5df9f7-00e5-812a-86f4-000b4eaef08d`

**Pushing output:**
- Both the Brand DNA doc and Static Ad Prompts get saved inside the client's **Context Library** section within their Team Projects page
- If a Context Library section doesn't exist, create one
- Each document becomes a separate page inside the Context Library
- Team Projects data source: `collection://1d5df9f7-00e5-812a-86f4-000b4eaef08d`

## Quality Checks

Before delivering the final prompts, verify:
- Brand DNA includes all sections from the Organised template (tables, not paragraphs)
- Image Gen Modifier is 50-75 words and captures the brand's visual feel
- Every prompt has real client data, not generic placeholders
- Compliance restrictions are respected in every prompt
- Stats and claims are accurate and sourced from real data
- Review language feels authentic (if you made it up, flag it)
- Competitor comparisons don't make false claims
- The hero offer matches what the client actually runs
- All prompts specify an aspect ratio
- The strategist has reviewed and approved copy before the prompts are finalized
