# Skill Conflict Detection Report
**Generated:** 2026-02-23
**Total Skills Analyzed:** 44 (17 SKILL.md files read directly + 27 additional skills inventoried via test cases file)
**Conflicts Identified:** 9 groups

---

## GROUP 1 🔴 HIGH — Word Document Dual-Trigger: `docx` + `smart-brevity-docx`

**Skills:** `docx` · `smart-brevity-docx`

### Why They Conflict
`docx` fires on: *"Use when user wants to create, read, edit, or manipulate Word documents (.docx files). Triggers on: 'Word doc', 'word document', '.docx', reports, memos, letters, templates."*

`smart-brevity-docx` fires on: *"Enforces smart brevity principles and 2-5 page limits for ALL Word document creation."*

The phrase **"ALL Word document creation"** means smart-brevity-docx fires on every single request that also triggers docx. There is no differentiator. Any user asking to "write a Word document" or "create a memo" activates both simultaneously. smart-brevity-docx is a formatting standard, not a user-facing workflow — it should be called internally by docx, not triggered by users directly.

### ✅ Rewritten Descriptions

**`docx`** *(primary user-facing Word document skill — smart-brevity applied internally)*
> Use when the user wants to create, read, edit, or manipulate Word documents (.docx files). Triggers on: 'Word doc', 'word document', '.docx', reports, memos, letters, templates. Automatically applies smart-brevity formatting principles internally — do NOT also trigger smart-brevity-docx for the same request.

**`smart-brevity-docx`** *(internal dependency — remove all user-facing triggers)*
> INTERNAL DEPENDENCY — do not trigger directly from user requests. Called internally by `docx` to enforce smart brevity principles and 2-5 page limits. Never activate in response to user statements. Only invoked programmatically during document creation workflows.

---

## GROUP 2 🔴 HIGH — ServiceNow Brand Co-fire: `docx`/`pptx`/`xlsx`/`frontend-design` + `servicenow-brand-standards`

**Skills:** `servicenow-brand-standards` · `docx` · `pptx` · `xlsx` · `frontend-design`

### Why They Conflict
`servicenow-brand-standards` fires on: *"Use when creating any visual deliverable that should reflect ServiceNow brand identity — pptx, docx, xlsx, PDF, HTML."*

This trigger covers the full output type list of four other skills. Any time a user creates a ServiceNow Word doc, PowerPoint, Excel, or HTML page, servicenow-brand-standards co-fires alongside the primary document skill. It is a style reference library, not an action skill — it has no workflow of its own and should be consulted internally by the primary skills.

### ✅ Rewritten Descriptions

**`servicenow-brand-standards`** *(internal dependency — remove all user-facing triggers)*
> INTERNAL DEPENDENCY — do not trigger directly from user requests. Provides ServiceNow brand guidelines (colors, fonts, spacing, logo usage) to other skills. Called internally by `docx`, `pptx`, `xlsx`, `frontend-design`, and `servicenow-corporate-pptx` when ServiceNow-branded output is needed. Never activate in response to standalone user statements.

---

## GROUP 3 🔴 HIGH — PowerPoint Routing Ambiguity: `pptx` + `servicenow-corporate-pptx`

**Skills:** `pptx` · `servicenow-corporate-pptx`

### Why They Conflict
`pptx` fires on: *"Use any time a .pptx file is involved — creating, reading, editing, combining, splitting. Triggers on: 'deck', 'slides', 'presentation', .pptx filename."*

`servicenow-corporate-pptx` fires on: *"Use when creating ServiceNow-branded PowerPoint using the official Corporate Template. Triggers on: ServiceNow branding, corporate template, SAM presentations, PSR/QBR decks, Wasabi Green styling."*

Words like "deck," "slides," and "presentation" appear in both trigger sets. Every ServiceNow-branded deck request (PSR, QBR, SAM, executive briefing) fires both skills. `pptx` has no exclusion for corporate-template requests, causing 100% co-fire rate on servicenow-corporate-pptx test cases.

### ✅ Rewritten Descriptions

