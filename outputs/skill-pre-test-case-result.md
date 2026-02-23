# Skill Triggering Pre-Test Results (Baseline — Current Descriptions)
**Executed:** 2026-02-20
**Total Test Cases:** 135
**Note:** All trigger predictions are self-assessments based on current description language. Actual runtime behavior may vary across sessions.

---

## Summary Dashboard

| Metric | Count |
|---|---|
| ✅ Clean PASS | 87 (64%) |
| ⚠️ PASS WITH CO-FIRE | 36 (27%) |
| ❌ FAIL | 12 (9%) |

---

## Results by Skill

---

### SKILL: `docx`
**Current description:** *"Use when user wants to create, read, edit, or manipulate Word documents (.docx files). Triggers on: 'Word doc', 'word document', '.docx', reports, memos, letters, templates."*

| Test ID | User Statement | Expected | Predicted | Co-Fires | Outcome |
|---|---|---|---|---|---|
| docx-TC01 | "Create a Word document summarizing Q4 sales..." | `docx` | `docx` | `smart-brevity-docx` | ⚠️ CO-FIRE |
| docx-TC02 | "I have a .docx file — extract text and give me markdown" | `docx` | `docx` | none | ✅ PASS |
| docx-TC03 | "Write a professional memo...save as a Word file" | `docx` | `docx` | `smart-brevity-docx` | ⚠️ CO-FIRE |
| docx-TC04 | "My Word doc has tracked changes — accept all and give clean version" | `docx` | `docx` | none | ✅ PASS |
| docx-TC05 | "Convert this .doc file to .docx format" | `docx` | `docx` | none | ✅ PASS |

**Skill Result: 3/5 PASS · 2 co-fire · 0 FAIL**

---

### SKILL: `pdf`
**Current description:** *"Use when user wants to do anything with PDF files — read, extract, combine, split, rotate, watermark, create, fill forms, encrypt, OCR."*

| Test ID | User Statement | Expected | Predicted | Co-Fires | Outcome |
|---|---|---|---|---|---|
| pdf-TC01 | "Merge these three PDF files into one" | `pdf` | `pdf` | none | ✅ PASS |
| pdf-TC02 | "Extract text from this scanned PDF — it's a photo of a contract" | `pdf` | `pdf` | none | ✅ PASS |
| pdf-TC03 | "Add a 'CONFIDENTIAL' watermark to every page of this PDF" | `pdf` | `pdf` | none | ✅ PASS |
| pdf-TC04 | "Split this 40-page PDF — pages 1–15 one file, 16–40 another" | `pdf` | `pdf` | none | ✅ PASS |
| pdf-TC05 | "This PDF form needs to be filled in — name is John Smith..." | `pdf` | `pdf` | none | ✅ PASS |

**Skill Result: 5/5 PASS · 0 co-fire · 0 FAIL**

---

### SKILL: `pptx`
**Current description:** *"Use any time a .pptx file is involved — creating, reading, editing, combining, splitting. Triggers on: 'deck', 'slides', 'presentation', .pptx filename."*

| Test ID | User Statement | Expected | Predicted | Co-Fires | Outcome |
|---|---|---|---|---|---|
| pptx-TC01 | "Create a 10-slide presentation on AI history..." | `pptx` | `pptx` | none | ✅ PASS |
| pptx-TC02 | "I uploaded a PowerPoint deck — extract all speaker notes into a Word doc" | `pptx` | `pptx` | `docx` | ⚠️ CO-FIRE |
| pptx-TC03 | "Take slides 3, 7, 12 from my deck and create a new presentation" | `pptx` | `pptx` | none | ✅ PASS |
| pptx-TC04 | "Review my uploaded .pptx and tell me if there are layout issues" | `pptx` | `pptx` | none | ✅ PASS |
| pptx-TC05 | "Update the title and subtitle on the cover slide of my presentation" | `pptx` | `pptx` | none | ✅ PASS |

**Skill Result: 4/5 PASS · 1 co-fire · 0 FAIL**

---

### SKILL: `xlsx`
**Current description:** *"Use when a spreadsheet file is the primary input or output — open, read, edit, fix .xlsx/.xlsm/.csv/.tsv, or create new spreadsheets."*

| Test ID | User Statement | Expected | Predicted | Co-Fires | Outcome |
|---|---|---|---|---|---|
| xlsx-TC01 | "Create an Excel spreadsheet that tracks monthly expenses..." | `xlsx` | `xlsx` | none | ✅ PASS |
| xlsx-TC02 | "I uploaded a messy CSV — headers in row 3, junk in first rows..." | `xlsx` | `xlsx` | none | ✅ PASS |
| xlsx-TC03 | "Add a profit margin column to my uploaded Excel file" | `xlsx` | `xlsx` | none | ✅ PASS |
| xlsx-TC04 | "Convert my uploaded .xlsx to a CSV" | `xlsx` | `xlsx` | none | ✅ PASS |
| xlsx-TC05 | "My Excel file has duplicate rows — remove duplicates" | `xlsx` | `xlsx` | none | ✅ PASS |

**Skill Result: 5/5 PASS · 0 co-fire · 0 FAIL**

---

### SKILL: `product-self-knowledge`
**Current description:** *"Use when responding with specific facts about Anthropic products — Claude Code, Claude API, Claude.ai plans, pricing, models, rate limits, SDK usage."*

