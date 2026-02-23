# Skill Conflict Detection Report
**Generated:** 2026-02-20
**Total Skills Analyzed:** 44 (17 from filesystem plugins/project + 27 from test-case descriptions)
**Conflicts Identified:** 9 groups

---

## Inventory Summary

### Skills Read From Filesystem

| Skill | Location |
|---|---|
| `github-file-checkin` | project `.claude/skills/` |
| `skills-conflict-detection-and-resolution` | project `.claude/skills/` |
| `stripe-best-practices` | plugin: external/stripe |
| `claude-automation-recommender` | plugin: claude-code-setup |
| `claude-md-improver` | plugin: claude-md-management |
| `example-skill` | plugin: example-plugin |
| `frontend-design` | plugin: frontend-design |
| `writing-hookify-rules` | plugin: hookify |
| `playground` | plugin: playground |
| `skill-creator` | plugin: skill-creator |
| `agent-development` | plugin: plugin-dev |
| `command-development` | plugin: plugin-dev |
| `hook-development` | plugin: plugin-dev |
| `mcp-integration` | plugin: plugin-dev |
| `plugin-settings` | plugin: plugin-dev |
| `plugin-structure` | plugin: plugin-dev |
| `skill-development` | plugin: plugin-dev |

### Skills From Test-Case Descriptions (trigger descriptions provided by test file)

**Public:** `docx`, `pdf`, `pptx`, `xlsx`, `product-self-knowledge`, `frontend-design`
**Organization:** `account-lookup`, `ai-coach-crm-now-next`, `ai-coach-crm-pursuit-plan`, `value-melody-analyst`, `ai-coach-engage-solution-mapping`, `ai-coach-engage-mutual-plan`, `kahani-customer-reference-agent`, `ai-coach-engage-discovery`, `analytics-data-connector`, `servicenow-corporate-pptx`, `ai-coach-engage-meeting-prep`, `ai-coach-engage-objection-handling`, `ai-coach-grow-sales-plays`, `ai-coach-plan-account-planning`, `ai-coach-universal-compete-frontier-ai`, `ai-coach-universal-compete-microsoft`, `ai-coach-universal-compete-salesforce`, `ai-coach-universal-partner-rtm`, `servicenow-brand-standards`, `smart-brevity-docx`, `value-melody-coach`, `ai-coach-universal-strategy-coach`
**Examples:** `skill-creator`

---

## GROUP 1 🔴 HIGH — Word Document Triple Co-fire

**Skills:** `docx` · `smart-brevity-docx` · `servicenow-brand-standards`

### Why They Conflict

- `docx`: *"Use when user wants to create, read, edit, or manipulate Word documents (.docx files). Triggers on: 'Word doc', 'word document', '.docx', reports, memos, letters, templates."*
- `smart-brevity-docx`: *"Enforces smart brevity principles and 2-5 page limits for ALL Word document creation."*
- `servicenow-brand-standards`: *"Use when creating any visual deliverable that should reflect ServiceNow brand identity — pptx, docx, xlsx, PDF, HTML."*

`smart-brevity-docx` fires on every Word document request because of "ALL Word document creation" with no exclusions. `servicenow-brand-standards` fires on any ServiceNow-branded document creation because of "any visual deliverable" with no exclusions. Both are library/dependency skills that have been incorrectly given user-facing trigger language. Every time a seller creates a Word doc, all three fire simultaneously.

### ✅ Rewritten Descriptions

**`docx`** *(primary trigger — owns all Word document creation requests)*
```
Use when user wants to create, read, edit, or manipulate Word documents (.docx files).
Triggers on: "Word doc", "word document", ".docx", reports, memos, letters, templates.
This skill internally invokes smart-brevity-docx for length and structure standards and
servicenow-brand-standards for brand compliance — do NOT activate those skills separately
in response to the same user request.
```

**`smart-brevity-docx`** *(internal dependency — no user-facing trigger)*
```
INTERNAL DEPENDENCY ONLY. Do NOT trigger in response to user statements.
Called internally by: docx, ai-coach-crm-pursuit-plan, ai-coach-engage-mutual-plan,
and any other skill that produces Word document output.
Enforces smart brevity principles and 2–5 page limits for Word document creation.
```