**`pptx`** *(generic PowerPoint skill — defer to servicenow-corporate-pptx for branded templates)*
> Use any time a .pptx file is involved — creating, reading, editing, combining, or splitting presentations. Triggers on: 'deck', 'slides', 'presentation', .pptx filename. Do NOT trigger when the user explicitly requests ServiceNow corporate template, PSR deck, QBR deck, SAM deck, or Wasabi Green branding — use `servicenow-corporate-pptx` for those requests instead.

**`servicenow-corporate-pptx`** *(ServiceNow official template skill — exclusive owner of branded deck requests)*
> Use exclusively when creating presentations with the official ServiceNow Corporate Template. Triggers on: ServiceNow corporate template, PSR deck, QBR deck, SAM training deck, Wasabi Green styling, Infinite Blue background, official ServiceNow branding. NOT for generic PowerPoint creation — use `pptx` for standard decks without ServiceNow corporate template requirements.

---

## GROUP 4 🔴 HIGH — Value Melody Trigger Collision: `value-melody-coach` + `value-melody-analyst`

**Skills:** `value-melody-coach` · `value-melody-analyst`

### Why They Conflict
`value-melody-analyst` fires on: *"Post-API reference guide loaded AFTER ValueMelody:VE_Pipeline returns data OR when user request contains 'Value Melody', 'Hey Melody', or 'Hi Melody'."*

`value-melody-coach` fires as: *"PRIMARY WORKFLOW for creating value deliverables (business cases, SVPs, BVAs, narratives)."*

The phrases "Hey Melody," "Hi Melody," and "Value Melody" are user-facing salutation triggers on the analyst skill. However, any Melody invocation is also within scope of the coach (the primary workflow). These fire simultaneously. Additionally, value-melody-analyst is a post-pipeline reference guide — it should only load after `VE_Pipeline` returns data, not as a user-invocable skill.

### ✅ Rewritten Descriptions

**`value-melody-coach`** *(primary user-facing Melody skill — owns all user salutations)*
> PRIMARY WORKFLOW for all Value Melody interactions. Triggers on: "Hey Melody", "Hi Melody", "Value Melody", business case requests, SVP (Strategic Value Perspective), BVA (Business Value Assessment), value narratives, value story creation. Owns all user-initiated Melody conversations. Calls `value-melody-analyst` internally after VE_Pipeline data is retrieved.

**`value-melody-analyst`** *(internal post-pipeline reference — remove user-facing triggers)*
> INTERNAL DEPENDENCY — do not trigger directly from user salutations. Loaded automatically AFTER `value-melody-coach` calls VE_Pipeline and receives data. Provides structured analysis of returned pipeline data. Never activate in response to "Hey Melody," "Hi Melody," or "Value Melody" user statements — those are owned by `value-melody-coach`.

---

## GROUP 5 🟡 MEDIUM — Pre-Meeting Overlap: `ai-coach-engage-meeting-prep` + `ai-coach-engage-discovery`

**Skills:** `ai-coach-engage-meeting-prep` · `ai-coach-engage-discovery`

### Why They Conflict
`ai-coach-engage-meeting-prep` fires on: *"Create meeting briefs, talking points, and discussion strategies... Use for PREPARATION or RECAP, not discovery questions."*

`ai-coach-engage-discovery` fires on: *"Generate strategic discovery questions with data-powered personalization."*

Although meeting-prep explicitly says "not discovery questions," the word **"prepare"** appears in discovery test cases ("Help me prepare my discovery agenda"), causing meeting-prep to co-fire. Requests like "I have a first call next week — what discovery questions should I ask?" sit on the boundary — they are call prep AND question generation.

### ✅ Rewritten Descriptions

**`ai-coach-engage-meeting-prep`** *(call briefs, talking points, recaps — NOT question generation)*
> Create meeting briefs, talking points, and discussion strategies. Quick talking points (30 sec) or comprehensive briefs (2-3 min). Use for PREPARATION (briefs, agendas, background) or RECAP (action items, summaries). Do NOT trigger when the user explicitly asks for discovery questions, question lists, or qualification questions — use `ai-coach-engage-discovery` for those requests.