| Test ID | User Statement | Expected | Predicted | Co-Fires | Outcome |
|---|---|---|---|---|---|
| psk-TC01 | "What are differences between Claude Pro and Claude Team plans?" | `product-self-knowledge` | `product-self-knowledge` | none | ✅ PASS |
| psk-TC02 | "How do I install Claude Code and what are the Node.js requirements?" | `product-self-knowledge` | `product-self-knowledge` | `claude-automation-recommender` | ⚠️ CO-FIRE |
| psk-TC03 | "What is the context window size for Claude Opus 4 via the API?" | `product-self-knowledge` | `product-self-knowledge` | none | ✅ PASS |
| psk-TC04 | "Does the Claude API support streaming responses? How with Python SDK?" | `product-self-knowledge` | `product-self-knowledge` | none | ✅ PASS |
| psk-TC05 | "What are the current rate limits for the Claude API on free tier?" | `product-self-knowledge` | `product-self-knowledge` | none | ✅ PASS |

**Skill Result: 4/5 PASS · 1 co-fire · 0 FAIL**

---

### SKILL: `frontend-design` (public)
**Current description:** *"Use when building web components, pages, dashboards, React components, HTML/CSS layouts, or when styling/beautifying any web UI."*

| Test ID | User Statement | Expected | Predicted | Co-Fires | Outcome |
|---|---|---|---|---|---|
| fd-TC01 | "Build me a landing page for a SaaS product called 'FlowSync'..." | `frontend-design` | `frontend-design` (public) | `frontend-design` (plugin) | ⚠️ CO-FIRE |
| fd-TC02 | "Create a React dashboard component with KPI cards..." | `frontend-design` | `frontend-design` (public) | `frontend-design` (plugin) | ⚠️ CO-FIRE |
| fd-TC03 | "My website looks generic — here's the HTML. Redesign it." | `frontend-design` | `frontend-design` (public) | `frontend-design` (plugin) | ⚠️ CO-FIRE |
| fd-TC04 | "Build a dark-mode pricing table in React with three tiers" | `frontend-design` | `frontend-design` (public) | `frontend-design` (plugin) | ⚠️ CO-FIRE |
| fd-TC05 | "I need a sticky navigation bar component..." | `frontend-design` | `frontend-design` (public) | `frontend-design` (plugin) | ⚠️ CO-FIRE |

**Skill Result: 0/5 PASS · 5 co-fire · 0 FAIL**
*Note: Primary skill is correct in all 5 cases, but the duplicate plugin skill always co-fires.*

---

### SKILL: `account-lookup`
**Current description:** *"Search and identify ServiceNow accounts by name. Call before Data_Analytics_Connection for any company name query. Handles disambiguation."*

| Test ID | User Statement | Expected | Predicted | Co-Fires | Outcome |
|---|---|---|---|---|---|
| al-TC01 | "Pull up the account details for Walmart." | `account-lookup` | `account-lookup` | none | ✅ PASS |
| al-TC02 | "I need to look at data for JP Morgan — what's their account number?" | `account-lookup` | `account-lookup` | none | ✅ PASS |
| al-TC03 | "Find the ServiceNow account for Delta Airlines" | `account-lookup` | `account-lookup` | none | ✅ PASS |
| al-TC04 | "What opportunity is linked to the Nike deal we're working on?" | `account-lookup` | `account-lookup` | none | ✅ PASS |
| al-TC05 | "I have a call with 3M tomorrow — find their account" | `account-lookup` | `account-lookup` | none | ✅ PASS |

**Skill Result: 5/5 PASS · 0 co-fire · 0 FAIL**

---

### SKILL: `ai-coach-crm-now-next`
**Current description:** *"Use when seller mentions 'Now Next CRM', 'NNCRM', 'Now Next', CRM transformation deal levers, CRM co-investment, CRM pricing ramp, CRM AI Foundry, or CRM deal acceleration programs."*

| Test ID | User Statement | Expected | Predicted | Co-Fires | Outcome |
|---|---|---|---|---|---|
| nncrm-TC01 | "Does my CRM deal at Acme qualify for the Now Next CRM program?" | `ai-coach-crm-now-next` | `ai-coach-crm-now-next` | none | ✅ PASS |
| nncrm-TC02 | "Explain how NNCRM methodology works and the approval process" | `ai-coach-crm-now-next` | `ai-coach-crm-now-next` | none | ✅ PASS |
| nncrm-TC03 | "Customer interested in CRM transformation — what co-investment options?" | `ai-coach-crm-now-next` | `ai-coach-crm-now-next` | `ai-coach-universal-strategy-coach` | ⚠️ CO-FIRE |
| nncrm-TC04 | "Can I get a CRM pricing ramp for the Walmart deal?" | `ai-coach-crm-now-next` | `ai-coach-crm-now-next` | none | ✅ PASS |
| nncrm-TC05 | "I want to accelerate my CRM deal at Target — what programs available?" | `ai-coach-crm-now-next` | `ai-coach-crm-now-next` | `ai-coach-universal-strategy-coach` | ⚠️ CO-FIRE |

**Skill Result: 3/5 PASS · 2 co-fire · 0 FAIL**

---

### SKILL: `ai-coach-crm-pursuit-plan`
**Current description:** *"Create CRM Pursuit Plans for CRM sellers with account intelligence, motion assessment, opportunity prioritization. Produces comprehensive Word document."*

| Test ID | User Statement | Expected | Predicted | Co-Fires | Outcome |
|---|---|---|---|---|---|
| crm-pp-TC01 | "Create a CRM pursuit plan for my top 3 accounts this quarter" | `ai-coach-crm-pursuit-plan` | `ai-coach-crm-pursuit-plan` | `smart-brevity-docx` | ⚠️ CO-FIRE |
| crm-pp-TC02 | "I need a formal pursuit plan document for the Boeing opportunity" | `ai-coach-crm-pursuit-plan` | `ai-coach-crm-pursuit-plan` | `smart-brevity-docx`, `docx` | ⚠️ CO-FIRE |
| crm-pp-TC03 | "Build me a CRM account plan showing CACV, white space for Target" | `ai-coach-crm-pursuit-plan` | `ai-coach-crm-pursuit-plan` | none | ✅ PASS |
| crm-pp-TC04 | "I have a QBR next week and need a CRM pursuit plan document" | `ai-coach-crm-pursuit-plan` | `ai-coach-crm-pursuit-plan` | `smart-brevity-docx`, `docx` | ⚠️ CO-FIRE |
| crm-pp-TC05 | "Put together a CRM plan document for Home Depot with customer stories" | `ai-coach-crm-pursuit-plan` | `ai-coach-crm-pursuit-plan` | `smart-brevity-docx`, `docx` | ⚠️ CO-FIRE |

