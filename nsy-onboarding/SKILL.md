---
name: nsy-onboarding
description: Onboard a new NSY Digital client end-to-end. Use this skill whenever Nativ says "onboard", "set up a new client", "create the onboarding", "get them onboarded", "set up in Notion", "set up in Slack", "onboarding for [client]", or any variation of needing to onboard a new client after a deal is closed. Also triggers when someone mentions needing to create a Team Projects page, send an onboarding form, set up a Slack channel, or prepare for a new client's start date. This skill handles everything from Team Projects setup through Slack channel creation, onboarding form sharing, Google Sheets approval system, CRM updates, invoice sequencing, and pre-start preparation. Always use this skill for onboarding — do not attempt to onboard a client without it.
---

# NSY Client Onboarding Skill

End-to-end onboarding workflow for new NSY Digital clients. This skill is used after a deal is closed and the agreement is signed. It ensures every system is set up correctly and nothing is missed.

**Who uses this skill:** Nativ or whoever is running the onboarding. The skill walks through every step, asks the right questions, and flags manual steps that can't be automated.

**CRITICAL RULE:** Do NOT start onboarding until the agreement is signed. No exceptions.

---

## Step 1: Gather Required Information

Pull from conversation context first. Only ask for what is genuinely missing.

**Required (must have before starting):**
- `brand_name` — The brand name as it will appear in Notion (e.g. "Mission", "Ascent"). Must match exactly across all systems (Notion, Google Sheets, Make.com).
- `brand_code` — 2-4 letter code (e.g. "MSN", "ASC")
- `agreement_signed` — Confirm the agreement is signed. Do NOT start onboarding until signed.
- `start_date` — Engagement start date (e.g. "6th April 2026"). This becomes the Batch Start Date.
- `services` — Which services: Ad Creative, Meta Ads, Google Ads, TikTok Ads, Static Ads, Editing, Consulting
- `deliverables` — Formatted deliverables string (e.g. "• 6 Video concepts (4 hook variations each) per month")
- `deal_type` — Retainer or One-Time (Project Basis)
- `country` — UK or USA (for ad targeting)
- `monthly_fee` — For invoicing
- `poc_names` — Point of contact names (for Slack invite and onboarding form)
- `poc_emails` — Email addresses for Slack invites
- `facebook_bm_id` — NSY's Facebook Business Manager ID: 1084328432442084 (include in onboarding message if Meta creative or buying is involved)

**Always ask these (may be empty initially but must be asked):**
- `strategist` — Who is the Creative Strategist?
- `creative_coordinator` — Who is the Creative Coordinator?
- `pod` — Which Pod (1, 2, 3, or 4)?
- `media_buyer` — Who is the Media Buyer? (only if Meta/Google/TikTok management)