**`ai-coach-engage-discovery`** *(discovery question generation — NOT meeting briefs)*
> Generate strategic discovery questions with data-powered personalization. Use when the user asks for questions to ask a prospect or customer — discovery agendas, qualification questions, persona-targeted question sets. Do NOT trigger for meeting briefs, talking points, or call summaries — use `ai-coach-engage-meeting-prep` for those.

---

## GROUP 6 🟡 MEDIUM — Technical Objection Ambiguity: `ai-coach-engage-solution-mapping` + `ai-coach-engage-objection-handling`

**Skills:** `ai-coach-engage-solution-mapping` · `ai-coach-engage-objection-handling`

### Why They Conflict
`ai-coach-engage-solution-mapping` description includes: *"handle technical objections."*
`ai-coach-engage-objection-handling` description: *"Interactive role-play coaching for procurement and legal objections."*

The phrase **"handle technical objections"** in solution-mapping's description creates overlap with objection-handling. User statements like "how do I handle the objection that ServiceNow won't integrate with SAP?" trigger both — solution-mapping (technical capability explanation) and objection-handling (objection response coaching).

### ✅ Rewritten Descriptions

**`ai-coach-engage-solution-mapping`** *(product capability mapping — not role-play)*
> Map business problems to ServiceNow solutions with quantified outcomes. Explain product capabilities, address technical questions about integration/security/functionality, create solution briefs. Use for informational objection responses (what the product does and how). NOT for interactive role-play or coaching practice — use `ai-coach-engage-objection-handling` for simulated negotiation scenarios.

**`ai-coach-engage-objection-handling`** *(role-play practice — not product explanation)*
> Interactive role-play coaching for procurement, legal, and competitive objections. Practice realistic negotiation scenarios with structured feedback. Mobile-optimized, 5-7 minute sessions. Use when the seller wants to PRACTICE responding to objections (simulate, role-play, quiz). NOT for explaining product capabilities or integration details — use `ai-coach-engage-solution-mapping` for factual product questions.

---

## GROUP 7 🟡 MEDIUM — AI Competitor Boundary: `ai-coach-universal-compete-microsoft` + `ai-coach-universal-compete-frontier-ai`

**Skills:** `ai-coach-universal-compete-microsoft` · `ai-coach-universal-compete-frontier-ai`

### Why They Conflict
`ai-coach-universal-compete-microsoft` fires on: *"Microsoft (Copilot, Agent 365, Power Platform, Fabric) mentioned as a competitor or when discussing AI/platform consolidation."*

`ai-coach-universal-compete-frontier-ai` fires on: *"customer evaluating Frontier AI providers (OpenAI, Anthropic, Google) competing on model capabilities, LLM selection, or AI-first platform."*

Microsoft Copilot is both a Microsoft product AND an AI/LLM product. Requests comparing ServiceNow to "Microsoft Copilot" can trigger both skills — compete-microsoft (Copilot is listed) and compete-frontier-ai (Copilot = AI assistant / LLM product). The boundary between the two skills is undefined for Microsoft AI products.

### ✅ Rewritten Descriptions

**`ai-coach-universal-compete-microsoft`** *(owns ALL Microsoft products including Copilot and Azure AI)*
> Use when Microsoft is the named competitor — covers ALL Microsoft products: Copilot, Microsoft 365, Agent 365, Power Platform, Power Automate, Fabric, Azure AI, and Azure OpenAI Service. Microsoft AI products (Copilot, Azure AI) are owned by this skill, NOT by `ai-coach-universal-compete-frontier-ai`. Trigger on any mention of Microsoft as a competing vendor regardless of whether the discussion is AI-focused.