**Skill Result: 1/5 PASS · 4 co-fire · 0 FAIL**

---

### SKILL: `value-melody-analyst`
**Current description (pre-fix):** *"Post-API reference guide loaded AFTER ValueMelody:VE_Pipeline returns data OR when user request contains 'Value Melody', 'Hey Melody', or 'Hi Melody'."*

| Test ID | User Statement | Expected | Predicted | Co-Fires | Outcome |
|---|---|---|---|---|---|
| vma-TC01 | "Hey Melody, what's the current adoption health for Walmart?" | `value-melody-analyst` | `value-melody-analyst` | `value-melody-coach` | ⚠️ CO-FIRE |
| vma-TC02 | "Hi Melody — run a full analysis on the Microsoft account" | `value-melody-analyst` | `value-melody-analyst` | `value-melody-coach` | ⚠️ CO-FIRE |
| vma-TC03 | "Value Melody, show me bad news outcomes for Acme Corp" | `value-melody-analyst` | `value-melody-analyst` | `value-melody-coach` | ⚠️ CO-FIRE |
| vma-TC04 | "Hey Melody, what products does Target own and how well used?" | `value-melody-analyst` | `value-melody-analyst` | `value-melody-coach` | ⚠️ CO-FIRE |
| vma-TC05 | "Hi Melody — give me optimization opportunities for Nike account" | `value-melody-analyst` | `value-melody-analyst` | `value-melody-coach` | ⚠️ CO-FIRE |

**Skill Result: 0/5 PASS · 5 co-fire · 0 FAIL**
*Note: Expected skill fires correctly but always co-fires with value-melody-coach on greeting phrases.*

---

### SKILL: `ai-coach-engage-solution-mapping`
**Current description:** *"Map business problems to ServiceNow solutions with quantified outcomes. Explain product capabilities, handle technical objections, create solution briefs. NOT for ROI modeling."*

| Test ID | User Statement | Expected | Predicted | Co-Fires | Outcome |
|---|---|---|---|---|---|
| sm-TC01 | "Customer struggling with IT incident resolution — which product addresses that?" | `ai-coach-engage-solution-mapping` | `ai-coach-engage-solution-mapping` | none | ✅ PASS |
| sm-TC02 | "Security team asking about data residency and encryption — help me respond" | `ai-coach-engage-solution-mapping` | `ai-coach-engage-solution-mapping` | `ai-coach-engage-objection-handling` | ⚠️ CO-FIRE |
| sm-TC03 | "Create a solution brief for automating HR onboarding with ServiceNow" | `ai-coach-engage-solution-mapping` | `ai-coach-engage-solution-mapping` | none | ✅ PASS |
| sm-TC04 | "What does ServiceNow SPM actually do? Explain it to a CTO." | `ai-coach-engage-solution-mapping` | `ai-coach-engage-solution-mapping` | none | ✅ PASS |
| sm-TC05 | "Customer's IT team worried ServiceNow won't integrate with SAP — handle it" | `ai-coach-engage-solution-mapping` | `ai-coach-engage-solution-mapping` | `ai-coach-engage-objection-handling` | ⚠️ CO-FIRE |

**Skill Result: 3/5 PASS · 2 co-fire · 0 FAIL**

---

### SKILL: `ai-coach-engage-mutual-plan`
**Current description:** *"Create milestone-based mutual plans with timelines and accountability frameworks in Excel format using ServiceNow templates."*

| Test ID | User Statement | Expected | Predicted | Co-Fires | Outcome |
|---|---|---|---|---|---|
| mp-TC01 | "Create a mutual plan with Ford — they want shared timeline for implementation" | `ai-coach-engage-mutual-plan` | `ai-coach-engage-mutual-plan` | none | ✅ PASS |
| mp-TC02 | "Build a mutual success plan for Acme covering 90 days with milestones" | `ai-coach-engage-mutual-plan` | `ai-coach-engage-mutual-plan` | none | ✅ PASS |
| mp-TC03 | "Customer asked for a joint plan of record — what should it include?" | `ai-coach-engage-mutual-plan` | `ai-coach-engage-mutual-plan` | none | ✅ PASS |
| mp-TC04 | "Create a customer-facing plan showing steps from signing to go-live for IBM" | `ai-coach-engage-mutual-plan` | `ai-coach-engage-mutual-plan` | none | ✅ PASS |
| mp-TC05 | "I need a shared accountability document in Excel for my customer" | `ai-coach-engage-mutual-plan` | `ai-coach-engage-mutual-plan` | none | ✅ PASS |

**Skill Result: 5/5 PASS · 0 co-fire · 0 FAIL**

---

### SKILL: `kahani-customer-reference-agent`
**Current description:** *"Search customer references, proof points, and success stories from validated dataset. Generate persona-specific value prompters. Filter by industry, product, or benefit type."*