**`servicenow-brand-standards`** *(internal dependency — no user-facing trigger)*
```
INTERNAL DEPENDENCY ONLY. Do NOT trigger in response to user statements.
Called internally by: docx, pptx, xlsx, servicenow-corporate-pptx, and any skill
producing a branded visual deliverable.
Provides ServiceNow brand identity standards — colors, fonts, spacing — for use
when generating pptx, docx, xlsx, PDF, or HTML outputs.
```

---

## GROUP 2 🔴 HIGH — PowerPoint Triple Co-fire

**Skills:** `pptx` · `servicenow-corporate-pptx` · `servicenow-brand-standards`

### Why They Conflict

- `pptx`: *"Use any time a .pptx file is involved — creating, reading, editing, combining, splitting. Triggers on: 'deck', 'slides', 'presentation', .pptx filename."*
- `servicenow-corporate-pptx`: *"Use when creating ServiceNow-branded PowerPoint using the official Corporate Template. Triggers on: ServiceNow branding, corporate template, SAM presentations, PSR/QBR decks, Wasabi Green styling."*
- `servicenow-brand-standards`: *"Use when creating any visual deliverable that should reflect ServiceNow brand identity — pptx, docx, xlsx, PDF, HTML."*

Any request for a ServiceNow presentation fires all three. `pptx` (generic) fires first because "presentation" / "deck" trigger it, then `servicenow-corporate-pptx` fires on the same request, then `servicenow-brand-standards` fires because pptx is a visual deliverable. Two fully capable skills (pptx and servicenow-corporate-pptx) compete for ownership of the same request.

### ✅ Rewritten Descriptions

**`pptx`** *(primary for non-branded presentations; defers to servicenow-corporate-pptx for branded)*
```
Use when working with .pptx files that are NOT ServiceNow-branded — creating, reading,
editing, combining, or splitting generic PowerPoint presentations.
Triggers on: "deck", "slides", "presentation", ".pptx" — UNLESS the request mentions
ServiceNow branding, corporate template, PSR, QBR, SAM, or Wasabi Green, in which case
use servicenow-corporate-pptx instead.
Brand compliance is handled internally via servicenow-brand-standards — do NOT activate
that skill separately.
```

**`servicenow-corporate-pptx`** *(primary for all ServiceNow-branded presentations)*
```
Use when creating a PowerPoint presentation that must use the official ServiceNow
Corporate Template. Triggers on: ServiceNow branding, corporate template, PSR deck,
QBR deck, SAM training deck, Wasabi Green styling, Infinite Blue background.
Do NOT also trigger the generic pptx skill for these requests — this skill handles
all .pptx operations for branded decks.
Brand standards are applied internally — do NOT activate servicenow-brand-standards separately.
```

---

## GROUP 3 🔴 HIGH — Value Melody Dual Trigger

**Skills:** `value-melody-coach` · `value-melody-analyst`

### Why They Conflict

- `value-melody-coach`: *"PRIMARY WORKFLOW for creating value deliverables (business cases, SVPs, BVAs, narratives)."*
- `value-melody-analyst`: *"Post-API reference guide loaded AFTER ValueMelody:VE_Pipeline returns data OR when user request contains 'Value Melody', 'Hey Melody', or 'Hi Melody'."*

The phrases "Hey Melody", "Hi Melody", and "Value Melody" appear in the trigger language of `value-melody-analyst` but are also the natural way a user would start any Value Melody workflow that belongs to `value-melody-coach`. Both skills fire simultaneously on the same greeting, creating race condition behavior where the user gets two conflicting responses.

### ✅ Rewritten Descriptions

**`value-melody-coach`** *(primary user-facing skill for all Value Melody workflows)*
```
PRIMARY WORKFLOW for creating value deliverables: business cases, Strategic Value
Perspectives (SVPs), Business Value Assessments (BVAs), and executive narratives.
Triggers on: "Hey Melody", "Hi Melody", "Value Melody", "business case", "SVP",
"BVA", "value story", "strategic framing", "value deliverable".
This skill calls VE_Pipeline internally and then loads value-melody-analyst as a
reference guide. Do NOT trigger value-melody-analyst directly in response to user
greeting phrases — this skill manages the full workflow.
```

