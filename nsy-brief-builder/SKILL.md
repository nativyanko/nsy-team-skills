---
name: nsy-brief-builder
description: Populate the Official NSY Brief Template in Notion for a creative
  concept. Use when the strategist says "add this to Notion", "push to Notion",
  "create the brief", "build the brief", "push this to the brief", "add to the
  brief template", "push to brief", or "add this to the brief". Takes the script,
  concept, target audience, visual guidance, editor notes, and all context from
  the current conversation and populates the full brief template in the correct
  Notion location inside the Master Creative Database. Always use this skill
  when the user wants to move a completed script into Notion as a formatted brief.
---

# NSY Brief Builder

## Purpose

This skill takes a completed script and all supporting context from the current Claude conversation and populates the Official NSY Brief Template in Notion. The brief is created inside a concept page in the Master Creative Database, fully formatted and ready for creators and editors.

This skill does NOT write the script. The script should already exist in the conversation from a previous back-and-forth with the strategist. This skill's job is placement and formatting: taking what already exists and putting it in the right place in the right format.

## Before You Start

Read the reference file `references/template-structure.md` to understand the exact structure of the Official NSY Brief Template, every section, every table, every database column, and the naming conventions.

Read the reference file `references/example-brief.md` to see a fully completed brief (Fat Cow Skincare - Jesy Nelson Hook) so you understand what "good" looks like for every field.

## Execution Flow

### Step 1: Confirm the Script is Ready and Determine Brief Type

Before doing anything, confirm the script exists in the conversation. You should be able to identify:

- The full script (hook, body sections, CTA)
- The concept angle
- The target audience
- The brand name
- Hook variations (at least 2-3)

If any of these are missing, ask the strategist to provide them before proceeding. Do not guess.

**CRITICAL - Ask the strategist: "Is this a creator brief or just an editor brief?"**

This determines two things: the level of detail needed AND whether to check the "Creator Needed?" property.

- **Creator brief**: A real UGC creator will film this. Set the "Creator Needed?" property to checked (__YES__) on the concept page. ALL sections must be fully populated - Creator table, shooting instructions, Other Creator Notes, shot list, Visual Guidance column in the script table. Do not cut corners. Be thorough. You would rather over-communicate than under-communicate to the creator.
- **Editor-only brief**: No creator is filming. The editor will use AI voiceover, stock footage, or existing B-roll. Set the "Creator Needed?" property to unchecked (__NO__) on the concept page. The Creator toggle sections (shooting instructions, Other Creator Notes, shot list, Google Drive link) can be left minimal or empty. The Visual Guidance column in the script table can be left empty. Focus all detail on the Editor table, Editor Notes column in the script, and Other Editor Notes.

Always ask this question. Do not assume.

**STATUS ON CREATION: When the concept page is created in the Master Creative Database, always set:**
- **Status** = "In progress"
- **Status Type** = "Strategy"

This signals to the team that the concept is actively being worked on at the strategy phase. Never leave it as "To-Do" or "Backlog" when the brief is being built.

### Step 2: Determine Batch Number and Create Concept

**Batch number logic (do NOT ask the strategist for this - calculate it yourself):**

1. Fetch the brand's Team Projects page from the Team Projects database (`collection://1d5df9f7-00e5-812a-86f4-000b4eaef08d`). Look at the "Deliverables" property to find how many total concepts are in each batch (e.g. "8 video concepts (4 hooks each) + 7 Static concepts (4 variations each)" = 15 concepts per batch).
2. Search the Master Creative Database for all existing concepts for this brand. Count them.
3. Calculate: if the brand has N concepts per batch and X concepts already exist, then concepts 1 through N are batch 1, concepts N+1 through 2N are batch 2, etc. The new concept's batch = ceiling((concept_number) / N).

Example: Resleep has 15 concepts per batch (8 video + 7 static). Concepts 1-15 are batch 1. Concept 16 is the start of batch 2. Concepts 16-30 are batch 2. Concept 31 starts batch 3.

**Where to put the concept:**

Ask the strategist:

"Where should I create this brief? Please share the Notion link to the concept page. If you need me to create a new concept in the Master Creative Database first, let me know."

**Scenario A: Existing concept page**
The strategist pastes a Notion link. Fetch the page to confirm the concept name, brand, and concept number.

**Scenario B: New concept needed**
Determine the next concept number by counting existing concepts for this brand in the Master Creative Database. Calculate the batch number using the logic above. Create the concept row using the Video Concept template (template ID: `1d5df9f7-00e5-8153-9e78-f3f7d6dfdf3b`).

**CRITICAL - Concept Page Name:** When creating the concept row in the Master Creative Database, the "Name" property MUST be the full concept name (e.g. "Reaction to Froch/Hearn podcast", "Wife testimonial", "30 Day Transformation"). It must NOT be just the brand code and number (e.g. "ZAP7"). The brand code and number are separate properties (Brand Code + Concept No.). The Name property is the human-readable concept name that describes what the ad is about. Look at existing concepts for the same brand to see the naming pattern - they all use descriptive names, never just the code + number.

Then proceed.

### Step 3: Look Up the Brand Code

Search the Team Projects database (`collection://1d5df9f7-00e5-812a-86f4-000b4eaef08d`) for the brand to get the Brand Code property. You need this to build the brief page name.

### Step 4: Build the Brief Page Name

The naming convention is: `[Brand Code][Concept No.] - [Concept Name]`

Examples:
- FAT2 - Jesy Nelson Hook
- HM7 - Magnesium Sleep Story
- WIL3 - Fussy Eater Founder

Get the Concept No. from the concept page properties in the Master Creative Database. Combine with the Brand Code from Step 3.

### Step 5: Gather All Content From the Conversation

Pull the following from the conversation history. Everything should already exist from the script-writing phase:

**CRITICAL - Required fields that must be provided by the strategist (never guess these):**

Before gathering content, check whether the strategist has provided ALL FIVE of the following items. If any are missing, ask for them as a flat numbered list. Each item is its own question so the strategist can answer one per line without needing commas or sub-grouping.

Ask ONLY for the items that are missing. If some have already been discussed in the conversation, do not re-ask. Present them like this:

"I need a few things before I push to Notion:

1. Reference ad link
2. Caption direction
3. Footage to use
4. Music
5. Where in Notion (existing concept page link, or should I create a new one?)

Drop your answers line by line."

**The five pre-push items explained:**

1. **Reference ad link** - A link to a reference ad the creator and editor should follow. If the strategist says there is none, note "TBC" in the brief. Do not proceed without asking.
2. **Caption direction** - The style for words on screen (e.g. "Bold keyword captions, white text with black outline" or "Brand style captions" or "Minimal, only specified text overlays").
3. **Footage to use** - General editing approach for the whole ad (e.g. "70/30 creator to B-roll" or "Creator talking head with product B-roll cuts").
4. **Music** - Overall mood/direction (e.g. "Lo-fi ambient, morning routine energy" or "Upbeat, not hype"). If the strategist says "you choose", pick something appropriate based on the concept's valence zone and target avatar. Briefly describe the choice.
5. **Where in Notion** - Either a link to an existing concept page, or confirmation to create a new concept in the Master Creative Database.

**IMPORTANT: Never bundle these into sub-questions under a parent question. Always present them as 5 separate numbered items at the same level. This lets the strategist answer quickly, one line per item.**

**For the Creator table:**
- Brand Name
- Brand Website
- Product Link
- Google Drive link (ask strategist if not in conversation)
- Concept (one concise sentence describing the ad structure and narrative)
- Target Audience (short format: archetype name plus age range in brackets, e.g. "Chronic Skin Sufferers (25-45)")
- Reference (link to reference ad)

**For the Editor table:**
- Concept (same as creator table)
- Reference (can be same or different from creator table)
- Caption Direction (from pre-push item 2)
- Footage to Use (from pre-push item 3)
- Music (from pre-push item 4)
- Target Audience (same as creator table)

**For the Main Brief section:**
- Concept (same as above)
- Reference (same as above)