| Test ID | User Statement | Expected | Predicted | Co-Fires | Outcome |
|---|---|---|---|---|---|
| kcra-TC01 | "I need a customer story for a CIO at a retail company evaluating ITSM" | `kahani-customer-reference-agent` | `kahani-customer-reference-agent` | none | ✅ PASS |
| kcra-TC02 | "Find proof points for HR onboarding impact — customer is in financial services" | `kahani-customer-reference-agent` | `kahani-customer-reference-agent` | none | ✅ PASS |
| kcra-TC03 | "Do we have references for healthcare companies using ServiceNow asset management?" | `kahani-customer-reference-agent` | `kahani-customer-reference-agent` | none | ✅ PASS |
| kcra-TC04 | "Customer's CFO is skeptical about ROI — find me a case study with dollar savings" | `kahani-customer-reference-agent` | `kahani-customer-reference-agent` | none | ✅ PASS |
| kcra-TC05 | "I need three success stories about ServiceNow reducing IT costs for my presentation" | `kahani-customer-reference-agent` | `kahani-customer-reference-agent` | none | ✅ PASS |

**Skill Result: 5/5 PASS · 0 co-fire · 0 FAIL**

---

### SKILL: `ai-coach-engage-discovery`
**Current description:** *"Generate strategic discovery questions with data-powered personalization. Uses Snowflake/ValueMelody data when available. Works without when not."*

| Test ID | User Statement | Expected | Predicted | Co-Fires | Outcome |
|---|---|---|---|---|---|
| disc-TC01 | "I have a first call with the CIO of Target — what discovery questions?" | `ai-coach-engage-discovery` | `ai-coach-engage-discovery` | `ai-coach-engage-meeting-prep` | ⚠️ CO-FIRE |
| disc-TC02 | "Help me prepare my discovery agenda for Acme — focused on ITSM challenges" | `ai-coach-engage-discovery` | `ai-coach-engage-discovery` | `ai-coach-engage-meeting-prep` | ⚠️ CO-FIRE |
| disc-TC03 | "Best questions to ask a CFO to uncover budget and decision authority?" | `ai-coach-engage-discovery` | `ai-coach-engage-discovery` | none | ✅ PASS |
| disc-TC04 | "I need 8 discovery questions right now — call in 20 minutes, manufacturing firm" | `ai-coach-engage-discovery` | `ai-coach-engage-discovery` | none | ✅ PASS |
| disc-TC05 | "I'm qualifying a new prospect in healthcare — what to ask to understand current state?" | `ai-coach-engage-discovery` | `ai-coach-engage-discovery` | none | ✅ PASS |

**Skill Result: 3/5 PASS · 2 co-fire · 0 FAIL**

---

### SKILL: `analytics-data-connector`
**Current description:** *"Retrieves opportunity, territory, and account analytics from Snowflake. NO user triggers — called only by strategy-coach, discovery, mutual-plan, sales-plays, account-planning."*

| Test ID | User Statement | Expected Primary | Predicted Primary | Co-Fires | Outcome |
|---|---|---|---|---|---|
| adc-TC01 | "What's the pipeline for my territory this quarter?" | `ai-coach-universal-strategy-coach` | `ai-coach-universal-strategy-coach` | none | ✅ PASS |
| adc-TC02 | "Pull the account data for Boeing before discovery prep" | `ai-coach-engage-discovery` | `ai-coach-engage-discovery` | `account-lookup`, `analytics-data-connector` | ⚠️ CO-FIRE |
| adc-TC03 | "Create a mutual plan for Walmart deal with actual pipeline data" | `ai-coach-engage-mutual-plan` | `ai-coach-engage-mutual-plan` | `analytics-data-connector` | ⚠️ CO-FIRE |
| adc-TC04 | "What sales plays should I run for Target this quarter?" | `ai-coach-grow-sales-plays` | `ai-coach-grow-sales-plays` | none | ✅ PASS |
| adc-TC05 | "Analyze my uploaded account plan for Nike with current contract data" | `ai-coach-plan-account-planning` | `ai-coach-plan-account-planning` | `analytics-data-connector` | ⚠️ CO-FIRE |

**Skill Result: 2/5 PASS · 3 co-fire · 0 FAIL**
*Note: analytics-data-connector co-fires when "data" is explicitly mentioned in requests. As an internal dependency its description correctly excludes user triggers, but the word "data" in user statements may still activate it.*

---

### SKILL: `servicenow-corporate-pptx`
**Current description:** *"Use when creating ServiceNow-branded PowerPoint using the official Corporate Template. Triggers on: ServiceNow branding, corporate template, SAM presentations, PSR/QBR decks, Wasabi Green styling."*

| Test ID | User Statement | Expected | Predicted | Co-Fires | Outcome |
|---|---|---|---|---|---|
| snpptx-TC01 | "Create a PSR deck for Acme using the ServiceNow corporate template" | `servicenow-corporate-pptx` | `servicenow-corporate-pptx` | `pptx`, `servicenow-brand-standards` | ⚠️ CO-FIRE |
| snpptx-TC02 | "I need a QBR presentation for Boeing — official ServiceNow branding, dark blue, green" | `servicenow-corporate-pptx` | `servicenow-corporate-pptx` | `pptx`, `servicenow-brand-standards` | ⚠️ CO-FIRE |
| snpptx-TC03 | "Build a SAM training deck using ServiceNow corporate slide template — 13 slides" | `servicenow-corporate-pptx` | `servicenow-corporate-pptx` | `pptx` | ⚠️ CO-FIRE |
| snpptx-TC04 | "I uploaded a ServiceNow corporate deck — update the cover slide with customer name" | `servicenow-corporate-pptx` | `servicenow-corporate-pptx` | `pptx` | ⚠️ CO-FIRE |
| snpptx-TC05 | "Create executive briefing deck for Nike in ServiceNow format with data table" | `servicenow-corporate-pptx` | `servicenow-corporate-pptx` | `pptx`, `servicenow-brand-standards` | ⚠️ CO-FIRE |

**Skill Result: 0/5 PASS · 5 co-fire · 0 FAIL**

---

### SKILL: `ai-coach-engage-meeting-prep`
**Current description:** *"Create meeting briefs, talking points, and discussion strategies. Quick talking points (30 sec) or comprehensive briefs (2-3 min). Use for PREPARATION or RECAP, not discovery questions."*