**`value-melody-analyst`** *(internal reference — no user-facing trigger)*
```
INTERNAL REFERENCE ONLY. Do NOT trigger in response to user statements containing
"Hey Melody", "Hi Melody", or "Value Melody" — those are handled by value-melody-coach.
Loaded automatically by value-melody-coach AFTER the VE_Pipeline API call returns data,
to provide analytical guidance for interpreting ValueMelody output fields.
```

---

## GROUP 4 🔴 HIGH — Duplicate Skill Names (frontend-design, skill-creator)

**Skills:** `frontend-design` (public, test-cases) · `frontend-design` (plugin: frontend-design)

**Skills:** `skill-creator` (examples, test-cases) · `skill-creator` (plugin: skill-creator)

### Why They Conflict

Two pairs of skills share **identical names**. When both are active, the routing system cannot deterministically select which one to invoke. The plugin `frontend-design` and the organization's public `frontend-design` have nearly identical trigger phrases — both fire on "build web components", "pages", "applications". The plugin `skill-creator` and the examples `skill-creator` both fire on "create a skill" and "improve skill".

### ✅ Rewritten Descriptions

**`frontend-design` (public/organization)** *(owns general frontend requests in organization context)*
```
Use when building web components, pages, dashboards, React components, HTML/CSS layouts,
or styling/beautifying any web UI — in the context of the organization's products or
customer-facing deliverables.
Do NOT trigger for plugin or Claude Code development tasks — use the plugin-dev/frontend-design
skill for those contexts.
```

**`frontend-design` (plugin)** *(owns frontend requests in Claude Code plugin development context)*
```
Create distinctive, production-grade frontend interfaces with high design quality for
Claude Code plugin development contexts.
Use this skill when the user asks to build web components, pages, or applications as part
of a Claude Code plugin, extension, or developer tool.
Do NOT trigger for general business/sales web UI tasks — those use the organization's
frontend-design skill.
```

**`skill-creator` (examples/organization)** *(owns skill creation for organizational skills library)*
```
Use when creating new organizational skills, improving existing skills in the /mnt/skills/
library, measuring skill performance, running evals, or benchmarking with variance analysis.
Scope: organization and public skill development workflows.
Do NOT trigger for plugin skill development — use the plugin-dev skill-development skill instead.
```

**`skill-creator` (plugin)** *(owns skill creation for Claude Code plugin development)*
```
Use when creating or improving skills within Claude Code plugins (stored in plugin
skills/ directories), running evals on plugin skills, or benchmarking plugin skill performance.
Scope: plugin skill development only.
Do NOT trigger for organizational skill library management — use the organization skill-creator instead.
```

---

## GROUP 5 🟡 MEDIUM — Skill Development Overlap (plugin-dev suite)

**Skills:** `skill-development` · `skill-creator` (plugin) · `example-skill`

### Why They Conflict

- `skill-development`: *"...when the user wants to 'create a skill', 'add a skill to plugin', 'write a new skill'..."*
- `skill-creator` (plugin): *"...when users want to create a skill from scratch, update or optimize an existing skill, run evals..."*
- `example-skill`: *"...when the user asks to 'demonstrate skills', 'show skill format', 'create a skill template'..."*

All three fire on "create a skill". `skill-development` and `skill-creator` have near-identical triggering conditions. `example-skill` partially overlaps on "create a skill template".

### ✅ Rewritten Descriptions

**`skill-development`** *(plugin-dev plugin — structural/architectural guidance only)*
```
This skill should be used when the user wants guidance on skill file structure, SKILL.md
format, progressive disclosure principles, writing style requirements, or frontmatter
conventions for skills inside Claude Code plugins.
Do NOT trigger for full skill creation workflows, evals, or iteration loops — use
skill-creator for those. Do NOT trigger for "create a skill template" examples — use example-skill.
```

**`skill-creator`** *(full creation/improvement/eval workflow)*
```
Use when users want to create a skill from scratch with full guided workflow (interviews,
drafts, test runs, iteration), update or optimize an existing skill through eval loops,
run evals to test skill performance, or benchmark skill performance with variance analysis.
Do NOT trigger for structural/format questions only — use skill-development for those.
```