**For the Script table (The Brief):**

IMPORTANT - MODULE SPLITTING RULES: Do NOT cram an entire body section into a single row. Each row in the script table should be a logical unit where the visual direction AND editor notes are consistent. If the visual guidance or editor notes need to change mid-section, that is a new row.

Rules for splitting:
- If the creator's on-camera action changes (e.g. from "speaking to camera" to "holding up product"), start a new row.
- If the editor notes change (e.g. from "B-roll of bedroom" to "product close-up"), start a new row.
- If there is a tonal or emotional shift in the script (e.g. from problem agitation to solution reveal), start a new row.
- Each row should contain roughly 1-3 sentences, NOT an entire paragraph.
- The goal is that each row has ONE clear visual direction and ONE clear editor instruction.

A body section like "Body 1" should typically become 2-4 rows (e.g. "Body 1a", "Body 1b", "Body 1c") depending on the visual and editorial changes within it.

Module naming when splitting:
- `02 - Body 1a`
- `03 - Body 1b`
- `04 - Body 1c`
- `05 - Body 2a`
- `06 - Body 2b`
- etc.

For each row, set:
- Module (Hook, Body 1a, Body 1b, etc.)
- Script (What Creator Needs to Say) - 1-3 sentences per row
- Visual Guidance (What Creator Needs to Do) - mostly "Speaking to camera" unless a specific action is needed. Leave empty if no creator involved.
- Editor Notes (Creator Ignore This Column) - see the Editor Notes guidance below.

After the CTA, add a blank row, then:
- Hook 2, Hook 3, Hook 4 (alternative hook openings)

**EDITOR NOTES IN THE SCRIPT TABLE - CRITICAL GUIDANCE:**

The Editor Notes column is the editor's instruction manual for each module. Editors are executors, not thinkers. Every note must be a literal, specific editing direction that the editor can follow without making any creative decisions. The editor's biggest bottleneck is finding the right B-roll footage, so every row must tell them exactly what footage to source or use.

**What to include in each Editor Notes cell (in this order):**

1. **Text overlay** - What text appears on screen during this module. Pull this directly from the text overlay directions already in the script (from the script-writing phase). If the module has no text overlay, write "Captions only" so the editor knows to just caption the spoken words.
2. **B-roll direction** - What footage to cut to (if any). Be specific about what the footage should show. "B-roll of product" is too vague. "Close-up of sachet being torn open, powder pouring into mug" is actionable. If the module is purely talking head with no B-roll cuts, write "No B-roll - creator talking head only."
3. **Any additional editor instructions** - Music changes, pacing notes, animation suggestions. Only include if relevant to this specific module. Do not pad with generic notes.

**Where this information comes from:** The script-writing phase (Creative Strategy skill) already produces a production script table with Visual/B-Roll Direction, Text Overlay, and Editor Notes columns for each module. When pushing to Notion, pull directly from those columns. Do not rewrite or over-elaborate. The script's editor notes ARE the editor's instructions - just transfer them cleanly.

**Keep it short.** Each Editor Notes cell should be 2-4 lines max. If the editor needs a paragraph to understand what to do, the instruction is too complicated. Break it into simpler steps or split the module into sub-rows.

**Example of good Editor Notes:**
```
Text overlay: "Recovery score: 62"
B-roll: Open tight on watch face showing score, pull back to reveal creator
```

**Example of bad Editor Notes:**
```
The editor should consider opening with a close-up shot of the creator's Garmin watch, ideally showing a recovery score that looks concerning. This establishes the data-driven nature of the concept and creates immediate visual intrigue. The camera should then slowly pull back to reveal the creator in their kitchen setting with natural morning light.
```

**Also bad - conceptual vibes instead of directions:**
```
Two words. Let them sit. The simplicity is the emotional beat.
```
```
The morning shot should feel genuinely different from the tossing-and-turning shots earlier.
```
```
This line should get a smile from the viewer.
```
These tell the editor how something should FEEL, not what to DO. The editor can't execute a feeling. They can execute "Hold for 2 seconds. No cuts. No music." or "Cut to morning light through curtains. Woman stretching in bed."