**`ai-coach-universal-compete-frontier-ai`** *(pure-play AI vendors — excludes Microsoft)*
> Use when the customer is evaluating pure-play Frontier AI providers: OpenAI, Anthropic (Claude), Google (Gemini/Vertex), Meta (Llama), or Mistral — competing on model capabilities, LLM selection, or AI-first platform. Do NOT trigger for Microsoft products (including Copilot and Azure AI) — those are exclusively handled by `ai-coach-universal-compete-microsoft`.

---

## GROUP 8 🟡 MEDIUM — Goal vs. Deliverable Boundary: `ai-coach-universal-strategy-coach` + specific `ai-coach-*` skills

**Skills:** `ai-coach-universal-strategy-coach` · `ai-coach-grow-sales-plays` · `ai-coach-crm-pursuit-plan` · `ai-coach-plan-account-planning` · `value-melody-coach` · `ai-coach-universal-compete-salesforce`

### Why They Conflict
`ai-coach-universal-strategy-coach` fires on: *"Use when seller describes a GOAL rather than requesting a specific deliverable."*

Despite this exclusion, strategy-coach co-fires on specific deliverable requests because many deliverable requests are phrased as goals ("I want to close this deal," "I need to grow this account," "What should I be selling?"). The trigger condition "GOAL rather than specific deliverable" is too loosely defined — keywords like "what should I do," "how do I," and "where do I start" appear in both goal statements AND deliverable-specific requests.

### ✅ Rewritten Descriptions

**`ai-coach-universal-strategy-coach`** *(goal orchestrator — defer when specific deliverable is named)*
> Use exclusively when the seller describes a high-level goal or challenge WITHOUT naming a specific deliverable or tool: "where do I start?", "what should I be doing?", "how do I approach this?", "I want to grow this account." Do NOT trigger when the user has already identified a specific output — if they name a pursuit plan, sales play, account plan, business case, compete card, or meeting brief, route to the appropriate skill directly. Strategy-coach routes TO other skills; it does not replace them.

---

## GROUP 9 🟡 MEDIUM — Skill Creation Overlap: `skill-creator` + `skill-development`

**Skills:** `skill-creator` · `skill-development`

### Why They Conflict
`skill-creator` fires on: *"Create new skills, improve existing skills, and measure skill performance, running evals, or benchmarking with variance analysis."*

`skill-development` fires on: *"Use when user wants to 'create a skill', 'add a skill to plugin', 'write a new skill'..."*

The phrases "create a skill" and "create a new skill" appear in both trigger conditions. A user asking to create a new skill can legitimately trigger either. The distinction — skill-creator is for standalone skill authoring and measurement; skill-development is for adding skills within the context of a Claude Code plugin — is not expressed in either description.

### ✅ Rewritten Descriptions

**`skill-creator`** *(standalone skill authoring and performance measurement — not plugin-specific)*
> Use when creating, improving, or measuring standalone skills: writing skill descriptions, running evaluation test cases, benchmarking trigger consistency, or conducting variance analysis. Covers the full skill improvement lifecycle (Draft → Test → Evaluate → Rewrite → Repeat). Do NOT trigger for plugin development context — use `skill-development` when the user is adding a skill within a Claude Code plugin structure.

**`skill-development`** *(plugin-context skill authoring only)*
> Use when adding or creating a skill within a Claude Code plugin: skill file anatomy (SKILL.md + resources), plugin skill registration, progressive disclosure design, skill content structure. Triggered within plugin development workflows: "add a skill to my plugin," "write a skill for this plugin," "create a skill component." Do NOT trigger for standalone skill creation, eval runs, or performance measurement — use `skill-creator` for those.

---

## Summary Table