**`example-skill`** *(reference template only)*
```
This skill should be used when the user asks to "demonstrate skills", "show skill format",
"see a skill template", or needs a reference example of SKILL.md structure.
Do NOT trigger for actual skill creation, improvement, or evaluation — use skill-creator
for those workflows.
```

---

## GROUP 6 🟡 MEDIUM — Meeting Prep, Discovery, and Objection Handling Overlap

**Skills:** `ai-coach-engage-meeting-prep` · `ai-coach-engage-discovery` · `ai-coach-engage-objection-handling`

### Why They Conflict

- `ai-coach-engage-meeting-prep`: *"Create meeting briefs, talking points, and discussion strategies... Use for PREPARATION or RECAP, not discovery questions."*
- `ai-coach-engage-discovery`: *"Generate strategic discovery questions with data-powered personalization."*
- `ai-coach-engage-objection-handling`: *"Interactive role-play coaching for procurement and legal objections."*

Meeting prep already includes a partial exclusion ("not discovery questions"), but requests like "prepare my discovery questions for my upcoming call" or "help me prepare for procurement objections in my meeting" fall in the overlap zone and fire 2 skills. "Prepare for objections" in a meeting context fires both meeting-prep and objection-handling.

### ✅ Rewritten Descriptions

**`ai-coach-engage-meeting-prep`** *(owns briefs, talking points, and recaps only)*
```
Create meeting briefs, talking points, and discussion strategies for upcoming customer
meetings or post-meeting recaps.
Triggers on: "meeting brief", "talking points", "prep for my meeting", "call prep",
"meeting recap", "what should I talk about".
Do NOT trigger when the request is specifically for discovery question generation —
use ai-coach-engage-discovery for that.
Do NOT trigger when the request is for objection role-play or practice coaching —
use ai-coach-engage-objection-handling for that.
```

**`ai-coach-engage-discovery`** *(owns discovery question generation only)*
```
Generate strategic discovery questions with data-powered personalization.
Triggers on: "discovery questions", "discovery agenda", "what to ask", "qualifying questions",
"uncover pain points" — when the output is a set of questions to ask the customer.
Do NOT trigger for general meeting prep (briefs, talking points) — use ai-coach-engage-meeting-prep.
Do NOT trigger for objection practice — use ai-coach-engage-objection-handling.
```

**`ai-coach-engage-objection-handling`** *(owns interactive role-play and objection coaching only)*
```
Interactive role-play coaching for procurement and legal objections.
Triggers on: "role play", "practice", "quiz me", "simulate", "objection handling",
"I keep fumbling", "practice run" — when the user wants an interactive coaching session.
Do NOT trigger for general meeting prep or call preparation — use ai-coach-engage-meeting-prep.
Do NOT trigger for solution mapping or technical objections in a non-role-play context —
use ai-coach-engage-solution-mapping for those.
```

---

## GROUP 7 🟡 MEDIUM — Solution Mapping vs Objection Handling

**Skills:** `ai-coach-engage-solution-mapping` · `ai-coach-engage-objection-handling`

### Why They Conflict

- `ai-coach-engage-solution-mapping`: *"...handle technical objections, create solution briefs. NOT for ROI modeling."*
- `ai-coach-engage-objection-handling`: *"Interactive role-play coaching for procurement and legal objections."*

Both handle "objections". The phrase "handle objections" or "respond to objections" fires both — even though solution-mapping handles substantive technical objections (informational) while objection-handling is for interactive role-play practice. "The customer's IT team is worried X — how do I handle that?" fires both.

### ✅ Rewritten Descriptions

**`ai-coach-engage-solution-mapping`** *(owns substantive technical objection responses — informational)*
```
Map business problems to ServiceNow solutions with quantified outcomes. Explain product
capabilities, handle technical objections with factual responses, create solution briefs.
NOT for ROI modeling. NOT for role-play coaching.
Triggers on: "what does ServiceNow do", "customer is asking about", "explain product",
"create a solution brief", "technical objection" (when the user wants a factual answer
to give the customer — not a practice session).
Do NOT trigger for interactive objection practice — use ai-coach-engage-objection-handling.
```