The good version tells the editor exactly what to do in two lines. The bad version buries the same instruction in a paragraph of unnecessary context. The vibes version gives the editor nothing to execute at all.

**For the Shot List:**
Generate at least 10 shots. Each shot follows the naming convention: "Shot [number] - [Short Name]"
The visual description starts with a verb, under 15 words.

Shot categories to cover (avoid over-indexing on any one category):
- Product shots (hero shot, product in context, close-ups)
- Problem/agitation visuals (showing the problem the product solves)
- Desired outcome visuals (showing the result)
- Lifestyle shots (product in real life context)
- Ingredient/science shots (if relevant)
- Application/usage shots (product being used)

Aim for 5 shots that directly support the script, plus 5 extra shots that build the B-roll bank for future videos.

**For Other Creator Notes:**
Only generate this section if the script has something that deviates from standard talking-to-camera delivery. Examples: reaction shots, clips from other videos, specific transitions, props, unusual hook mechanics. If the entire script is straightforward talking head, leave the bullet points empty.

**For Other Editor Notes:**
Keep this section concise and focused on the overall editing approach for the whole ad. Cover:
- Overall pacing direction (e.g. "Conversational pace throughout, no rapid cuts in mechanism section")
- B-roll rhythm (e.g. "70/30 creator to B-roll split")
- Any recurring visual motifs (e.g. "Garmin watch is the visual anchor - returns at hook, agitation, and transformation")
- General text overlay style if not covered in the Editor table

Do NOT repeat module-level instructions that already exist in the script table's Editor Notes column. The Other Editor Notes section is for big-picture editing direction only. The module-level specifics live in the script table.

**For Shooting Instructions - Location:**
Fill in the location field with specific direction tied to the brand and concept. Not generic. Examples: "Farm with cows in the background", "Bright kitchen with natural light", "Bathroom mirror, clean and well-lit."

### Step 6: Show Summary and Confirm

Before pushing to Notion, show the strategist a summary:

"Here is what I am about to push to Notion:

- Brief name: [Brand Code][Concept No.] - [Concept Name]
- Brand: [Brand Name]
- Target Audience: [Target Audience]
- Script: [X] body sections + [Y] hook variations
- Shot List: [Z] shots
- Creator Notes: [Yes/No - brief description if yes]
- Location: [Location direction]

Confirm?"

Wait for the strategist to confirm before proceeding.

### Step 7: Create the Brief in Notion

**Step 7a: Find the Concept Brief database inside the Strategy section**

CRITICAL: The brief page MUST be created inside the "Concept Brief" inline database that lives INSIDE the Strategy section of the concept page. It must NEVER be created at the bottom of the concept page as a loose child page.

Here is exactly how to find the right location:
1. Fetch the concept page content
2. Look for the Strategy section (it has a brain emoji and is titled "Strategy")
3. Inside the Strategy section, find the inline database called "Concept Brief"
4. Get the data source ID of this Concept Brief database
5. Create the brief page inside THIS database

If you create the brief page as a child of the concept page directly (not inside the Concept Brief database inside Strategy), it will appear at the bottom of the page, which is WRONG. The brief must appear inside the Strategy section's Concept Brief database where the arrow points in the template. Look at how existing briefs are structured for other concepts in the same brand (e.g. Batch 1 concepts) to verify you're putting it in the right place.

**Step 7b: Create the brief page using the Official NSY Brief Template**

Create a new page inside the Concept Brief database using the Official NSY Brief Template (template ID: `31ddf9f700e58020841af3b4dc0f670d`). Set the title to the brief page name from Step 4.

Note: Template application is asynchronous. After creating the page, wait at least 8 seconds, then fetch the page to confirm the template has been applied and to get the inline database IDs for "The Brief" and "Shot List."

**Step 7c: Populate the page content**

Using the Notion update-page tool, populate:

1. The Creator table (Brand Name, Brand Website, Product Link, Google Drive, Concept, Target Audience, Reference)
2. The Shooting Instructions location line
3. Other Creator Notes (if applicable)
4. The Editor table (Concept, Reference, Caption Direction, Footage to Use, Music, Target Audience)
5. Other Editor Notes
6. The Main Brief concept/reference table

**Step 7d: Populate the Script table (The Brief inline database)**

IMPORTANT - TEMPLATE IS EMPTY: The "The Brief" inline database in the template contains ZERO rows. The skill creates ALL rows from scratch. There are no placeholder rows to worry about.

IMPORTANT - SORTING AND ORDERING: The database view is sorted ascending by the Module column. To guarantee correct display order, prefix every Module name with a two-digit sort number:

- `01 - Hook`
- `02 - Body 1a`
- `03 - Body 1b`
- `04 - Body 2a`
- `05 - Body 2b`
- `06 - Body 2c`
- `07 - Body 3a`
- `08 - Body 3b`
- (continue incrementing for additional body sub-sections)
- `[N] - CTA` (where N is the next number after the last body sub-section)
- `[N+1] -` (blank separator row - just the number prefix and dash, no module name)
- `[N+2] - Hook 2`
- `[N+3] - Hook 3`
- `[N+4] - Hook 4` (if applicable)

Example for a script with 3 body sections (each split into 2-3 rows) and 2 extra hooks:
- `01 - Hook`
- `02 - Body 1a`
- `03 - Body 1b`
- `04 - Body 1c`
- `05 - Body 2a`
- `06 - Body 2b`
- `07 - Body 2c`
- `08 - Body 3a`
- `09 - Body 3b`
- `10 - CTA`
- `11 -`
- `12 - Hook 2`
- `13 - Hook 3`

All rows can be created in a single batch API call. The ascending sort on the Module column will display them in the correct order because of the numeric prefix.

For each row, set: Module, Script (What Creator Needs to Say), Visual Guidance (What Creator Needs to Do), Editor Notes (Creator Ignore This Column).

**Step 7e: Populate the Shot List inline database**

IMPORTANT - TEMPLATE IS EMPTY: The "Shot List" inline database in the template contains ZERO rows. The skill creates ALL rows from scratch.

IMPORTANT - SORTING: The database view is sorted ascending by the Shot column. The existing naming convention "Shot 1 - [Name]", "Shot 2 - [Name]" etc. already sorts correctly in ascending order. Use zero-padded numbers if there are 10+ shots: "Shot 01 - [Name]", "Shot 02 - [Name]", etc.

All rows can be created in a single batch API call.

For each row, set: Shot (the name), Visual (What You Do) (the description).

**Step 7f: Update the Master Creative Database concept page**

After the brief page is created, update the concept page in the Master Creative Database with ALL of the following properties:

1. **Brief Link** - Set the "Brief Link" property to the FULL Notion URL of the newly created brief page as PLAIN TEXT with NO link formatting. The URL must look like: `https://www.notion.so/nsydigital/PageName-abc123def456` (the full URL you get when you copy the page link). When setting this via the Notion API or MCP, the rich_text content must be JUST the URL string with NO `link` object attached - if you include a `link` object, Notion will embed/preview it instead of showing the raw URL. Set it as: `{"rich_text": [{"text": {"content": "https://www.notion.so/nsydigital/..."}}]}` with NO `"link"` key inside the text object.
2. **Description** - Set the "Description" property to the concept sentence (same one used in the Creator/Editor tables).
3. **Hypothesis** - Set the "Hypothesis" property. This should explain WHY you are testing this concept. It should describe: who the target is, what messaging angle is being tested, what behavior or belief you are leveraging, and what you expect to happen. Write it as 2-3 sentences. This is critical for the team to understand the strategic reasoning behind the concept.
4. **ICP - Target Avatar** - Set the "ICP - Target Avatar" property. Use the same short format as the Target Audience field (archetype name plus age range in brackets).

ALL FOUR of these must always be populated. Never leave any of them empty after pushing a brief.

### Step 8: Confirm Completion

Tell the strategist:

"Brief created: [Brief Name]. Here is the link: [Notion URL]. Please open it and verify everything looks correct."