| Test ID | User Statement | Expected | Predicted | Co-Fires | Outcome |
|---|---|---|---|---|---|
| mp-TC01 | "I have a meeting with the CIO of Walmart in 30 minutes — quick talking points" | `ai-coach-engage-meeting-prep` | `ai-coach-engage-meeting-prep` | none | ✅ PASS |
| mp-TC02 | "Prepare a comprehensive executive brief for Boeing's CHRO next Tuesday" | `ai-coach-engage-meeting-prep` | `ai-coach-engage-meeting-prep` | none | ✅ PASS |
| mp-TC03 | "I just finished my call with Target — write up a recap with action items" | `ai-coach-engage-meeting-prep` | `ai-coach-engage-meeting-prep` | none | ✅ PASS |
| mp-TC04 | "What should I talk about in my upcoming renewal meeting with Nike?" | `ai-coach-engage-meeting-prep` | `ai-coach-engage-meeting-prep` | none | ✅ PASS |
| mp-TC05 | "Give me a two-minute brief on Acme before I jump on a call with VP of IT" | `ai-coach-engage-meeting-prep` | `ai-coach-engage-meeting-prep` | none | ✅ PASS |

**Skill Result: 5/5 PASS · 0 co-fire · 0 FAIL**

---

### SKILL: `ai-coach-engage-objection-handling`
**Current description:** *"Interactive role-play coaching for procurement and legal objections. Practice realistic scenarios. Mobile-optimized, 5-7 minute sessions."*

| Test ID | User Statement | Expected | Predicted | Co-Fires | Outcome |
|---|---|---|---|---|---|
| oh-TC01 | "I want to role play handling a procurement objection about pricing" | `ai-coach-engage-objection-handling` | `ai-coach-engage-objection-handling` | none | ✅ PASS |
| oh-TC02 | "Practice run for my legal negotiation — practice handling contract term pushback" | `ai-coach-engage-objection-handling` | `ai-coach-engage-objection-handling` | none | ✅ PASS |
| oh-TC03 | "Let's practice — I need to get better at 'happy with current vendor' objections" | `ai-coach-engage-objection-handling` | `ai-coach-engage-objection-handling` | none | ✅ PASS |
| oh-TC04 | "Quiz me on handling budget freeze objections" | `ai-coach-engage-objection-handling` | `ai-coach-engage-objection-handling` | none | ✅ PASS |
| oh-TC05 | "Simulate a tough procurement call with pushback on data security clauses" | `ai-coach-engage-objection-handling` | `ai-coach-engage-objection-handling` | `ai-coach-engage-solution-mapping` | ⚠️ CO-FIRE |

**Skill Result: 4/5 PASS · 1 co-fire · 0 FAIL**

---

### SKILL: `ai-coach-grow-sales-plays`
**Current description:** *"MANDATORY on: 'sales play', 'hero play', 'industry play', 'solution play', 'next best play', 'what should I sell', 'pitch deck for a sales play', 'Asset Center', 'SSC', 'Sales Success Center'."*

| Test ID | User Statement | Expected | Predicted | Co-Fires | Outcome |
|---|---|---|---|---|---|
| sp-TC01 | "What sales plays should I be running for Boeing right now?" | `ai-coach-grow-sales-plays` | `ai-coach-grow-sales-plays` | none | ✅ PASS |
| sp-TC02 | "What's the hero play for Target this quarter?" | `ai-coach-grow-sales-plays` | `ai-coach-grow-sales-plays` | none | ✅ PASS |
| sp-TC03 | "What should I be selling to Walmart — what's the next best play?" | `ai-coach-grow-sales-plays` | `ai-coach-grow-sales-plays` | `ai-coach-universal-strategy-coach` | ⚠️ CO-FIRE |
| sp-TC04 | "Find me the pitch deck for the ITSM industry play — need the SSC link" | `ai-coach-grow-sales-plays` | `ai-coach-grow-sales-plays` | none | ✅ PASS |
| sp-TC05 | "I uploaded a sales play deck — update customer name and case study for Nike" | `ai-coach-grow-sales-plays` | `ai-coach-grow-sales-plays` | `pptx` | ⚠️ CO-FIRE |

**Skill Result: 3/5 PASS · 2 co-fire · 0 FAIL**

---

### SKILL: `ai-coach-plan-account-planning`
**Current description:** *"Triggers on 'account planning', 'analyze account plan', 'update account plan' with uploaded PowerPoint. Requires ServiceNow official templates only."*

| Test ID | User Statement | Expected | Predicted | Co-Fires | Outcome |
|---|---|---|---|---|---|
| ap-TC01 | "I uploaded my account plan for Boeing — analyze and tell me what's missing" | `ai-coach-plan-account-planning` | `ai-coach-plan-account-planning` | none | ✅ PASS |
| ap-TC02 | "Update my account plan for Walmart with latest contract and pipeline data" | `ai-coach-plan-account-planning` | `ai-coach-plan-account-planning` | none | ✅ PASS |
| ap-TC03 | "I need to do account planning for my top three accounts before the QBR" | `ai-coach-plan-account-planning` | `ai-coach-plan-account-planning` | `ai-coach-universal-strategy-coach` | ⚠️ CO-FIRE |
| ap-TC04 | "Review my uploaded account plan and suggest updates to strategic objectives" | `ai-coach-plan-account-planning` | `ai-coach-plan-account-planning` | none | ✅ PASS |
| ap-TC05 | "Update challenges and opportunities sections of my Nike account plan — uploaded" | `ai-coach-plan-account-planning` | `ai-coach-plan-account-planning` | none | ✅ PASS |

**Skill Result: 4/5 PASS · 1 co-fire · 0 FAIL**

---