**`ai-coach-engage-objection-handling`** *(owns objection role-play and practice coaching only)*
*(see rewritten description in Group 6 above)*

---

## GROUP 8 🟡 MEDIUM — Compete Skill Overlap (Microsoft + Frontier AI)

**Skills:** `ai-coach-universal-compete-microsoft` · `ai-coach-universal-compete-frontier-ai`

### Why They Conflict

- `ai-coach-universal-compete-microsoft`: *"Use when Microsoft (Copilot, Agent 365, Power Platform, Fabric) is mentioned as a competitor or when discussing AI/platform consolidation."*
- `ai-coach-universal-compete-frontier-ai`: *"Use when customer evaluating Frontier AI providers (OpenAI, Anthropic, Google) competing on model capabilities, LLM selection, or AI-first platform."*

Microsoft Copilot and Azure OpenAI Service straddle both categories. A request about "Microsoft AI" or "Azure AI" or "Microsoft vs AI-first platform" fires both skills. "AI/platform consolidation" in microsoft's description also collides with "AI-first platform" in frontier-ai's description.

### ✅ Rewritten Descriptions

**`ai-coach-universal-compete-microsoft`** *(owns Microsoft product suite — excludes pure LLM model comparisons)*
```
Use when Microsoft is mentioned as a competitor in a deal, specifically around:
Microsoft 365 / Copilot for M365, Agent 365, Power Platform, Power Automate, Fabric,
Teams, or platform consolidation.
Do NOT trigger when the discussion is purely about foundation model or LLM selection
(e.g., Azure OpenAI API vs other model APIs) — use ai-coach-universal-compete-frontier-ai
for those. If both Microsoft products AND LLM capabilities are in scope, use this skill
and reference compete-frontier-ai for the AI model portion.
```

**`ai-coach-universal-compete-frontier-ai`** *(owns foundation model and LLM platform comparisons)*
```
Use when the customer is evaluating foundation model providers or LLM platforms:
OpenAI (ChatGPT / API), Anthropic Claude, Google Gemini / Vertex AI, or build-vs-buy
on raw AI models.
Do NOT trigger when the competitor is Microsoft's productivity suite (Copilot for M365,
Power Platform, Agent 365) — use ai-coach-universal-compete-microsoft for those.
Trigger only when the conversation is about LLM selection, model capabilities, or
AI-first platform strategy.
```

---

## GROUP 9 🟡 MEDIUM — Strategy Coach vs Specific ai-coach-* Skills

**Skills:** `ai-coach-universal-strategy-coach` · multiple `ai-coach-*` skills

### Why They Conflict

- `ai-coach-universal-strategy-coach`: *"Use when seller describes a GOAL rather than requesting a specific deliverable. Transforms goal statements into actionable milestone sequences."*

The distinction "GOAL rather than a specific deliverable" is correct in intent but fails in practice because:
- Goal statements often contain keywords owned by specific skills ("I want to close a competitive Salesforce deal" → fires strategy-coach AND compete-salesforce)
- The strategy-coach routes to other skills anyway, creating a relay: user → strategy-coach → compete-salesforce, instead of direct: user → compete-salesforce

### ✅ Rewritten Descriptions

**`ai-coach-universal-strategy-coach`** *(owns ambiguous multi-step goals only)*
```
Use when the seller describes an open-ended strategic goal WITHOUT naming a specific
action or deliverable type — the request spans multiple deal stages or skills and
requires milestone sequencing.
Triggers on: "where do I even start", "how should I approach", "what's my strategy for",
"help me figure out", "I want to grow [account]", "I just got assigned" — when there
is NO specific deliverable (brief, discovery questions, compete card, etc.) mentioned.
Do NOT trigger if the seller names a specific deliverable or action type (compete card,
meeting brief, discovery questions, pursuit plan, account plan) — use the specific
skill for that deliverable directly.
```

---

## Summary Table