## Rules

1. Never guess brand information. Always pull from the conversation or ask the strategist.
2. The Concept field must be one concise sentence, not a paragraph. It describes the ad structure and narrative.
3. Target Audience follows the format: archetype name plus age range in brackets. No long descriptions.
4. Shot List naming convention is strict: "Shot [number] - [Short Name]". Visual descriptions start with a verb, under 15 words. Use zero-padded numbers for 10+ shots.
5. Visual Guidance column in the script table is for what the creator physically does on camera. Editing instructions, B-roll cuts, overlays belong in Editor Notes only.
6. For creator briefs, always populate the Creator toggle fully. For editor-only briefs, the Creator toggle sections (shooting instructions, Other Creator Notes, shot list, Google Drive link) can be left minimal or empty, and the Visual Guidance column can be left empty.
7. Editor Notes in the script table must follow the format: text overlay first, then B-roll direction, then any additional instructions. Keep each cell to 2-4 lines max. Pull directly from the script's production table - do not rewrite or over-elaborate.
8. The skill should be conversational and adaptive. Ask clarifying questions when needed rather than guessing. Err on the side of asking too many questions rather than too few.
9. Always show the summary and get confirmation before pushing to Notion.
10. Only one concept should be "In Progress" at a time in Notion to maintain accurate speed metrics.
11. If the strategist mentions adding editor notes after content comes back from the creator, that is fine. The Editor Notes column can be left empty initially and filled in later.
12. When generating shot lists, avoid over-indexing on product shots. Cover problem visuals, desired outcome visuals, lifestyle shots, and application shots too. Aim for at least 10 shots total, with extra shots beyond what the script needs to build a B-roll bank for future videos.
13. The "The Brief" and "Shot List" inline databases in the template are EMPTY (zero rows). Never expect placeholder rows to exist. Always create all rows from scratch.
14. Always prefix Module names with two-digit sort numbers (01, 02, 03...) to guarantee correct ascending sort order in the database view.
15. After creating the brief page, ALWAYS update the concept page in the Master Creative Database with ALL FOUR properties: "Brief Link" (plain text URL), "Description" (concept sentence), "Hypothesis" (strategic reasoning), and "ICP - Target Avatar" (target audience short format). Never leave any of these empty.
16. ALWAYS ask the strategist for a Reference ad link before building the brief. If the strategist has not provided one in the conversation, stop and ask. Do not proceed without it or leave it blank without explicit confirmation.
17. ALWAYS ask the strategist for the five pre-push items (Reference, Caption Direction, Footage to Use, Music, Where in Notion) as a flat numbered list if they have not been discussed. Never bundle these as sub-questions under a parent question. Each item gets its own number so the strategist can answer one per line.
18. Never cram an entire body section into a single script row. Split body sections into sub-rows (Body 1a, Body 1b, etc.) wherever the visual direction, editor notes, or tonal shift changes. Each row should have 1-3 sentences max and ONE clear visual/editor instruction.
19. **NEVER use em dashes (the long dash character) anywhere in the output - not in scripts, not in editor notes, not in creator notes, not in any Notion content. Always use a regular hyphen/dash (-) instead. This is a hard rule with zero exceptions.**
20. **Brief Link must always be the full plain text URL with NO link object. When setting via Notion MCP/API, use `{"text": {"content": "https://..."}}` with NO `"link"` key. If a `link` key is included, Notion embeds/previews it instead of showing the raw URL, which breaks the Google Sheets sync. This applies to ALL URLs set in Notion properties.**
21. **All URLs in Notion table cells must be plain text. Do NOT wrap them in markdown link syntax like `[text](url)`. Just paste the raw URL.**
22. **ALWAYS ask the strategist whether this is a creator brief or an editor-only brief before building. This determines the level of detail needed in the Creator sections.**
23. **Batch number must be calculated automatically using the deliverables from Team Projects and the count of existing concepts. Never ask the strategist for the batch number.**
24. **Creator Needed? property**: If the strategist says it is a creator brief, set "Creator Needed?" to __YES__. If it is an editor-only brief, set "Creator Needed?" to __NO__. This must always match the brief type.
25. **Status on creation**: When creating the concept page in the Master Creative Database, always set Status = "In progress" and Status Type = "Strategy". Never leave these as default values (To-Do / Backlog).
26. **Concept page Name property**: When creating a new concept row in the Master Creative Database, the "Name" property must be the descriptive concept name (e.g. "30 Day Transformation", "Wife testimonial", "Dr Huberman hook"). It must NEVER be just the brand code + number (e.g. "ZAP7"). Look at existing concepts for the same brand to see the pattern. The brand code and concept number are handled by separate properties.
27. **Brief page placement**: The brief page MUST be created inside the Concept Brief inline database that lives inside the Strategy section of the concept page. NEVER create it as a loose child page at the bottom of the concept page. If the brief appears at the bottom of the page outside the Strategy section, it is in the wrong place. Always verify placement by checking that the brief shows up under Strategy > Concept Brief, not as a standalone page below the Time Log.
28. **Editor Notes must be pulled from the script.** The production script table already contains text overlay, B-roll direction, and editor notes for each module. When pushing to Notion, transfer these directly into the Editor Notes column. Do not rewrite, expand, or add unnecessary context. The script IS the source of truth for editor instructions.

