# Research Phases - Step-by-Step Process

This document contains the exact process for each research phase, including the prompt templates Claude should follow, what the strategist provides, and minimum depth requirements. Read `frameworks.md` first for the theoretical backbone.

---

## Phase 1: Gather Inputs

### What Claude Does
1. Ask the strategist: "Which client is this for?"
2. Ask: "Is this a new client (full research) or an existing client needing a refresh?"
3. Check Notion for the client's Team Projects entry and onboarding form data
4. If onboarding data exists: pull all fields from the Product 1 database
5. If onboarding data does not exist: ask the strategist for the basics:
   - Brand name
   - Product name(s) and what they do
   - Website URL
   - Target audience (who buys this?)
   - Key competitors (who are they up against?)
   - Country running ads in (US, UK, or both)
   - Product ingredients list (for health/wellness/supplement brands)
6. Crawl the brand's website: homepage, product pages, about page, any advertorial or landing pages. Extract: product claims, pricing, offer structure, brand voice, guarantees, testimonials shown.
7. Ask: "Before I start the deep research, do you have any of the following? I can work without them, but they make the research much deeper:"
   - Product review CSV or spreadsheet (from Amazon, Trustpilot, or internal)
   - Ad comment export (CSV from Meta Ads Manager)
   - Post-purchase survey data (CSV or link)
   - Ad account performance export (last 90 days, broken down by ad, with spend/impressions/CPM/CTR/CPC/purchases/ROAS)
   - Any previous research documents or Claude project files
   - Call transcripts (onboarding calls, strategy calls)
8. Start with whatever is available. Do not wait for everything.

### What the Strategist Provides
- Brand basics (if not in Notion)
- Any available data files (reviews, ad comments, surveys, ad account exports)
- Verbal context about the brand and what they know so far

---

## Phase 2: Product-Market Awareness Research

### Purpose
Determine where the majority of the addressable market sits on the Schwartz awareness spectrum. This single finding shapes the entire creative strategy: ad length, funnel complexity, what to lead with, how much education is needed.

### What Claude Does

Run the following research process. Do NOT do a single search and move on. Run at least 5 different searches to gather enough signal:

1. Search for the product category + "market size" + "growth"
2. Search for the product category on social media: Reddit discussions, TikTok trends, Instagram hashtags
3. Search for the product category + "reviews" + "do they work"
4. Search for influencer content about this product category
5. Search for Google Trends data or search volume signals for the category

### Prompt Template (Adapted from RMBC)

Use this framework to structure your analysis:

---

**Evaluate the level of Market Awareness for a product in the [NICHE] space. The specific product is [PRODUCT].**

**Focus on the [GEOGRAPHY] market. Target demographic: [DEMOGRAPHIC DETAILS].**

Apply the Eugene Schwartz awareness stages:

1. **Unaware:** Prospects are not even aware of a problem or need that this product can solve.
2. **Problem Aware:** Prospects recognize they have a problem or need but are unaware of potential solutions.
3. **Solution Aware:** Prospects know that solutions exist for their problem, but they are not yet aware of specific products in this category.
4. **Product Aware:** Prospects know that this CATEGORY of product exists (e.g., they know peptide eye creams exist) and are evaluating options. NOTE: This does NOT mean they know about this specific brand - even $20M+ brands are unknown to most of their TAM.
5. **Most Aware:** Prospects are highly aware of specific brands in this category, have researched options, and are close to a purchase decision.

Using social media chatter, articles, blog posts, influencer content, search trends, and any available sales data on the product category:

1. Estimate the TAM (total addressable market) for this product category.
2. Provide a rough percentage breakdown of what portion of the TAM falls into each awareness stage.
3. Give a FINAL assessment of which stage the MAJORITY of the addressable market falls into.
4. Explain what this means for creative strategy: how long should ads be? What should they lead with? How much education is needed?

---

### Minimum Depth Requirements
- All 5 stages described with specific examples relevant to this product/market
- Percentage estimates for each stage with reasoning
- Final assessment with creative implications
- Evidence cited: at least 3 specific signals (search trends, social media volume, forum activity, etc.)