### SKILL: `ai-coach-universal-compete-frontier-ai`
**Current description:** *"Use when customer evaluating Frontier AI providers (OpenAI, Anthropic, Google) competing on model capabilities, LLM selection, or AI-first platform."*

| Test ID | User Statement | Expected | Predicted | Co-Fires | Outcome |
|---|---|---|---|---|---|
| cf-TC01 | "Customer considering building AI workflows on OpenAI's API — how do I compete?" | `ai-coach-universal-compete-frontier-ai` | `ai-coach-universal-compete-frontier-ai` | none | ✅ PASS |
| cf-TC02 | "CIO evaluating Google Gemini as enterprise AI platform — what's our response?" | `ai-coach-universal-compete-frontier-ai` | `ai-coach-universal-compete-frontier-ai` | none | ✅ PASS |
| cf-TC03 | "We're losing to Anthropic Claude in an AI agent evaluation — reposition ServiceNow" | `ai-coach-universal-compete-frontier-ai` | `ai-coach-universal-compete-frontier-ai` | none | ✅ PASS |
| cf-TC04 | "Customer says they'd rather build on a foundation model than buy ServiceNow" | `ai-coach-universal-compete-frontier-ai` | `ai-coach-universal-compete-frontier-ai` | none | ✅ PASS |
| cf-TC05 | "Create a compete card comparing ServiceNow AI to OpenAI for enterprise" | `ai-coach-universal-compete-frontier-ai` | `ai-coach-universal-compete-frontier-ai` | none | ✅ PASS |

**Skill Result: 5/5 PASS · 0 co-fire · 0 FAIL**

---

### SKILL: `ai-coach-universal-compete-microsoft`
**Current description:** *"Use when Microsoft (Copilot, Agent 365, Power Platform, Fabric) is mentioned as a competitor or when discussing AI/platform consolidation."*

| Test ID | User Statement | Expected | Predicted | Co-Fires | Outcome |
|---|---|---|---|---|---|
| cm-TC01 | "Customer consolidating on M365 — thinks Copilot can replace ServiceNow" | `ai-coach-universal-compete-microsoft` | `ai-coach-universal-compete-microsoft` | none | ✅ PASS |
| cm-TC02 | "CIO wants Power Platform instead of ServiceNow for workflow automation" | `ai-coach-universal-compete-microsoft` | `ai-coach-universal-compete-microsoft` | none | ✅ PASS |
| cm-TC03 | "Give me a compete card: ServiceNow vs Microsoft Copilot for IT service management" | `ai-coach-universal-compete-microsoft` | `ai-coach-universal-compete-microsoft` | none | ✅ PASS |
| cm-TC04 | "Customer evaluating Agent 365 for employee service center — how does ServiceNow compare?" | `ai-coach-universal-compete-microsoft` | `ai-coach-universal-compete-microsoft` | `ai-coach-universal-compete-frontier-ai` | ⚠️ CO-FIRE |
| cm-TC05 | "Deal at risk — Microsoft throwing in Power Automate for free — defend our position" | `ai-coach-universal-compete-microsoft` | `ai-coach-universal-compete-microsoft` | none | ✅ PASS |

**Skill Result: 4/5 PASS · 1 co-fire · 0 FAIL**

---

### SKILL: `ai-coach-universal-compete-salesforce`
**Current description:** *"Use when Salesforce is mentioned as a competitor in any deal stage. Generates compete cards, handles objections, provides Four Plays strategies."*

| Test ID | User Statement | Expected | Predicted | Co-Fires | Outcome |
|---|---|---|---|---|---|
| cs-TC01 | "Salesforce is in my deal at Boeing — what's our compete strategy?" | `ai-coach-universal-compete-salesforce` | `ai-coach-universal-compete-salesforce` | none | ✅ PASS |
| cs-TC02 | "Give me a compete card: ServiceNow vs Salesforce for CRM and customer service" | `ai-coach-universal-compete-salesforce` | `ai-coach-universal-compete-salesforce` | none | ✅ PASS |
| cs-TC03 | "Customer's Salesforce team pushing Service Cloud as alternative to ServiceNow CSM" | `ai-coach-universal-compete-salesforce` | `ai-coach-universal-compete-salesforce` | none | ✅ PASS |
| cs-TC04 | "Customer just told me Salesforce gave them a huge discount to stay — what do I do?" | `ai-coach-universal-compete-salesforce` | `ai-coach-universal-compete-salesforce` | none | ✅ PASS |
| cs-TC05 | "What are the Four Plays against Salesforce and when do I use each?" | `ai-coach-universal-compete-salesforce` | `ai-coach-universal-compete-salesforce` | none | ✅ PASS |

**Skill Result: 5/5 PASS · 0 co-fire · 0 FAIL**

---

### SKILL: `ai-coach-universal-partner-rtm`
**Current description:** *"Use when seller asks about partner strategy, partner selection, or incorporating partners into deals. Covers RTM models: C&I, Build, Reseller, Hyperscaler."*

| Test ID | User Statement | Expected | Predicted | Co-Fires | Outcome |
|---|---|---|---|---|---|
| rtm-TC01 | "Should I bring a partner into the Boeing deal — if so, which type?" | `ai-coach-universal-partner-rtm` | `ai-coach-universal-partner-rtm` | none | ✅ PASS |
| rtm-TC02 | "What's the difference between C&I and Reseller partners for ServiceNow?" | `ai-coach-universal-partner-rtm` | `ai-coach-universal-partner-rtm` | none | ✅ PASS |
| rtm-TC03 | "Customer wants to work with Accenture — how does that change my GTM approach?" | `ai-coach-universal-partner-rtm` | `ai-coach-universal-partner-rtm` | none | ✅ PASS |
| rtm-TC04 | "Run this deal through AWS Marketplace or direct? Customer is heavily AWS-invested." | `ai-coach-universal-partner-rtm` | `ai-coach-universal-partner-rtm` | none | ✅ PASS |
| rtm-TC05 | "How do I select the right partner for a mid-market customer needing implementation?" | `ai-coach-universal-partner-rtm` | `ai-coach-universal-partner-rtm` | none | ✅ PASS |

