---
name: nsy-creative-research
description: Run deep creative research for NSY Digital clients. Use when the strategist
  says "run research", "do research", "start research", "research for [client]",
  "build the Claude project", "create research docs", "research skill", "onboarding
  research", or any variation of wanting to do creative strategy research for a client
  brand. Also use when the strategist mentions needing to understand a new client,
  build context for a brand, prepare for a first batch, set up a Claude project, or
  do a research refresh for an existing client. This skill handles onboarding data,
  market awareness analysis, competitor research, psychographic deep dives, customer
  review mining, ad comment analysis, post-purchase survey mining, ad account analysis,
  and ingredient research for health/wellness brands. It produces structured documents
  ready to be uploaded into a client Claude project.
---

# NSY Creative Research Skill

## Purpose

This skill runs a comprehensive creative research process for NSY Digital clients. The ultimate goal is to build the best possible Claude project for each client. A Claude project is context engineering - the better the context, the better every script, brief, and concept it produces.

The skill does two things:
1. **Produces rich research documents** that go into the project as knowledge files
2. **Guides the strategist on what else to add** - raw review CSVs, ad comment exports, post-purchase survey data, call transcripts, winning scripts. The research docs are the analysis layer, but the raw data makes the project even stronger because the Claude project can reference specific quotes and data points directly.

The quality of the research documents DIRECTLY determines the quality of every script the Claude project writes. Shallow research = shallow scripts. Deep, specific, evidence-rich research = scripts that convert because they speak the customer's actual language, address their real objections, and channel their existing desires toward the product.

This is a collaborative process. The skill does heavy lifting on analysis, synthesis, and web research. But there are things only the strategist can provide (review CSVs, ad comment exports, ad account data, post-purchase surveys). The skill must clearly separate these two categories and guide the strategist through providing everything needed.

**Research methodology:** This skill follows the RMBC research methodology (Research, Mechanism, Brief, Copy) adapted for NSY's Meta ads creative process. The frameworks, prompts, and question sets in the reference files are battle-tested across multiple niches and product types.

## Before You Start

Read the following reference files before beginning:

- `references/research-phases.md` - The full step-by-step research process with all phases, what Claude does vs what the strategist provides, and interaction patterns
- `references/output-templates.md` - The exact structure, depth standard, and example content for EVERY output document. This is the most important reference file. Each document has a detailed template showing what "great" looks like.
- `references/frameworks.md` - The theoretical frameworks (Schwartz awareness stages, market sophistication, RMBC research methodology, psychographic deep dive questions, corruption/curiosity angles) that inform the research

## Two Key Principles

### 1. Know What Claude Can and Cannot Do

**Claude CAN do automatically (no strategist input needed):**
- Read the client's website, landing pages, product pages via web search
- Search Reddit, forums, Mumsnet, Quora for customer conversations
- Search Trustpilot, Amazon for public product reviews
- Research competitor brands via web search and Meta Ad Library (ad copy and descriptions only - Claude cannot watch video ads)
- Research ingredients, clinical studies, mechanisms of action via PubMed/NCBI
- Pull onboarding data from Notion (if the form has been completed)
- Analyze market awareness stages and sophistication levels
- Build psychographic profiles from all gathered data
- Synthesize everything into structured documents

**Claude CANNOT do (strategist must provide):**
- Watch or analyze video ads (Claude has no video capability)
- Access ad account performance data (strategist must export CSV from Ads Manager)
- Access private review databases or CSVs (strategist must upload)
- Access ad comment exports (strategist must export and upload)
- Access post-purchase survey data (strategist must provide CSV or link)
- Access Foreplay boards or AdNova saved collections (strategist must describe findings verbally)
- Make strategic decisions about which angles to pursue (Claude presents options, strategist decides)
- Access Google Drive brand assets or B-roll footage

When you need something from the strategist, be extremely specific about what to provide and how to provide it. For example: "I need the ad comments exported as a CSV. In Ads Manager, go to Ads tab, select all ads from the last 90 days, click Export, and upload the CSV here."

### 2. Flexible Starting Point

The skill does NOT require the onboarding form to be completed. At the start:

1. Check Notion for the client's onboarding data by searching the Team Projects database for the brand name and looking for an "Onboarding Response" page
2. If the onboarding form EXISTS and is filled out: pull all data from the Product 1 database and use it as the foundation
3. If the onboarding form DOES NOT EXIST or is empty: ask the strategist for the basics (brand name, product name, website URL, target audience, key competitors) and work from web research as the foundation

Either way, the skill produces the same quality output. The onboarding form just gives a head start.

## Research Modes

### Full Research (New Client / First Batch)
- Runs all phases end to end
- Produces the complete set of research documents (10-12 documents depending on brand type and available data)
- Used when NSY starts working with a brand for the first time

### Research Refresh (Existing Client, New Batch)
- Skips foundational research that doesn't change (market awareness, psychographics, ingredient claims)
- Focuses on: new review/comment data, updated competitor activity, ad account performance since last batch
- Updates only the documents that need refreshing
- Ask the strategist what's changed since last batch

## Phase Overview

Full research runs in this order. Each phase builds on previous ones. See `references/research-phases.md` for the full process with prompt templates.

1. **Gather Inputs** - Pull from Notion (or ask strategist), fetch website/product pages, ask strategist for uploads they have available
2. **Product-Market Awareness Research** - Where the market sits on the Schwartz awareness spectrum and what this means for creative approach (ad length, what to lead with, funnel complexity)
3. **Competitor Research** - At least 5 competitors with full profiles: messaging, positioning, pricing, claims, recurring hooks/angles, customer love/hate with real quotes, specific repeated language
4. **Psychographic Deep Research** - Full RMBC psychographic framework: 16 questions covering demographics, attitudes, hopes, dreams, failures, outside forces, prejudices, beliefs, existing solutions, horror stories, Curiosity angles, Corruption angles, and primary promises. Must surface at least 20 real customer quotes.
5. **Descriptive Language Follow-Up** - Second pass focused on vivid emotional language: how does the market describe the pain points AND the desired outcome in their own words? At least 15 quotes for each.
6. **Customer Evidence Mining** - Reviews from Trustpilot/Amazon/Reddit (Claude searches) PLUS uploaded CSVs (strategist provides). At least 30 real quotes organized by theme.
7. **Ad Comment Mining** - From uploaded CSV only (strategist provides the export)
8. **Post-Purchase Survey Mining** - From uploaded data only (strategist provides)
9. **Ingredient/Science Research** - For health/wellness/supplement brands only. Claims tied to NCBI/PubMed studies. Run research twice: once broadly, once focused on the product's mechanism.
10. **Unified Research Document Synthesis** - THE MOST IMPORTANT STEP. Combine all research into one strategic brief containing only actionable copy inputs: demographic overview, psychographic overview (dimensionalized pain points, hopes/dreams, language guidance, primary promises, objections), existing solutions, curiosity/corruption angles. Explicitly exclude TAM numbers, marketing strategies, and general background.
11. **Output Document Generation** - Produce all final documents per the templates in `references/output-templates.md`
12. **Claude Project Setup Walkthrough** - Guide the strategist through creating the project, uploading research docs AND raw data files, adding skill files, setting custom instructions, and testing

## Output Documents

The skill produces these documents. Read `references/output-templates.md` for the exact structure and depth standard for each one. Every document has minimum depth requirements that must be met before delivery.