---

## Phase 3: Competitor Research

### Purpose
Understand who else is talking to this market, what they're saying, what's working, and where the gaps are. The goal is to find specific language, hooks, and angles - not just a list of brand names.

### What Claude Does

For each competitor identified, run MULTIPLE searches:
1. "[Competitor name] reviews" - find customer opinions
2. "[Competitor name] complaints" or "[Competitor name] reddit" - find frustrations
3. "[Competitor name] ads" or search Meta Ad Library descriptions - find their messaging
4. "[Competitor name] vs [other brand]" - find comparison discussions
5. "[Competitor name] landing page" or visit their website - analyze their claims and positioning

### Prompt Template (Adapted from RMBC)

---

**Research competitors for a product in the [NICHE] space. The specific product is [PRODUCT] and we are focused on competitors in [GEOGRAPHY].**

**We're looking for D2C brands who primarily sell online through ecommerce or direct response sales funnels.**

For each competitor found, provide:

1. **Target demographic** - who do they speak to in their marketing?
2. **Primary acquisition funnels** - Meta ads, Google, influencer, organic, affiliate? What's dominant?
3. **Core messaging** - what is their main promise? What headline do they lead with?
4. **Ad examples** - what advertising copy, headlines, and descriptions are they using?
5. **Recurring hooks/angles/big ideas** - what themes appear consistently across their ads and landing pages? List at least 3 specific hooks per competitor.
6. **Pricing structure** - hero product price, bundles, subscriptions, discounts, guarantee terms.
7. **Customer love** - what do reviewers praise? Include at least 3 actual customer quotes.
8. **Customer hate** - what do reviewers complain about? Include at least 3 actual customer quotes.
9. **Estimated revenue** - if available from public data or industry reports.
10. **Specific repeated language** - exact phrases, claims, and verbiage they use consistently across multiple assets. I'm looking for specific phrases, sentences, and fragments that we see these competitors repeatedly use. If I were selling this product, what language would I want to borrow or respond to?

After all individual competitor profiles, provide:
- **Common industry language** - phrases every competitor uses (table stakes)
- **Differentiable language** - phrases only 1-2 competitors use (potentially ownable)
- **Messaging gaps** - what is NO competitor saying that the market wants to hear?
- **Opportunities** - angles, claims, or positions this brand could own

---

### Minimum Depth Requirements
- At least 5 direct competitors profiled
- All 10 data points filled for each competitor
- At least 3 real customer quotes per competitor (from reviews, forums, social media)
- At least 3 recurring hooks/angles per competitor
- Cross-competitor analysis completed with gaps and opportunities identified

---

## Phase 4: Psychographic Deep Research

### Purpose
Get inside the customer's head. Understand their language, beliefs, fears, hopes, objections, and worldview. This is where the best ad copy comes from - not from product features, but from customer psychology.

### What Claude Does

Run multiple targeted searches to answer every question in the framework:
1. Search Reddit for relevant subreddits discussing this problem/product category
2. Search forums specific to the niche (e.g., skincare forums, supplement forums, fitness forums)
3. Search Quora for questions about this problem
4. Search social media comments and discussions
5. Search YouTube video comments on relevant topics
6. Search Mumsnet (for UK-focused brands)
7. Search Amazon Q&A sections for related products

For every search, PRESERVE EXACT QUOTES. Do not paraphrase. The customer's raw language is the most valuable output of this entire research process.

### Prompt Template (Adapted from RMBC)

---

**I am building creative strategy for ads targeted towards [DEMOGRAPHIC/MARKET DESCRIPTION]. I need deep psychographic research. What are their struggles and pain points? What are their beliefs?**

**I want to hear what they're saying in their own words. Look at comments on social media, forums, Reddit, review sites, Quora, YouTube comments, etc. Provide actual quotes wherever possible - we want to hear answers in their own words, not AI-paraphrased versions.**

Answer ALL of the following questions with evidence:

**Insights Into the Demographic:**