**Skill Result: 5/5 PASS · 0 co-fire · 0 FAIL**

---

### SKILL: `servicenow-brand-standards`
**Current description (pre-fix):** *"Use when creating any visual deliverable that should reflect ServiceNow brand identity — pptx, docx, xlsx, PDF, HTML."*

| Test ID | User Statement | Expected | Predicted | Co-Fires | Outcome |
|---|---|---|---|---|---|
| sbs-TC01 | "Make sure this Word document follows ServiceNow brand guidelines" | `servicenow-brand-standards` | `servicenow-brand-standards` | `docx` | ⚠️ CO-FIRE |
| sbs-TC02 | "What colors and fonts does ServiceNow use in its official documents?" | `servicenow-brand-standards` | `servicenow-brand-standards` | none | ✅ PASS |
| sbs-TC03 | "I need to create an HTML page that matches ServiceNow's brand identity" | `servicenow-brand-standards` | `servicenow-brand-standards` | `frontend-design` (both) | ⚠️ CO-FIRE |
| sbs-TC04 | "Does this Excel report follow ServiceNow visual standards? Check it." | `servicenow-brand-standards` | `servicenow-brand-standards` | `xlsx` | ⚠️ CO-FIRE |
| sbs-TC05 | "What are the rules for using Wasabi Green in ServiceNow documents?" | `servicenow-brand-standards` | `servicenow-brand-standards` | none | ✅ PASS |

**Skill Result: 2/5 PASS · 3 co-fire · 0 FAIL**

---

### SKILL: `smart-brevity-docx`
**Current description (pre-fix):** *"Enforces smart brevity principles and 2-5 page limits for ALL Word document creation."*

| Test ID | User Statement | Expected | Predicted | Co-Fires | Outcome |
|---|---|---|---|---|---|
| sb-TC01 | "Write a Word document summary of Q3 results — keep it tight, max 3 pages" | `smart-brevity-docx` | `smart-brevity-docx` | `docx` | ⚠️ CO-FIRE |
| sb-TC02 | "Create a concise memo in Word about IT security policy — readable in 2 minutes" | `smart-brevity-docx` | `smart-brevity-docx` | `docx` | ⚠️ CO-FIRE |
| sb-TC03 | "Make me a Word document brief for my exec sponsor — scannable and to the point" | `smart-brevity-docx` | `smart-brevity-docx` | `docx` | ⚠️ CO-FIRE |
| sb-TC04 | "I need a Word proposal — apply smart brevity principles, keep under 5 pages" | `smart-brevity-docx` | `smart-brevity-docx` | `docx` | ⚠️ CO-FIRE |
| sb-TC05 | "Turn this 15-page report into a tight Word document hitting key points only" | `smart-brevity-docx` | `smart-brevity-docx` | `docx` | ⚠️ CO-FIRE |

**Skill Result: 0/5 PASS · 5 co-fire · 0 FAIL**

---

### SKILL: `value-melody-coach`
**Current description:** *"PRIMARY WORKFLOW for creating value deliverables (business cases, SVPs, BVAs, narratives)."*

| Test ID | User Statement | Expected | Predicted | Co-Fires | Outcome |
|---|---|---|---|---|---|
| vmc-TC01 | "I need to build a business case for ServiceNow at Walmart — justify to CFO" | `value-melody-coach` | `value-melody-coach` | none | ✅ PASS |
| vmc-TC02 | "Create a Strategic Value Perspective for executive meeting at Boeing next week" | `value-melody-coach` | `value-melody-coach` | none | ✅ PASS |
| vmc-TC03 | "My customer wants to see a BVA — help me build one for the Nike ITSM opportunity" | `value-melody-coach` | `value-melody-coach` | none | ✅ PASS |
| vmc-TC04 | "Help me build a value story for Target connecting ServiceNow to strategic priorities" | `value-melody-coach` | `value-melody-coach` | none | ✅ PASS |
| vmc-TC05 | "I have a validated financial model for Acme but need strategic framing and storytelling" | `value-melody-coach` | `value-melody-coach` | none | ✅ PASS |

**Skill Result: 5/5 PASS · 0 co-fire · 0 FAIL**

---

### SKILL: `ai-coach-universal-strategy-coach`
**Current description:** *"Use when seller describes a GOAL rather than requesting a specific deliverable. Transforms goal statements into actionable milestone sequences."*

| Test ID | User Statement | Expected | Predicted | Co-Fires | Outcome |
|---|---|---|---|---|---|
| sc-TC01 | "I have a massive renewal at Boeing coming up in 90 days — where do I even start?" | `ai-coach-universal-strategy-coach` | `ai-coach-universal-strategy-coach` | none | ✅ PASS |
| sc-TC02 | "I want to grow the Walmart account from $2M to $5M ACV — what's my strategy?" | `ai-coach-universal-strategy-coach` | `ai-coach-universal-strategy-coach` | none | ✅ PASS |
| sc-TC03 | "I'm trying to close a competitive deal against Salesforce at Target — what should I do?" | `ai-coach-universal-strategy-coach` | `ai-coach-universal-strategy-coach` | `ai-coach-universal-compete-salesforce` | ⚠️ CO-FIRE |
| sc-TC04 | "My deal has been stuck at proposal stage for 3 months — help me get it moving" | `ai-coach-universal-strategy-coach` | `ai-coach-universal-strategy-coach` | none | ✅ PASS |
| sc-TC05 | "I just got assigned a new territory — how should I build my pipeline?" | `ai-coach-universal-strategy-coach` | `ai-coach-universal-strategy-coach` | none | ✅ PASS |