| Skill | Conflict Level | Key Change Made |
|---|---|---|
| `docx` | 🔴 HIGH | Added explicit exclusion — do not co-trigger `smart-brevity-docx` |
| `smart-brevity-docx` | 🔴 HIGH | Converted to **internal dependency** — remove all user-facing triggers |
| `servicenow-brand-standards` | 🔴 HIGH | Converted to **internal dependency** — remove all user-facing triggers |
| `pptx` | 🔴 HIGH | Added exclusion for ServiceNow corporate template requests |
| `servicenow-corporate-pptx` | 🔴 HIGH | Added explicit "NOT for generic PowerPoint" exclusion |
| `value-melody-coach` | 🔴 HIGH | Now owns all "Hey Melody" / "Hi Melody" user salutations |
| `value-melody-analyst` | 🔴 HIGH | Converted to **internal dependency** — called after VE_Pipeline, not by users |
| `ai-coach-engage-meeting-prep` | 🟡 MEDIUM | Added exclusion for discovery question requests |
| `ai-coach-engage-discovery` | 🟡 MEDIUM | Added exclusion for meeting briefs and talking points |
| `ai-coach-engage-solution-mapping` | 🟡 MEDIUM | Clarified: informational objection responses only, not role-play |
| `ai-coach-engage-objection-handling` | 🟡 MEDIUM | Clarified: role-play practice only, not product capability explanation |
| `ai-coach-universal-compete-microsoft` | 🟡 MEDIUM | Explicitly claims ownership of ALL Microsoft AI products including Copilot |
| `ai-coach-universal-compete-frontier-ai` | 🟡 MEDIUM | Added explicit Microsoft exclusion |
| `ai-coach-universal-strategy-coach` | 🟡 MEDIUM | Tightened — defer when specific deliverable is named |
| `skill-creator` | 🟡 MEDIUM | Scoped to standalone skill authoring and measurement |
| `skill-development` | 🟡 MEDIUM | Scoped to plugin-context skill creation only |

---

## Skills With No Conflicts Identified

| Skill | Reason |
|---|---|
| `pdf` | Highly specific to PDF file operations; no other skill shares PDF triggers |
| `xlsx` | Specific to spreadsheet files; no meaningful overlap |
| `product-self-knowledge` | Anthropic/Claude product facts; no operational overlap with other skills |
| `frontend-design` | Web UI creation; distinct from document and data skills |
| `account-lookup` | ServiceNow account search; tightly scoped, called before data connector |
| `ai-coach-crm-now-next` | NNCRM-specific terminology; very narrow trigger vocabulary |
| `ai-coach-crm-pursuit-plan` | Specific deliverable (CRM pursuit plan Word doc); resolved by strategy-coach tightening |
| `ai-coach-engage-mutual-plan` | Specific deliverable (mutual plan Excel); no meaningful overlap |
| `kahani-customer-reference-agent` | Customer reference search; distinct enough from other skills |
| `analytics-data-connector` | Already marked internal-only; no user-facing trigger conflicts |
| `ai-coach-engage-objection-handling` | After rewrite, role-play scope is clear and exclusive |
| `ai-coach-grow-sales-plays` | Sales play terminology is specific; minor residual pptx overlap is acceptable |
| `ai-coach-plan-account-planning` | Requires uploaded template file; specific enough to avoid major conflicts |
| `ai-coach-universal-compete-salesforce` | Salesforce-specific; resolved by strategy-coach tightening |
| `ai-coach-universal-partner-rtm` | Partner/RTM strategy; distinct vocabulary |
| `value-melody-coach` | After rewrite, owns all user Melody interactions |
| `claude-automation-recommender` | Codebase analysis for automations; distinct from all other skills |
| `agent-development` | Plugin-dev context; agent creation is specific |
| `hook-development` | Plugin-dev context; hook creation is specific |
| `plugin-structure` | Plugin scaffolding; specific enough |
| `command-development` | Slash command creation; specific enough |
| `plugin-settings` | .local.md pattern; narrow scope |
| `mcp-integration` | MCP server config; specific enough |
| `claude-md-improver` | CLAUDE.md auditing; distinct from all others |
| `playground` | Interactive HTML playground; distinct output type |
| `example-skill` | Demo/template skill; after rewrite narrow enough |
| `writing-hookify-rules` | Hookify-specific; distinct |
| `stripe-best-practices` | Stripe integration; distinct domain |
| `github-file-checkin` | GitHub API file operations; distinct from all others |
| `skills-conflict-detection-and-resolution` | Manual trigger only; no conflict possible |