**Auto-set (don't ask):**
- `creative_batch` — Always "1" for new clients
- `signed_date` — Today's date (or the date the agreement was signed)
- `batch_start_date` — Same as `start_date`. NEVER leave this empty.
- `status` — Always "Active"

---

## Step 2: Create Team Projects Page in Notion

### 2.1 Create the page using the Brand Page Template

**Database:** Team Projects
**Data Source ID:** `1d5df9f7-00e5-812a-86f4-000b4eaef08d`
**Template ID:** `1d5df9f7-00e5-8184-b9a6-fc1f2ea2cf7b` (Brand Page Template)

Create the page with ALL of these properties populated:

| Property | Value | Notes |
|---|---|---|
| Brand | [brand_name] | Must match exactly in Make.com datastore |
| Brand Code | [brand_code] | 2-4 letters |
| Status | Active | Always Active for new clients |
| Deal | [deal_type] | Retainer or One-Time |
| Services | [services array] | e.g. ["Ad Creative", "Google Ads"] |
| Deliverables | [formatted string] | Use bullet format |
| Country Running Ads In | [country] | UK or USA |
| Creative Batch | 1 | Always 1 for new clients |
| Signed | [signed_date] | Date agreement was signed |
| Batch Start Date | [start_date] | **NEVER LEAVE EMPTY** |
| Strategist | [if assigned] | Can be empty |
| Creative Coordinator | [if assigned] | Can be empty |
| Pod | [if assigned] | Can be empty |
| Media Buyer | [if assigned] | Can be empty |
| Icon | [emoji] | Choose one that represents the brand |

### 2.2 Verify the template populated correctly

After creating the page, fetch it to confirm these sub-pages were created by the template:
- Context Library
- Onboarding Response (contains Product databases and Form views)
- Onboarding Call (inside Meeting Notes)
- Ideas Library
- Monthly Reports
- Creator Hub
- Performance Hub
- Project Overview section with linked view of Master Creative Database

### 2.3 Manual Steps — TELL THE OPERATOR TO DO THESE

**CRITICAL: These steps CANNOT be done via the Notion API. The operator MUST do them manually. Present each one as a numbered checklist item with exact click-by-click instructions.**

---

**MANUAL STEP A — Set the Project Overview filter:**
1. Open the new brand page in Notion
2. Scroll down to "👀 Project Overview"
3. Find the "View of Master Creative Database" linked database
4. Click the filter icon (or "+ Filter")
5. Set filter: **"Brand" → "contains" → "[brand_name]"**
6. This ensures only this brand's concepts show in the Project Overview

**WHY:** Without this filter, ALL brands' scripts and concepts will show on this page. This is confusing and makes the page unusable for the team.

---

**MANUAL STEP B — Set the Ideas Library filter:**
1. Open the "Ideas Library" sub-page (purple card)
2. Find the "Brand(s)" filter at the top of the database
3. Click it and set: **"Brand(s)" → "contains" → "[brand_name]"**
4. This ensures only this brand's ideas show in the Ideas Library

**WHY:** Same as above. Without this filter, every brand's ideas will show.

---

**MANUAL STEP C — Share the Onboarding Response form:**
1. Open the "Onboarding Response" sub-page (red card)
2. Click the **"Product 1 Form"** tab at the top (next to "Product 1" table view)
3. Click the **"Share form"** button (blue button, top right)
4. A sharing modal appears. Change "Who can fill out" from "Only members at NSY Digital" to **"Anyone on the web with link"**
5. Click **"Copy form link"**
6. Save this link — you will send it to the client in the Slack onboarding message

**WHY:** By default, the form is restricted to NSY team members only. The client cannot fill it out unless you change the sharing to "Anyone on the web with link". If you send the Notion page link instead of the form link, the client won't be able to access it.

**CRITICAL:** Send the FORM link (from "Share form"), NOT the Notion page URL. These are different URLs.

---

**MANUAL STEP D — Create Google Drive folder:**
1. Go to the NSY client Google Drive structure
2. Create a new folder named "[brand_name]"
3. Copy the folder link
4. Go back to the Team Projects page and paste the link into the **"Google Drive Link"** property

---

## Step 3: Set Up Google Sheets Approval System

Each client needs their own Google Sheet so they can review and approve/reject creative concepts without needing Notion access. When a concept reaches "Client reviewing" status in Notion, a Make.com automation pushes it to the client's sheet automatically.

**Steps (all manual — tell the operator):**

**MANUAL STEP E — Create the Google Sheet:**
1. Go to the Google Sheet template
2. File → Make a copy
3. Rename it: **"[brand_name] | Creative Performance Hub"**
4. Share the sheet with the client's POC email(s)
5. Copy the **Sheet ID** from the URL (the long string between `/d/` and `/edit`)

**MANUAL STEP F — Add to Make.com datastore:**
1. Go to Make.com → Data stores → "Google Sheets by Brand"
2. Click "Add"
3. Enter the Brand Name: **[brand_name]** (must match the Notion Brand property EXACTLY — case sensitive)
4. Paste the Sheet ID
5. Click Save

**MANUAL STEP G — Trigger initial population:**
1. Go to the Notion Master Creative Database for this client
2. If there are existing concepts, edit the Description field on each one (add a dot, then remove it) to trigger the Make.com webhook and populate the sheet
3. For new clients with no existing concepts yet, this step can be skipped — concepts will auto-populate as the team creates them

**IMPORTANT:** The brand name in Make.com MUST exactly match the Brand property in Notion. If it's "Mission" in Notion, it must be "Mission" in Make.com — not "mission", not "Mission Health & Wellness Limited", not "drink Mission".

---

## Step 4: Create Slack Channel and Send Onboarding Message

### 4.1 Create the Slack channels

**Two channels per client:**
- `#nsy-[brand_name_lowercase]` — Client-facing channel (Tom, Alex, etc. are in here)
- `#internal-[brand_name_lowercase]` — Internal team channel (NSY team only)

**Manual step:** The operator needs to create both channels in Slack and invite:

**Client channel (#nsy-[brand]):**
- The client's POC(s)
- Any additional client team members they've asked to include
- Nativ
- Assigned strategist (if known)
- Creative coordinator (if known)

**Internal channel (#internal-[brand]):**
- Nativ
- Assigned strategist
- Creative coordinator
- Media buyer (if applicable)
- Editors assigned to the account

### 4.2 Send the onboarding message

Post this in the **client-facing** channel (#nsy-[brand]):

```
Welcome to NSY! 🚀

We are very excited to get started with you. To be proactive, I'd love to get the onboarding details sorted so we are ready to hit the ground running on [start_date].

Here are the onboarding details for you:

• Please fill out this onboarding form - [ONBOARDING_FORM_LINK]
    ◦ The more detail you can give us here, the better our research and creative will be from day one

• What day works for our onboarding/kickoff call? Ideally [suggest timeframe]
    ◦ We will come to this call with creative ideas which we'll present and brainstorm, then we can start production

[If Google Ads included:]
• We'll also get a call booked with James (our Google Ads specialist) to walk you through the audit scope and how he'd approach the restructure

[If Meta creative or buying:]
• Our Facebook Business Manager ID for any access you need to share: 1084328432442084

Really excited about getting started with you and helping scale [brand_name]! Let me know if you have any questions 🙏
```

**CRITICAL:** The `[ONBOARDING_FORM_LINK]` must be the shareable form link from Step 2.3 Manual Step C. NOT the Notion page link.

---

## Step 5: Pre-Populate the Onboarding Call Page

The Onboarding Call page lives inside Team Projects → [Brand] → Meeting Notes → Onboarding Call. Pre-populate it with the standard structure so the strategist has a framework ready for the kick-off call.

**Structure (based on the Ascent gold standard):**

```
Recording Link (if available):
Who attended the call:
---

# [brand_name] x NSY Digital - Onboarding Call

**Duration:** 30 minutes
**Date:** [TBD]
**Attendees:** [TBD]

---

## 1. Meet Your Team (3 mins)
- **Nativ** - Account Lead. Oversees strategy, keeps everything on track, your main point of escalation
- **[Strategist Name]** - Lead Creative Strategist. Owns research, concept development, scripting, and briefing. Your day-to-day creative partner
- **[Coordinator/Production Name]** - Creative Production Manager. Manages the editing pipeline and delivery timelines

---

## 2. How We Track Everything (5 mins)
**Creative Approval Sheet walkthrough:**
- Every brief and edit flows through a shared Google Sheet connected to our internal system
- When a script or brief is ready for you to review, it automatically appears in the sheet as "Client Brief Review"
- You can open the brief directly from the sheet, review it, and either approve or request revisions
- If you want changes, move the status to "Brief Needs Revisions" and it flows back to the team automatically
- When an edited ad is ready for your sign-off, it shows as "Client Edit Review"
- Once you approve, move it to "Edit Approved" and we move straight to delivery
- No need for constant back-and-forth in Slack on approvals. Everything lives in one place with a full audit trail

**Bookmark this sheet for easy access.**

---

## 3. Batch 1 Concept Ideas (10 mins)
[Strategist to fill in before the call with initial creative directions based on research, audit, and onboarding response data]

### Video Concepts
1. **[Concept Name]** - [Brief description of angle, format, target audience]
2. **[Concept Name]** - [Brief description]
[Continue for all planned concepts]

### Static Concepts (if applicable)
1. **[Concept Name]** - [Brief description]

---

## 4. Questions for [Client POC Name] (5 mins)
1. **B-roll and assets:** What do you currently have? What are we missing?
2. **Creator content:** Have you worked with creators who film to camera before? Open to us sourcing creators?
3. **Top ad update:** What's currently performing best? Anything changed since the audit?
4. **Landing pages:** How are current pages performing? Open to testing different destinations?
5. **Post-purchase surveys:** Are you running any? If not, we recommend adding 3 simple questions
6. **Compliance:** Any claims we need to avoid?

---

## 5. Client's Questions (5 mins)
Open floor. Anything about the creative process, timelines, creator sourcing, communication.

---

## Notes
-

## Observations
-

## Actions
- Book in bi-weekly calls
- [Client] to share [specific access/assets needed]
- [Strategist] to finalise Batch 1 concept selection by [date]
- Creator sourcing to begin [date]
```

**IMPORTANT:** The strategist fills in the Batch 1 concepts before the actual call. This page is a framework, not a finished document. The "Meet Your Team" section and "Questions for Client" section should be personalised to this specific client.

---

## Step 6: Update Systems

### 6.1 Sales CRM
Find the client's page in the Sales CRM and update:
- Add a note: "Agreement signed [date]. Onboarded to Team Projects. Slack channel created."
- Update the onboarding checklist to tick off completed items

### 6.2 Client Contract Management Database
If not already added, create a record:
- **Data Source ID:** `a39b7622-6ba6-49a7-9059-f93942d02c1b`
- Brand: [brand_name] (use the trading name, e.g. "Mission (drink Mission)")
- Status: Active
- Contract Start Date: [start_date]
- Payment Amount/mo: [monthly_fee]
- Contract Duration: as per agreement
- Deliverables: [services]
- POC: [poc_names]
- Email: [poc_email]
- Leave "Last Paid" empty

### 6.3 War Map
Mark completed tasks as Done. Create new tasks:
- Send Month 1 invoice — Today, Urgent
- Schedule kick-off/onboarding call — This Week, High
- Schedule first in-person creative planning session (if included) — This Week, High
- [If Google Ads:] Confirm Google team member scope and pricing
- [If Google Ads:] Schedule Google scope walkthrough call with client
- Begin creative research ahead of [start_date]
- Set up Google Sheet approval system — This Week, High

---

## Step 7: Invoice Sequencing

**Do NOT send the invoice before the agreement is signed.**

Once signed:

1. **Month 1 invoice** — Send the same day the agreement is signed (or the next business day)
   - Amount: [monthly_fee] + VAT
   - Description: "Video Ad Creative - [Package] (6th April - 5th May 2026)" [adjust dates]
   - Reference: [service_period_start] - [service_period_end] (e.g. "06/04/2026 - 05/05/2026")
   - Due: 7 days from issue date
   - Each service is a separate line item (e.g. Ad Creative line + Google line)

2. **One-off services** (if applicable, e.g. Google Ads audit)
   - Can be included as a separate line item on the Month 1 invoice
   - Description: "Google Ads Audit and Restructure (One-Off)"
   - Invoice upon commencement, NOT upon completion

3. **Subsequent monthly invoices** — Issued on the same day of each month as the start date

Invoice via Xero. Use the client's registered company name, address, and VAT number.

### 7.1 Send confirmation email to client

After sending the invoice, email the client confirming:
- Invoice has been sent
- Slack channel is set up and they've been invited
- Onboarding details are in the Slack channel
- Next steps (fill out onboarding form, schedule kick-off call)

---

## Step 8: Pre-Start Preparation

Between now and the start date:

1. **Run the creative research skill** — Build the full research library (Brand Overview, Target Audience, Competitive Landscape, Science/Mechanism, Customer Voice, etc.)
2. **Set up the client Claude project** — Create a project with all research docs uploaded
3. **Fill the Context Library** — Once the client completes the onboarding form, move the data into the Context Library in Team Projects
4. **Prepare for the onboarding call** — Strategist fills in Batch 1 concepts on the Onboarding Call page
5. **Source creators** (if UGC) — Begin creator search based on brand, target demo, and location

---

## Step 9: Client Communication Cadence Setup

Once the engagement starts, the following cadence kicks in (per Client Communication SOP):

| Day | Touchpoint |
|---|---|
| Monday | Weekly Performance Report (Loom video + Slack summary) |
| Tuesday | Check-in message in Slack (3-5 lines) |
| Wednesday | No scheduled touchpoint |
| Thursday | Check-in message in Slack (3-5 lines) |
| Friday | No scheduled touchpoint |

Plus bi-weekly check-in calls (20-30 mins). Schedule the first one during the onboarding call.

---

## Master Onboarding Checklist

Copy this into the CRM page for tracking:

```
## Onboarding Checklist
1. Agreement signed ✅
2. Team Projects page created (Brand Page Template)
3. All properties filled (including Batch Start Date)
4. Project Overview filter set (Brand contains [brand_name])
5. Ideas Library filter set (Brand(s) contains [brand_name])
6. Onboarding form shared (Anyone on the web with link)
7. Google Drive folder created and linked
8. Google Sheet created ("[brand_name] | Creative Performance Hub")
9. Google Sheet added to Make.com datastore (brand name matches exactly)
10. Slack channels created (#nsy-[brand] + #internal-[brand])
11. Client invited to Slack
12. Onboarding message sent with form link
13. Client Contract Management database updated
14. Month 1 invoice sent
15. Confirmation email sent to client
16. Onboarding Call page pre-populated with template
17. Kick-off/onboarding call scheduled
18. First in-person creative planning session scheduled (if applicable)
19. [If Google Ads:] Google team call scheduled
20. Creative research started
21. Client Claude project set up
22. Context Library populated (after client fills onboarding form)
23. Google Sheet shared with client
24. Bi-weekly call cadence set up
```

---

## Common Mistakes to Avoid

1. **Forgetting Batch Start Date** — Must match the engagement start date. Without it, batch tracking breaks.
2. **Not setting Project Overview filter** — ALL brands' scripts show on the page without "Brand contains [name]".
3. **Not setting Ideas Library filter** — ALL brands' ideas show without the filter.
4. **Sending Notion page link instead of form link** — Client can't fill out the page. They need the FORM link (Share form → Anyone on the web with link → copy).
5. **Not asking about Strategist, Coordinator, Pod** — Even if empty, always ask. These get forgotten.
6. **Invoicing before agreement is signed** — Never invoice before the contract is executed.
7. **Invoicing one-off services upon completion** — Invoice when work STARTS, not when delivered.
8. **Brand name mismatch in Make.com** — Must exactly match Notion. "Mission" ≠ "mission" ≠ "Mission Health & Wellness Limited".
9. **Not creating internal Slack channel** — Team needs a private space to discuss strategy without the client seeing.
10. **Not sharing Google Sheet with client** — The sheet needs to be shared with their email so they can review and approve concepts.
11. **Not creating Google Drive folder** — Team needs a shared folder for raw files, B-roll, brand assets.
12. **Skipping the onboarding call page** — The strategist needs the framework before the call. Don't leave it blank.

---

## Reference IDs

- **Team Projects Database Data Source:** `1d5df9f7-00e5-812a-86f4-000b4eaef08d`
- **Brand Page Template ID:** `1d5df9f7-00e5-8184-b9a6-fc1f2ea2cf7b`
- **Client Contract Management Data Source:** `a39b7622-6ba6-49a7-9059-f93942d02c1b`
- **Sales CRM Data Source:** `775b8d3e-b088-4589-9f9d-92e911ab31ba`
- **War Map Data Source:** `59c69797-cbf8-4ecf-9f3a-c00caf09f0fc`
- **Client Onboarding Task Database Data Source:** `d1eb316e-80e8-46b0-a133-0d55db779f8d`
- **Slack channel naming:** `#nsy-[brand_lowercase]` (client) + `#internal-[brand_lowercase]` (team)
- **Google Ads team member (Slack):** James — U0A2C27L9D5
- **NSY Facebook Business Manager ID:** 1084328432442084
- **Make.com datastore:** Google Sheets by Brand (brand name must match Notion exactly)