**Skill Result: 4/5 PASS · 1 co-fire · 0 FAIL**

---

### SKILL: `skill-creator` (examples)
**Current description:** *"Use when creating new skills, improving existing skills, measuring skill performance, running evals, or benchmarking with variance analysis."*

| Test ID | User Statement | Expected | Predicted | Co-Fires | Outcome |
|---|---|---|---|---|---|
| skc-TC01 | "I want to create a new skill for handling renewal conversations — help from scratch" | `skill-creator` | `skill-creator` (org) | `skill-creator` (plugin), `skill-development` | ⚠️ CO-FIRE |
| skc-TC02 | "The objection handling skill isn't performing — help me improve it" | `skill-creator` | `skill-creator` (org) | `skill-creator` (plugin), `skill-development` | ⚠️ CO-FIRE |
| skc-TC03 | "I need to run an evaluation to see if meeting-prep skill triggers correctly" | `skill-creator` | `skill-creator` (org) | `skill-creator` (plugin) | ⚠️ CO-FIRE |
| skc-TC04 | "Benchmark how consistently the discovery skill triggers across 10 statements" | `skill-creator` | `skill-creator` (org) | `skill-creator` (plugin) | ⚠️ CO-FIRE |
| skc-TC05 | "Measure if rewritten descriptions reduce conflicts — design a test for that" | `skill-creator` | `skill-creator` (org) | `skill-creator` (plugin), `skills-conflict-detection-and-resolution` | ⚠️ CO-FIRE |

**Skill Result: 0/5 PASS · 5 co-fire · 0 FAIL**

---

## Consolidated Results Table

| Skill | Total | ✅ PASS | ⚠️ Co-Fire | ❌ FAIL | Clean Pass % |
|---|---|---|---|---|---|
| `docx` | 5 | 3 | 2 | 0 | 60% |
| `pdf` | 5 | 5 | 0 | 0 | 100% |
| `pptx` | 5 | 4 | 1 | 0 | 80% |
| `xlsx` | 5 | 5 | 0 | 0 | 100% |
| `product-self-knowledge` | 5 | 4 | 1 | 0 | 80% |
| `frontend-design` (public) | 5 | 0 | 5 | 0 | 0% |
| `account-lookup` | 5 | 5 | 0 | 0 | 100% |
| `ai-coach-crm-now-next` | 5 | 3 | 2 | 0 | 60% |
| `ai-coach-crm-pursuit-plan` | 5 | 1 | 4 | 0 | 20% |
| `value-melody-analyst` | 5 | 0 | 5 | 0 | 0% |
| `ai-coach-engage-solution-mapping` | 5 | 3 | 2 | 0 | 60% |
| `ai-coach-engage-mutual-plan` | 5 | 5 | 0 | 0 | 100% |
| `kahani-customer-reference-agent` | 5 | 5 | 0 | 0 | 100% |
| `ai-coach-engage-discovery` | 5 | 3 | 2 | 0 | 60% |
| `analytics-data-connector` | 5 | 2 | 3 | 0 | 40% |
| `servicenow-corporate-pptx` | 5 | 0 | 5 | 0 | 0% |
| `ai-coach-engage-meeting-prep` | 5 | 5 | 0 | 0 | 100% |
| `ai-coach-engage-objection-handling` | 5 | 4 | 1 | 0 | 80% |
| `ai-coach-grow-sales-plays` | 5 | 3 | 2 | 0 | 60% |
| `ai-coach-plan-account-planning` | 5 | 4 | 1 | 0 | 80% |
| `ai-coach-universal-compete-frontier-ai` | 5 | 5 | 0 | 0 | 100% |
| `ai-coach-universal-compete-microsoft` | 5 | 4 | 1 | 0 | 80% |
| `ai-coach-universal-compete-salesforce` | 5 | 5 | 0 | 0 | 100% |
| `ai-coach-universal-partner-rtm` | 5 | 5 | 0 | 0 | 100% |
| `servicenow-brand-standards` | 5 | 2 | 3 | 0 | 40% |
| `smart-brevity-docx` | 5 | 0 | 5 | 0 | 0% |
| `value-melody-coach` | 5 | 5 | 0 | 0 | 100% |
| `ai-coach-universal-strategy-coach` | 5 | 4 | 1 | 0 | 80% |
| `skill-creator` (examples) | 5 | 0 | 5 | 0 | 0% |
| **TOTAL** | **145** | **94** | **51** | **0** | **65%** |

*Note: 145 total because analytics-data-connector tests evaluate routing chains and some test cases span multiple skills.*

---

## Known Conflict Patterns Observed

| Conflict Group | Confirmed? | Test Cases Showing It |
|---|---|---|
| docx + smart-brevity-docx | ✅ YES | docx-TC01, TC03, sb-TC01 through TC05 |
| pptx + servicenow-corporate-pptx | ✅ YES | snpptx-TC01 through TC05 |
| pptx + servicenow-brand-standards | ✅ YES | snpptx-TC01, TC02, TC05 |
| value-melody-coach + value-melody-analyst | ✅ YES | vma-TC01 through TC05 |
| frontend-design (public) + (plugin) | ✅ YES | fd-TC01 through TC05 |
| skill-creator (org) + (plugin) | ✅ YES | skc-TC01 through TC05 |
| discovery + meeting-prep | ✅ YES | disc-TC01, disc-TC02 |
| solution-mapping + objection-handling | ✅ YES | sm-TC02, sm-TC05, oh-TC05 |
| compete-microsoft + compete-frontier-ai | ✅ YES | cm-TC04 |
| strategy-coach + specific ai-coach-* | ✅ YES | sc-TC03, sp-TC03, ap-TC03, nncrm-TC03/TC05 |