## Quality Checks

Before pushing to Notion, verify:
- Brief page name follows [Brand Code][Concept No.] - [Concept Name] format
- Concept field is one concise sentence
- Target Audience is in short format (archetype + age range)
- Every script row has a Module name with a two-digit sort prefix
- Module sort numbers are sequential with no gaps
- Body sections are split into sub-rows (a, b, c) - no row has more than 3 sentences
- Each script row has consistent visual guidance and editor notes (if they change mid-section, split the row)
- Hook variations exist after a blank separator row
- Shot List has at least 10 shots with correct naming convention (zero-padded if 10+)
- Location in shooting instructions is specific to the brand/concept, not generic
- Editor table is fully populated (Concept, Reference, Caption Direction, Footage to Use, Music, Target Audience) - if any field is missing, ask the strategist
- Creator table is fully populated for creator briefs (Brand Name, Brand Website, Product Link, Google Drive, Concept, Target Audience, Reference) - if Reference is missing, ask the strategist
- Reference has been provided by the strategist (not auto-generated)
- Brief Link property in the Master Creative Database is set to the brief page URL as PLAIN TEXT (not a formatted link)
- Description property in the Master Creative Database is populated with the concept sentence
- Hypothesis property in the Master Creative Database is populated with 2-3 sentences explaining why this concept is being tested
- ICP - Target Avatar property in the Master Creative Database is populated with the target audience short format
- **ZERO em dashes exist anywhere in the output. Scan all text for the em dash character and replace with regular dashes.**
- All URLs in Notion table cells are plain text (not markdown links)
- Batch number has been calculated correctly based on deliverables and existing concept count
- Brief type (creator vs editor-only) has been confirmed with the strategist
- "Creator Needed?" property matches the brief type (checked for creator briefs, unchecked for editor-only)
- Status is set to "In progress" and Status Type is set to "Strategy" on the concept page
- **Editor Notes in script table follow the format: text overlay, then B-roll direction, then additional instructions. Each cell is 2-4 lines max. No paragraphs.**
- **Editor Notes are pulled directly from the script's production table, not rewritten or expanded.**

## Notion Reference IDs

- Master Creative Database data source: `collection://1d5df9f7-00e5-81a2-9e34-000be92d1412`
- Team Projects data source (for Brand Code lookup): `collection://1d5df9f7-00e5-812a-86f4-000b4eaef08d`
- Video Concept template: `1d5df9f7-00e5-8153-9e78-f3f7d6dfdf3b`
- Official NSY Brief Template: `31ddf9f700e58020841af3b4dc0f670d`

## References

- `references/template-structure.md` - The exact structure of the Official NSY Brief Template
- `references/example-brief.md` - A fully completed example brief (Fat Cow Skincare)