1. **[Client Name] - Brand Overview and Product Deep Dive** - Everything about the product, brand, offer, positioning. At least 2 pages. All pricing, claims, and website analysis included.
2. **[Client Name] - Target Audience and Customer Psychographics** - Named avatars, full RMBC psychographic profile (all 16 questions), curiosity angles, corruption angles, primary promises, objections with rebuttals, language guide. At least 4-5 pages with 20+ real quotes.
3. **[Client Name] - Customer Voice (Reviews)** - At least 5 themes with 5+ real quotes each. 30+ total quotes. Recurring language patterns. Strongest testimonials highlighted.
4. **[Client Name] - Customer Voice (Ad Comments)** - Common questions, positive social proof, negative comments organized by theme. (Conditional: only if strategist provides CSV)
5. **[Client Name] - Customer Voice (Post-Purchase Surveys)** - What convinced them, what almost stopped them, most valued benefit. (Conditional: only if strategist provides data)
6. **[Client Name] - Competitive Landscape** - At least 5 competitors with full profiles (10 data points each, 3+ quotes per competitor), positioning map, messaging gaps, opportunities.
7. **[Client Name] - Market Awareness and Sophistication** - All 5 awareness stages with percentages, final assessment, creative strategy implications (ad length, what to lead with, funnel complexity).
8. **[Client Name] - Ad Account Insights and Proven Angles** - Winning angles, fatigued creative, missing opportunities, format gaps. (Conditional: only if strategist provides data)
9. **[Client Name] - Science, Mechanism and Objections** - Per-ingredient claims with NCBI study references, mechanism support, objection rebuttals with evidence. (Conditional: health/wellness brands only)
10. **[Client Name] - Brand DNA for Image Gen** - Visual identity for static ad generation with hex codes, typography, photography style, copy elements.
11. **[Client Name] - Unified Research Document** - THE MOST IMPORTANT OUTPUT. Single synthesis document containing only actionable copy inputs: demographic overview, dimensionalized pain points with quotes, hopes/dreams, language guidance, primary promises, objections, existing solutions, curiosity/corruption angles. At least 5-7 pages. This is what powers all downstream copy generation.
12. **[Client Name] - Project Instructions** - The meta-document that configures the Claude project itself with client-specific rules, compliance guardrails, and document map.

Documents 4, 5, 8, and 9 are conditional - they only get created if the strategist provides the relevant data. The skill should always ask if the strategist has these available, but never block on them.

## Interaction Flow

### Opening
When the strategist triggers the skill:

1. Ask: "Which client is this for?"
2. Ask: "Is this a new client (full research) or an existing client needing a refresh?"
3. Check Notion for the onboarding form
4. Ask: "Before I start, do you have any of the following available? I can work without them, but they make the research much deeper:"
   - Product review CSV or spreadsheet
   - Ad comment export (CSV from Ads Manager)
   - Post-purchase survey data (CSV or link)
   - Ad account performance export (last 90 days, broken down by ad, with spend/impressions/CPM/CTR/CPC/purchases/ROAS)
   - Any previous research documents or Claude project files
5. Start with whatever is available. Don't wait for everything.