1. Who is your customer? (Go beyond demographics into psychographics - what kind of person are they?)
2. What attitudes do they have? (Religious, political, social, economic - how do these affect what messaging resonates?)
3. What are their hopes and dreams? (Specifically: what does their ideal future look like where this problem is solved? How would they look and feel? What else would be true about their life?)
4. What are their victories and failures? (What have they tried? What small wins have they had? What crushing failures?)
5. What outside forces do THEY believe have prevented their best life? (What external villains do they blame?)
6. What are their prejudices? (Biases and snap judgments - not discrimination. What types of people, brands, or approaches do they instinctively distrust?)
7. Sum up their core beliefs about life, love, and family in 1-3 sentences.

**Other Existing Solutions:**

8. What is the market already using? (List every competing solution they've tried or considered)
9. What has their experience been like with those solutions?
10. What does the market like about existing solutions?
11. What does the market dislike about existing solutions?
12. Are there horror stories about existing solutions? (Real stories of things going wrong - these are gold for ad hooks)
13. Does the market believe existing solutions work? If not, why? (Look for the "efficacy paradox" - do they keep buying things they don't fully believe in?)

**Curiosity Angles:**

14. Has someone tried to solve the market's pain points before in a very unique way? What was the result? Is there a conspiratorial story behind why old solutions didn't work? Are there any older attempts to solve the problem (pre-1960) that are unique? What happened - were they successful but forgotten? Were they suppressed? Why did they disappear?

**Corruption Angles:**

15. Is there a belief that the market's pain point used to not exist, or used to not be so bad? Is there a belief that it's been recently exacerbated by outside forces? If so, what are those forces and what's the reason behind their presence?

Look for patterns like: "This isolated group of people doesn't struggle from [condition] that most of us do. The reason is that they are not exposed to [outside force] while we are."

**Primary Promises:**

16. What are the primary promises we can make to them that they would want to hear when it comes to solving their pain points? (These should be specific, vivid outcomes described in the customer's language - NOT product features or ingredient claims.)

---

### Minimum Depth Requirements
- All 16 questions answered with evidence
- At least 20 real customer quotes from forums, social media, reviews (preserved exactly as written)
- At least 3 curiosity angles identified with supporting stories/examples
- At least 2 corruption angles identified with supporting evidence
- At least 5 primary promises articulated in customer language
- At least 3 horror stories about existing solutions
- Language to use and language to avoid sections completed

---

## Phase 5: Descriptive Language Follow-Up

### Purpose
After the psychographic deep dive, do a second pass focused exclusively on capturing vivid, emotional language from the market. This produces the adjectives, descriptors, and phrases that make ad copy feel authentic rather than AI-generated.

### What Claude Does
Run targeted searches specifically for emotional language:
1. Search Reddit/forums for people describing the problem in vivid terms
2. Search review sites for emotional language about the pain points
3. Search social media for people describing the desired outcome
4. Look for before/after language patterns

### Prompt Template

---

**Continue researching and leverage social signals like social media, forums, reviews, etc. to provide the following:**

1. **As many quotes as possible from [TARGET DEMOGRAPHIC] describing their specific pain points around [PROBLEM AREA].** I want to hear how they think about the specific pain points in their own words. What adjectives and descriptors do they use? What metaphors? How do they describe the emotional impact?

2. **As many quotes as possible from [TARGET DEMOGRAPHIC] describing the opposite: the desired outcome - [POSITIVE STATE].** What adjectives and descriptors do they use when talking about the ideal result? How do they describe what "good" looks like?

---

### Minimum Depth Requirements
- At least 15 quotes describing pain points with emotional language
- At least 15 quotes describing desired outcomes with emotional language
- Adjectives and descriptors catalogued separately (e.g., "tired", "dull", "lifeless" for skin problems; "glowing", "radiant", "youthful" for desired outcomes)

---

## Phase 6: Customer Evidence Mining

### Purpose
Mine reviews and customer feedback for themes, quotes, and language patterns. This phase combines Claude's web search capabilities with any data the strategist uploads.

### What Claude Does (Automated)
1. Search Trustpilot for the brand name (if they have reviews there)
2. Search Amazon for the brand's products or similar products in the category
3. Search Reddit for mentions of the brand or product category
4. Search YouTube comments on review videos about the brand or similar products
5. Search Google for "[brand name] reviews" and "[brand name] testimonials"

### What the Strategist Provides (Optional but High-Value)
- Review CSV exports from any platform
- Internal customer feedback data
- Support ticket themes or common questions

### How to Process Reviews
Organize ALL reviews (both web-found and uploaded) into themes:

1. Read through all available reviews
2. Identify recurring themes (e.g., "results speed", "texture/feel", "value for money", "customer service", "packaging")
3. For each theme, collect at least 5 direct quotes that represent that theme
4. Note the language patterns: what words and phrases do customers use repeatedly?
5. Identify the strongest testimonials that could be used in ad creative
6. Flag any negative themes that represent common objections

### Minimum Depth Requirements
- At least 5 themes identified
- At least 5 real quotes per theme (more is better)
- Recurring language patterns listed
- Strongest testimonials highlighted
- Negative themes and objections catalogued

---

## Phase 7: Ad Comment and Survey Mining

### Purpose
Mine ad comments and post-purchase survey responses for objections, questions, and social proof. These are ONLY available when the strategist provides them.

### What Claude Does
When the strategist uploads ad comment exports or survey data:

**For Ad Comments:**
1. Identify the most common questions people ask in comments (these are objections to address in future ads)
2. Identify positive comments that serve as social proof
3. Identify negative comments and complaints (these are objections to preempt)
4. Note the language patterns in comments
5. Flag any comments that reveal customer psychology not captured elsewhere

**For Post-Purchase Surveys:**
1. What convinced them to buy? (The tipping point)
2. What almost stopped them from buying? (The biggest objection)
3. What benefit do they value most after using the product?
4. What would they tell a friend about the product?
5. How do they describe the product in their own words?

### What the Strategist Must Provide
- Ad comment export CSV from Meta Ads Manager (go to Ads tab, select all ads from last 90 days, export)
- Post-purchase survey data (CSV or link to survey results)

If the strategist doesn't have these, note it as a gap and move on. Do not block.

---

## Phase 8: Ingredient/Science Research (Health/Wellness Brands Only)

### Purpose
Build a library of evidence-backed claims for each ingredient in the product. These claims feed into scripts, hooks, and ad copy. Only cite NCBI, PubMed, or peer-reviewed journals. No blogs, no marketing sites.

### What Claude Does

Run this process for EACH ingredient:
1. Search NCBI/PubMed for the ingredient name + relevant conditions
2. Look for RCTs (Randomized Controlled Trials) with human subjects first
3. If no human RCTs exist, include in-vitro or animal studies but note the limitation
4. Focus claims on two areas: (a) how the ingredient supports the product's mechanism/approach, and (b) how the ingredient directly helps with the target market's pain points

**Important: Run the research TWICE.**
- First pass: Research each ingredient broadly without focusing on any specific mechanism
- Second pass: Research each ingredient in the context of the product's specific mechanism/approach
- Combine both passes into the final output. The first pass often surfaces key stats that get missed when the research is too narrowly focused.

### Prompt Template (Adapted from RMBC)

---

**These are the ingredients for [PRODUCT TYPE] I'll be doing creative strategy for:**

[LIST ALL INGREDIENTS]

**I'm attaching the market research document for reference on the target market's pain points.**

**For each ingredient, provide a list of claims that can be tied back to specific studies or research. This research must come from NCBI, PubMed, or other scientific journals - not from blogs or marketing websites. Give preference to RCTs with humans, but if those aren't available, include other studies too.**

**Claims should focus on:**
1. How the ingredient supports the product's approach/mechanism (when applicable)
2. Additional studies showing how the ingredient helps alleviate pain points of the target market (regardless of connection to the mechanism)

**Keep claims digestible with references. I don't need a biology lesson. I need accurate claims showing the best efficacy and results possible for each ingredient, so I can use them in marketing assets.**

---

### Minimum Depth Requirements
- Every ingredient covered
- At least 2 studies per ingredient from NCBI/peer-reviewed sources
- Study type noted (RCT, clinical trial, in-vitro, animal study)
- Claims written in digestible, ad-ready language (not academic jargon)
- Key statistics highlighted (e.g., "32% reduction in wrinkle depth after 8 weeks")

---

## Phase 9: Unified Research Document Synthesis

### Purpose
This is the MOST IMPORTANT step. Combine all research from previous phases into one strategic brief that becomes the single most valuable document in the Claude project. This document powers all downstream copy generation.

### What Claude Does

Review all research gathered in Phases 2-8 and synthesize into ONE document containing ONLY actionable copy inputs.

**Explicitly EXCLUDE from this document:**
- TAM size numbers
- Marketing strategies or recommendations
- General market background or industry overview
- Anything the copywriter doesn't need to write better ads

**Include ONLY:**

### Section 1: Target Market Demographic Overview
Focus on people who fall into the awareness segments most relevant for this brand's Meta ads (typically Problem Aware and Solution Aware, but adjust based on what Phase 2 revealed).

### Section 2: Target Market Psychographic Overview

**What are their problems and pain points?**
Dimensionalized, specific, emotional pain points. Not generic. Written the way the customers describe them, with real quotes embedded.

**What are their hopes and dreams?**
Specifically: what does their ideal future state look like where their problem has been solved? What would that look like? How would they look and feel? When they dream and imagine this future, what else is true about their life?

**How do they view themselves? What language should we use when speaking to them, and what language should we avoid?**
Identity-level insights. How they see themselves. What validates them. What would feel patronizing or tone-deaf.

**What are the Primary Promises we can make to them?**
Specific, vivid outcomes they want to hear. Written in their language, not in product-feature language.

**What will their biggest objections be, and how can we address those?**
Every objection paired with a rebuttal strategy.

### Section 3: Existing Solutions
What has the market tried already? Why are those existing solutions not adequate enough? What's the gap your product fills?

### Section 4: Curiosity and Corruption Angles
The strongest curiosity angles and corruption angles discovered during research, with enough detail that a copywriter could build a hook or lead around each one.

### Prompt Template

---

**I've completed deep research on [BRAND/PRODUCT] across market awareness, competitors, psychographics, customer reviews, and [ingredient research if applicable].**

**Create one unified research brief that contains all of the key elements needed for creative strategy and copywriting. This document will be shared with AI tools and human strategists as background context for generating ad scripts, hooks, and marketing assets - most of which will be direct response oriented.**

**Do NOT include: TAM size, marketing strategies, general market background, or industry overview.**

**DO include:**

1. **Target Market Demographic Overview** - focused on people in the [Problem Aware / Solution Aware] segments primarily.

2. **Target Market Psychographic Overview:**
   - Their problems and pain points (dimensionalized, with real quotes)
   - Their hopes and dreams (vivid future state where the problem is solved)
   - How they view themselves, language to use, language to avoid
   - Primary promises we can make (specific outcomes they want to hear)
   - Their biggest objections and how to address each one

3. **Existing Solutions** - what has the market tried, and why are those solutions inadequate?

4. **Curiosity and Corruption Angles** - the strongest angles discovered, with enough detail to build hooks and leads from.

---

### Quality Check
Before finalizing, ask: "If a world-class direct response copywriter read this document and nothing else, would they have everything they need to write a winning ad for this product?" If no, it's not deep enough.

---

## Phase 10: Output Document Generation

### Purpose
Produce all final documents per the templates in `output-templates.md`. Each document should be complete, deep, and ready for upload to a Claude project.

### What Claude Does
1. Generate each document following the exact structure in `output-templates.md`
2. Cross-reference against the minimum depth standards
3. Ensure every document contains real evidence: actual customer quotes, specific competitor claims, concrete data points, named studies
4. Present each document to the strategist for review
5. Make revisions based on strategist feedback

### Document Production Order
1. Brand Overview and Product Deep Dive
2. Market Awareness and Sophistication
3. Competitive Landscape
4. Target Audience and Customer Psychographics
5. Customer Voice (Reviews)
6. Customer Voice (Ad Comments) - if data provided
7. Customer Voice (Post-Purchase Surveys) - if data provided
8. Ad Account Insights and Proven Angles - if data provided
9. Science, Mechanism and Objections - if health/wellness brand
10. Brand DNA for Image Gen
11. Unified Research Document (the synthesis)
12. Project Instructions (the Claude project configuration)

---

## Phase 11: Claude Project Setup Walkthrough

### Purpose
The research is only valuable if it ends up in a working Claude project. This phase walks the strategist through building the best possible project by combining the research documents with raw data and skill files.

### What Claude Does

**Step 1: Confirm the project exists**
Ask: "Have you created a Claude project for [Client Name] on claude.ai yet? If not, go to claude.ai, click Projects in the sidebar, and create a new project called '[Client Name]'."

Wait for confirmation.

**Step 2: Upload the research documents**
Tell the strategist: "Download the research files and upload them to the project's knowledge base in this order:"

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
11. Science, Mechanism and Objections - if produced
12. Brand DNA for Image Gen - if produced

Wait for confirmation.

**Step 3: Upload the raw data files**
This is critical. The research documents are the analysis layer, but the raw data makes the project even stronger.

Tell the strategist: "Now add any raw data files you have. These give the project direct access to every individual quote and data point, not just my summaries:"

- Review CSVs (the full dataset, not just the summary)
- Ad comment export CSVs
- Post-purchase survey data
- Call transcripts (onboarding calls, strategy calls, monthly reviews)
- Winning scripts from previous batches

**If the strategist uploaded any of these during the research conversation, remind them specifically:** "You shared a [reviews CSV / ad comment export / etc.] during our research. Make sure to download that and add it to the project too. The raw data gives the project access to every individual quote."

Wait for confirmation.

**Step 4: Upload the skill files**
Tell the strategist: "Now add the skill files. These are the tools that let the project produce briefs and scripts:"
- Creative Strategy skill file
- Brief Builder skill file
- Static Ad Generator skill file

Explain: "Skills uploaded at the platform level are available in general conversations, but a Claude Project is its own contained environment. It only sees files uploaded directly into that project's knowledge base."

Wait for confirmation.

**Step 5: Set custom instructions**
Generate client-specific custom instructions based on what the research revealed. Example:

"You are the creative strategist for [Client Name]. Read all uploaded research documents before writing any scripts. Follow the rules in the Project Instructions document. Every script must target one specific avatar, lead with the problem not the offer, and aim for 40%+ hook rate. [Add any client-specific compliance rules, tone requirements, or creative constraints discovered during research.]"

Wait for confirmation.

**Step 6: Test the project**
Tell the strategist: "Let's test it. Open a conversation inside the project and try this prompt: 'Write me 3 hook variations for a 30-second creator-to-camera ad targeting [primary avatar], using the [proven winning angle from research].' If the output references specific customer language from the reviews, mentions the correct offer, and speaks to the right avatar, the project is working."

**Step 7: Final checklist**
Verify everything is in place before signing off:

- [ ] Claude project created on claude.ai
- [ ] Project Instructions uploaded FIRST
- [ ] Unified Research Document uploaded
- [ ] All other research documents uploaded
- [ ] Raw data files uploaded (review CSVs, ad comments, surveys, transcripts)
- [ ] Winning scripts from previous batches uploaded (if available)
- [ ] Creative Strategy skill file uploaded
- [ ] Brief Builder skill file uploaded
- [ ] Static Ad Generator skill file uploaded
- [ ] Brand DNA for Image Gen uploaded (if produced)
- [ ] Custom instructions set in project settings
- [ ] Test prompt run and output verified
- [ ] All research docs also saved in Notion Context Library

Do not sign off until the strategist confirms the checklist is complete. The project is context engineering - every file makes it smarter. The more raw material it has, the better every script it writes.