| Skill | Conflict Level | Key Change Made |
|---|---|---|
| `docx` | 🔴 HIGH | Owns all Word doc requests; explicitly suppresses smart-brevity-docx and brand-standards co-fires |
| `smart-brevity-docx` | 🔴 HIGH | Removed user-facing trigger; designated internal dependency of docx |
| `servicenow-brand-standards` | 🔴 HIGH | Removed user-facing trigger; designated internal dependency |
| `pptx` | 🔴 HIGH | Defers to servicenow-corporate-pptx for branded decks; mutual exclusion added |
| `servicenow-corporate-pptx` | 🔴 HIGH | Explicit owner of all branded presentation requests; suppresses pptx co-fire |
| `value-melody-coach` | 🔴 HIGH | Owns all "Hey Melody" / "Hi Melody" triggers; calls analyst internally |
| `value-melody-analyst` | 🔴 HIGH | Removed user-facing triggers; internal reference only |
| `frontend-design` (public) | 🔴 HIGH | Scoped to org/customer deliverables only |
| `frontend-design` (plugin) | 🔴 HIGH | Scoped to plugin development context only |
| `skill-creator` (org/examples) | 🔴 HIGH | Scoped to /mnt/skills organizational library |
| `skill-creator` (plugin) | 🔴 HIGH | Scoped to plugin skill development only |
| `skill-development` | 🟡 MEDIUM | Scoped to structure/format guidance; defers workflow to skill-creator |
| `example-skill` | 🟡 MEDIUM | Scoped to reference/template viewing only |
| `ai-coach-engage-meeting-prep` | 🟡 MEDIUM | Explicit exclusions: not for discovery questions, not for role-play |
| `ai-coach-engage-discovery` | 🟡 MEDIUM | Explicit exclusions: not for general prep, not for role-play |
| `ai-coach-engage-objection-handling` | 🟡 MEDIUM | Scoped to interactive role-play only; not for factual objection responses |
| `ai-coach-engage-solution-mapping` | 🟡 MEDIUM | Clarified: factual objection responses only, not role-play |
| `ai-coach-universal-compete-microsoft` | 🟡 MEDIUM | Excludes pure LLM/foundation model comparisons |
| `ai-coach-universal-compete-frontier-ai` | 🟡 MEDIUM | Excludes Microsoft productivity suite scenarios |
| `ai-coach-universal-strategy-coach` | 🟡 MEDIUM | Narrowed to ambiguous multi-stage goals only; defers when specific deliverable named |
| `analytics-data-connector` | 🟢 LOW | Already correctly marked internal; no change needed |

---

## Skills With No Conflicts Identified

The following skills have sufficiently narrow, non-overlapping trigger conditions:

- `pdf` — unique trigger domain (PDF files only)
- `xlsx` — unique trigger domain (spreadsheet files)
- `product-self-knowledge` — unique domain (Anthropic product facts)
- `account-lookup` — unique role (account resolution before other skills)
- `ai-coach-crm-now-next` — specific keyword set (NNCRM, Now Next CRM)
- `ai-coach-crm-pursuit-plan` — specific deliverable (CRM pursuit plan document)
- `kahani-customer-reference-agent` — unique function (customer reference search)
- `ai-coach-engage-mutual-plan` — specific deliverable (mutual plan Excel)
- `ai-coach-grow-sales-plays` — keyword-gated (sales play, hero play, SSC)
- `ai-coach-plan-account-planning` — upload-gated (requires uploaded account plan)
- `ai-coach-universal-compete-salesforce` — specific competitor (Salesforce only)
- `ai-coach-universal-partner-rtm` — specific topic (partner strategy/RTM models)
- `github-file-checkin` — specific action (GitHub API file commits)
- `skills-conflict-detection-and-resolution` — manual trigger only
- `stripe-best-practices` — specific domain (Stripe payment integration)
- `claude-automation-recommender` — specific context (Claude Code setup/automation)
- `claude-md-improver` — specific target (CLAUDE.md audit and improvement)
- `writing-hookify-rules` — specific tool (hookify rule authoring)
- `playground` — specific output type (interactive HTML explorers)
- `agent-development` — specific component type (agent file creation)
- `command-development` — specific component type (slash command creation)
- `hook-development` — specific component type (hook configuration)
- `mcp-integration` — specific component type (MCP server configuration)
- `plugin-settings` — specific pattern (.claude/plugin-name.local.md)
- `plugin-structure` — specific scope (plugin directory layout)