### During Research
- Present findings at each phase and ask the strategist to validate
- Be specific when something looks wrong or surprising: "The reviews heavily mention sleep as the #1 benefit, but the onboarding form lists energy as the main USP. Which is more accurate for the target audience?"
- When the strategist provides verbal context about the ad account (what angles are winning, what they've seen in competitors, what formats work), capture this systematically and include it in the relevant document
- Keep the strategist informed of progress: "I've completed the brand deep dive and psychographic analysis. Next I'll do competitor research. While I'm doing that, can you export the ad comments for me?"

### Closing and Claude Project Setup

Once all documents are produced and pushed to Notion, the skill enters the Claude Project Setup phase. This is not optional - it's the final and most critical step. The research is only valuable if it actually ends up in a working Claude project. The skill must walk the strategist through this step by step, checking at each stage that they've completed it before moving on.

**Step 1: Confirm the project exists**

Ask: "Have you created a Claude project for [Client Name] on claude.ai yet? If not, go to claude.ai, click Projects in the sidebar, and create a new project called '[Client Name]'."

Wait for confirmation before proceeding.

**Step 2: Upload the research files**

Tell the strategist: "Now download the research files I've given you and upload them to the project's knowledge base. Upload them in this order - the order matters because the Project Instructions file tells the project how to behave, so it needs to go in first:"

Then list every document that was produced in the research, numbered, in the correct upload order:
1. Project Instructions (always first - this configures the project's behavior)
2. Unified Research Document (the core synthesis - most important context file)
3. Brand Overview and Product Deep Dive
4. Target Audience and Customer Psychographics
5. Customer Voice (Reviews)
6. Customer Voice (Ad Comments) - if produced
7. Customer Voice (Post-Purchase Surveys) - if produced
8. Competitive Landscape
9. Market Awareness and Sophistication
10. Ad Account Insights and Proven Angles - if produced
11. Science, Mechanism and Objections - if produced (health/wellness brands)
12. Brand DNA for Image Gen - if produced

Ask: "Have you uploaded all of those? Let me know once they're in."

Wait for confirmation before proceeding.

**Step 3: Upload the skill files**

Ask: "Now we need the skill files. These are the tools that let the Claude project actually produce briefs and static ad prompts. Do you have the following skill files available?"
- Brief Builder skill file
- Static Ad Generator skill file
- Any other custom skills relevant to this client

If the strategist says the skill files are already uploaded to claude.ai at the platform level, explain: "Skills uploaded to the platform level are available in general conversations, but a Claude Project is its own contained environment - it only sees files uploaded directly into that project's knowledge base. You need to download the skill files and upload them into this specific project."

Wait for confirmation that skills are uploaded.

**Step 4: Upload raw data files**

Tell the strategist: "Now add any raw data files you have. These give the project direct access to every individual quote and data point, not just my summaries. The more raw material the project has, the better every script it writes:"

- Review CSVs (the full dataset from Amazon, Trustpilot, or internal systems)
- Ad comment export CSVs (from Meta Ads Manager)
- Post-purchase survey data
- Call transcripts (onboarding calls, strategy calls, monthly reviews)
- Winning scripts from previous batches
- Any other brand context documents the client has shared

**If the strategist uploaded any of these during the research conversation, remind them specifically:** "You shared a [reviews CSV / ad comment export / etc.] during our research earlier. Make sure to download that and add it to the project too."

Wait for confirmation.

**Step 5: Set the project custom instructions**

Tell the strategist: "Last thing - add custom instructions to the project. Go to the project settings and paste this into the custom instructions field:"

Then provide a custom instruction tailored to the specific client, something like:

"You are the creative strategist for [Client Name]. Read all uploaded research documents before writing any scripts. Follow the rules in the Project Instructions document. Every script must target one specific avatar, lead with the problem not the offer, and aim for 40%+ hook rate. Never use em dashes."

Adjust this based on the specific client's needs, compliance requirements, and creative rules discovered during research.

**Step 6: Test the project**

Tell the strategist: "Let's test it. Open a conversation inside the project and try this prompt: 'Write me 3 hook variations for a 30-second creator-to-camera ad targeting [the brand's primary avatar], using the [brand's proven winning angle].' If the output references specific customer language from the reviews, mentions the correct offer, and speaks to the right avatar, the project is working. If it's generic, check the files uploaded correctly."

**Step 7: Confirm completion**

Ask: "Did the test output look good? Is it referencing the research and speaking in the right voice?"

If yes: "The Claude project is live and ready for script production. Everything from the research is now powering every conversation inside this project. The documents are also in Notion in the Context Library if you or the team need to reference them outside of Claude."

If no: Troubleshoot. Common issues:
- Files didn't upload properly (re-upload)
- Project Instructions file wasn't uploaded first (re-order)
- Custom instructions are missing or too generic (update them)
- The project is confusing platform-level instructions with project-level (check for conflicts)

**Summary checklist the skill should verify before signing off:**

- [ ] Claude project created on claude.ai
- [ ] Project Instructions uploaded FIRST
- [ ] Unified Research Document uploaded (most important context file)
- [ ] All other research documents uploaded to the project knowledge base
- [ ] Raw data files uploaded (review CSVs, ad comment exports, survey data, call transcripts)
- [ ] Winning scripts from previous batches uploaded (if available)
- [ ] Creative Strategy skill file uploaded to the project
- [ ] Brief Builder skill file uploaded to the project
- [ ] Static Ad Generator skill file uploaded to the project
- [ ] Brand DNA for Image Gen uploaded (if produced)
- [ ] Custom instructions set in project settings
- [ ] Test prompt run and output verified
- [ ] All research docs also saved in Notion Context Library

Do not sign off on the research build until the strategist confirms they've completed the checklist. The project is context engineering - every file makes it smarter. The more raw material it has, the better every script it writes.

## Notion Integration

**Pulling data:**
- Team Projects data source: `collection://1d5df9f7-00e5-812a-86f4-000b4eaef08d`
- Search for the brand name, navigate to the Onboarding Response page
- Fetch the Product 1 database to get all form fields
- Also check Context Library for any existing research docs

**Pushing output:**
- Each document becomes a separate page inside the client's Context Library in Notion
- If Context Library doesn't exist, create one inside the client's Team Projects page

## Rules

### Research Depth Rules
1. **Never do one search and call it done.** For each topic, run at least 3 different searches with different search terms. For competitor research, search "[competitor name] reviews", "[competitor name] complaints", "[competitor name] reddit" separately.
2. **Search specific sources.** Don't rely on general web search alone. Explicitly search: Reddit (relevant subreddits), Trustpilot, Amazon reviews, forums, Quora, YouTube comments, Mumsnet (for UK brands).
3. **Preserve exact language.** When you find a customer quote, keep it exactly as written. Do not paraphrase or clean it up. The raw language is the value.
4. **After each phase, review and gap-fill.** Ask yourself: "What questions from the framework haven't been answered? What's still vague or generic?" Then run additional searches to fill those gaps.
5. **Meet the minimum depth standards.** Every document has minimum requirements in `references/output-templates.md`. If a document doesn't meet them, it needs another pass.
6. **Dimensionalize pain points.** Never write one-line bullet points for pain points. Each pain point should be a vivid, emotional description with real customer quotes showing how it affects daily life, relationships, and self-image.
7. **Look for surprises.** The most valuable research findings are the ones that contradict assumptions. Flag these prominently.

### Process Rules
8. Never guess brand information. Pull from Notion or ask the strategist.
9. Always validate findings with the strategist before moving to the next phase.
10. For ingredient research, only cite PubMed, NCBI, or peer-reviewed journals. No blogs. Run ingredient research twice: once broadly, once focused on mechanism.
11. Be honest about what you can and cannot access. Never pretend to analyze video ads.
12. When the strategist describes ad account findings verbally, capture the insight systematically in the Ad Account Insights document.
13. When the strategist says something contradicts what the AI research found, the strategist is probably right.
14. For health/wellness/supplement brands, always run ingredient research. For other product types, skip it.
15. Never use em dashes anywhere in the output. Use regular dashes only.
16. Be opinionated. If the research reveals something important, say it clearly. Don't hedge.
17. Don't take LLM "avoid" language at face value. If the research says "avoid instant transformation claims" but the product IS an instant eye lift, use that language. Apply critical thinking.
18. Adjust the awareness focus based on findings. Don't default to "problem aware and solution aware" - use what the market awareness research actually reveals.

### Quality Rules
19. Every document must contain real evidence: actual customer quotes, specific competitor claims, concrete data points, named studies. No generic filler.
20. The output must be deep enough that a strategist could open any document and immediately start writing scripts without needing to do additional research.
21. Customer language sections must contain ACTUAL phrases from reviews, forums, and comments - not AI-paraphrased versions.
22. Always ask the strategist if they have review CSVs, ad comment exports, and post-purchase surveys. These are the most valuable inputs. Help them get these if they don't know how.
23. The skill should feel like working with a senior research analyst who has spent a week deep-diving the brand, not like getting a generic AI summary.
24. The Unified Research Document is the single most important output. It must be 5-7 pages of dense, specific, evidence-backed content. No filler.

### Project Rules
25. Never sign off on a research build without completing the Claude Project Setup Walkthrough. The research is wasted if it doesn't end up in a working project.
26. During the project setup, remind the strategist to add raw data files (review CSVs, ad comment exports, surveys) directly to the project. The research documents are the analysis layer, but raw data gives the project access to every individual quote.
27. Track what data the strategist shared during the research conversation and specifically remind them to add those files to the project at the end.

## Quality Standard

Before delivering any document, ask yourself: "If a world-class direct response copywriter read this document, would they have everything they need to write a winning ad?" If the answer is no, the document isn't deep enough.

Read `references/output-templates.md` for the specific depth standard for each document type.

## References

- `references/research-phases.md` - Step-by-step research process
- `references/output-templates.md` - Document structures and depth standards
- `references/frameworks.md` - Theoretical frameworks and methodologies
