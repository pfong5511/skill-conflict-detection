# Skill Triggering Pre-Test Results (Baseline — Current Descriptions)
**Executed:** 2026-02-23
**Total Test Cases:** 145 (29 skills × 5 test cases)
**Evaluation basis:** Current/original skill descriptions — no rewrites applied

> ⚠️ All trigger predictions are self-assessments. Claude is predicting its own behavior based on reading current skill descriptions. Actual runtime behavior may vary across sessions.

---

## Summary Dashboard

| Metric | Count | % |
|---|---|---|
| ✅ Clean PASS | 108 | 74.5% |
| ⚠️ PASS WITH CO-FIRE | 37 | 25.5% |
| ❌ FAIL | 0 | 0% |
| **Total** | **145** | **100%** |

---

## Results by Skill

---

### SKILL: `docx`
| Test ID | User Statement | Expected Skill | Predicted Skill | Co-Fires | Outcome |
|---|---|---|---|---|---|
| docx-TC01 | "Can you create a Word document summarizing our Q4 sales performance with a table of contents and page numbers?" | `docx` | `docx` | `smart-brevity-docx` | ⚠️ CO-FIRE |
| docx-TC02 | "I have a .docx file I uploaded — can you extract all the text from it and give me a clean markdown version?" | `docx` | `docx` | — | ✅ PASS |
| docx-TC03 | "Please write a professional memo to my team about the new expense policy and save it as a Word file." | `docx` | `docx` | `smart-brevity-docx` | ⚠️ CO-FIRE |
| docx-TC04 | "My Word document has tracked changes from three different reviewers — can you accept all of them and give me a clean version?" | `docx` | `docx` | — | ✅ PASS |
| docx-TC05 | "Convert this .doc file I uploaded to .docx format." | `docx` | `docx` | — | ✅ PASS |

**Skill Result: 3/5 PASS · 2 co-fire · 0 FAIL**

---

### SKILL: `pdf`
| Test ID | User Statement | Expected Skill | Predicted Skill | Co-Fires | Outcome |
|---|---|---|---|---|---|
| pdf-TC01 | "I need you to merge these three PDF files I uploaded into one single document." | `pdf` | `pdf` | — | ✅ PASS |
| pdf-TC02 | "Can you extract all the text from this scanned PDF? It's a photo of a contract." | `pdf` | `pdf` | — | ✅ PASS |
| pdf-TC03 | "Please add a 'CONFIDENTIAL' watermark to every page of this PDF." | `pdf` | `pdf` | — | ✅ PASS |
| pdf-TC04 | "I need to split this 40-page PDF — pages 1–15 go to one file and pages 16–40 go to another." | `pdf` | `pdf` | — | ✅ PASS |
| pdf-TC05 | "This PDF form needs to be filled in — name is John Smith, date is February 18, 2026..." | `pdf` | `pdf` | — | ✅ PASS |

**Skill Result: 5/5 PASS · 0 co-fire · 0 FAIL**

---

### SKILL: `pptx`
| Test ID | User Statement | Expected Skill | Predicted Skill | Co-Fires | Outcome |
|---|---|---|---|---|---|
| pptx-TC01 | "Create a 10-slide presentation on the history of artificial intelligence with a bold, modern design." | `pptx` | `pptx` | — | ✅ PASS |
| pptx-TC02 | "I uploaded a PowerPoint deck — can you extract all the speaker notes into a Word document?" | `pptx` | `pptx` | `docx` (for Word output) | ⚠️ CO-FIRE |
| pptx-TC03 | "Take slides 3, 7, and 12 from my uploaded deck and create a new presentation with just those three slides." | `pptx` | `pptx` | — | ✅ PASS |
| pptx-TC04 | "Can you review my uploaded .pptx and tell me if there are any layout issues or text that's getting cut off?" | `pptx` | `pptx` | — | ✅ PASS |
| pptx-TC05 | "I need to update the title and subtitle on the cover slide of my uploaded presentation." | `pptx` | `pptx` | — | ✅ PASS |

**Skill Result: 4/5 PASS · 1 co-fire · 0 FAIL**

---

### SKILL: `xlsx`
| Test ID | User Statement | Expected Skill | Predicted Skill | Co-Fires | Outcome |
|---|---|---|---|---|---|
| xlsx-TC01 | "Create an Excel spreadsheet that tracks monthly expenses with columns for date, category, amount, and notes." | `xlsx` | `xlsx` | — | ✅ PASS |
| xlsx-TC02 | "I uploaded a messy CSV — the headers are in row 3, there's junk in the first two rows..." | `xlsx` | `xlsx` | — | ✅ PASS |
| xlsx-TC03 | "Add a new column to my uploaded Excel file that calculates the profit margin..." | `xlsx` | `xlsx` | — | ✅ PASS |
| xlsx-TC04 | "Convert my uploaded .xlsx file to a CSV." | `xlsx` | `xlsx` | — | ✅ PASS |
| xlsx-TC05 | "My Excel file has duplicate rows — can you remove all duplicates and give me a clean version?" | `xlsx` | `xlsx` | — | ✅ PASS |

**Skill Result: 5/5 PASS · 0 co-fire · 0 FAIL**

---

### SKILL: `product-self-knowledge`
| Test ID | User Statement | Expected Skill | Predicted Skill | Co-Fires | Outcome |
|---|---|---|---|---|---|
| psk-TC01 | "What are the differences between Claude Pro and Claude Team plans? Which one should my organization use?" | `product-self-knowledge` | `product-self-knowledge` | — | ✅ PASS |
| psk-TC02 | "How do I install Claude Code and what are the Node.js version requirements?" | `product-self-knowledge` | `product-self-knowledge` | — | ✅ PASS |
| psk-TC03 | "What is the context window size for Claude Opus 4 via the API?" | `product-self-knowledge` | `product-self-knowledge` | — | ✅ PASS |
| psk-TC04 | "Does the Claude API support streaming responses? How do I implement it with the Python SDK?" | `product-self-knowledge` | `product-self-knowledge` | — | ✅ PASS |
| psk-TC05 | "What are the current rate limits for the Claude API on the free tier?" | `product-self-knowledge` | `product-self-knowledge` | — | ✅ PASS |

**Skill Result: 5/5 PASS · 0 co-fire · 0 FAIL**

---

### SKILL: `frontend-design`
| Test ID | User Statement | Expected Skill | Predicted Skill | Co-Fires | Outcome |
|---|---|---|---|---|---|
| fd-TC01 | "Build me a landing page for a SaaS product called 'FlowSync'..." | `frontend-design` | `frontend-design` | — | ✅ PASS |
| fd-TC02 | "Create a React dashboard component that shows KPI cards for revenue, users, and churn rate..." | `frontend-design` | `frontend-design` | — | ✅ PASS |
| fd-TC03 | "My current website looks generic and boring — here's the HTML. Can you redesign it to look more premium?" | `frontend-design` | `frontend-design` | — | ✅ PASS |
| fd-TC04 | "Build a dark-mode pricing table component in React with three tiers: Starter, Pro, and Enterprise." | `frontend-design` | `frontend-design` | — | ✅ PASS |
| fd-TC05 | "I need a navigation bar component with a logo on the left, links in the center, and a 'Get Started' button on the right." | `frontend-design` | `frontend-design` | — | ✅ PASS |

**Skill Result: 5/5 PASS · 0 co-fire · 0 FAIL**

---

### SKILL: `account-lookup`
| Test ID | User Statement | Expected Skill | Predicted Skill | Co-Fires | Outcome |
|---|---|---|---|---|---|
| al-TC01 | "Pull up the account details for Walmart." | `account-lookup` | `account-lookup` | — | ✅ PASS |
| al-TC02 | "I need to look at data for JP Morgan — what's their account number in our system?" | `account-lookup` | `account-lookup` | — | ✅ PASS |
| al-TC03 | "Before we start the meeting prep, can you find the ServiceNow account for Delta Airlines?" | `account-lookup` | `account-lookup` | — | ✅ PASS |
| al-TC04 | "What opportunity is linked to the Nike deal we're working on?" | `account-lookup` | `account-lookup` | — | ✅ PASS |
| al-TC05 | "I have a call with 3M tomorrow — find their account so we can pull their data." | `account-lookup` | `account-lookup` | — | ✅ PASS |

**Skill Result: 5/5 PASS · 0 co-fire · 0 FAIL**

---

### SKILL: `ai-coach-crm-now-next`
| Test ID | User Statement | Expected Skill | Predicted Skill | Co-Fires | Outcome |
|---|---|---|---|---|---|
| crm-nn-TC01 | "Does my CRM deal at Acme qualify for the Now Next CRM program?" | `ai-coach-crm-now-next` | `ai-coach-crm-now-next` | — | ✅ PASS |
| crm-nn-TC02 | "Explain to me how the NNCRM methodology works and what the approval process looks like." | `ai-coach-crm-now-next` | `ai-coach-crm-now-next` | — | ✅ PASS |
| crm-nn-TC03 | "My customer is interested in CRM transformation — what co-investment options do we have available?" | `ai-coach-crm-now-next` | `ai-coach-crm-now-next` | — | ✅ PASS |
| crm-nn-TC04 | "Can I get a CRM pricing ramp for the Walmart deal? What are the conditions?" | `ai-coach-crm-now-next` | `ai-coach-crm-now-next` | — | ✅ PASS |
| crm-nn-TC05 | "I want to accelerate my CRM deal at Target — what deal acceleration programs are available?" | `ai-coach-crm-now-next` | `ai-coach-crm-now-next` | — | ✅ PASS |

**Skill Result: 5/5 PASS · 0 co-fire · 0 FAIL**

---

### SKILL: `ai-coach-crm-pursuit-plan`
| Test ID | User Statement | Expected Skill | Predicted Skill | Co-Fires | Outcome |
|---|---|---|---|---|---|
| crm-pp-TC01 | "Create a CRM pursuit plan for my top 3 accounts this quarter." | `ai-coach-crm-pursuit-plan` | `ai-coach-crm-pursuit-plan` | `ai-coach-universal-strategy-coach` | ⚠️ CO-FIRE |
| crm-pp-TC02 | "I need a formal pursuit plan document for the Salesforce takeout opportunity at Boeing." | `ai-coach-crm-pursuit-plan` | `ai-coach-crm-pursuit-plan` | `ai-coach-universal-compete-salesforce` | ⚠️ CO-FIRE |
| crm-pp-TC03 | "Build me a CRM account plan that shows CACV, white space, and which CRM products to prioritize for Target." | `ai-coach-crm-pursuit-plan` | `ai-coach-crm-pursuit-plan` | — | ✅ PASS |
| crm-pp-TC04 | "I have a QBR with my manager next week and need a CRM pursuit plan document for my territory." | `ai-coach-crm-pursuit-plan` | `ai-coach-crm-pursuit-plan` | — | ✅ PASS |
| crm-pp-TC05 | "Can you put together a CRM plan document for the Home Depot opportunity that includes customer stories and proof points?" | `ai-coach-crm-pursuit-plan` | `ai-coach-crm-pursuit-plan` | — | ✅ PASS |

**Skill Result: 3/5 PASS · 2 co-fire · 0 FAIL**

---

### SKILL: `value-melody-analyst`
| Test ID | User Statement | Expected Skill | Predicted Skill | Co-Fires | Outcome |
|---|---|---|---|---|---|
| vma-TC01 | "Hey Melody, what's the current adoption health for my Walmart account?" | `value-melody-analyst` | `value-melody-analyst` | — | ✅ PASS |
| vma-TC02 | "Hi Melody — run a full analysis on the Microsoft account." | `value-melody-analyst` | `value-melody-analyst` | `value-melody-coach` | ⚠️ CO-FIRE |
| vma-TC03 | "Value Melody, show me the bad news outcomes for Acme Corp." | `value-melody-analyst` | `value-melody-analyst` | — | ✅ PASS |
| vma-TC04 | "Hey Melody, what products does Target own and how well are they using them?" | `value-melody-analyst` | `value-melody-analyst` | — | ✅ PASS |
| vma-TC05 | "Hi Melody — give me the optimization opportunities for the Nike account." | `value-melody-analyst` | `value-melody-analyst` | `value-melody-coach` | ⚠️ CO-FIRE |

**Skill Result: 3/5 PASS · 2 co-fire · 0 FAIL**

---

### SKILL: `ai-coach-engage-solution-mapping`
| Test ID | User Statement | Expected Skill | Predicted Skill | Co-Fires | Outcome |
|---|---|---|---|---|---|
| sm-TC01 | "My customer is struggling with IT incident resolution times — which ServiceNow product addresses that and what outcomes can they expect?" | `ai-coach-engage-solution-mapping` | `ai-coach-engage-solution-mapping` | — | ✅ PASS |
| sm-TC02 | "The customer's security team is asking about how ServiceNow handles data residency and encryption — can you help me respond?" | `ai-coach-engage-solution-mapping` | `ai-coach-engage-solution-mapping` | `ai-coach-engage-objection-handling` | ⚠️ CO-FIRE |
| sm-TC03 | "Create a solution brief for a customer who needs to automate their HR onboarding process using ServiceNow." | `ai-coach-engage-solution-mapping` | `ai-coach-engage-solution-mapping` | — | ✅ PASS |
| sm-TC04 | "What does ServiceNow's Strategic Portfolio Management product actually do? I need to explain it to a customer CTO." | `ai-coach-engage-solution-mapping` | `ai-coach-engage-solution-mapping` | — | ✅ PASS |
| sm-TC05 | "The customer's IT team is worried that ServiceNow won't integrate with their SAP system — how do I handle that objection?" | `ai-coach-engage-solution-mapping` | `ai-coach-engage-solution-mapping` | `ai-coach-engage-objection-handling` | ⚠️ CO-FIRE |

**Skill Result: 3/5 PASS · 2 co-fire · 0 FAIL**

---

### SKILL: `ai-coach-engage-mutual-plan`
| Test ID | User Statement | Expected Skill | Predicted Skill | Co-Fires | Outcome |
|---|---|---|---|---|---|
| mp-TC01 | "I need to create a mutual plan with my customer at Ford — they want a shared timeline for the implementation." | `ai-coach-engage-mutual-plan` | `ai-coach-engage-mutual-plan` | — | ✅ PASS |
| mp-TC02 | "Can you build a mutual success plan for the Acme deal that covers the next 90 days with clear milestones and owners?" | `ai-coach-engage-mutual-plan` | `ai-coach-engage-mutual-plan` | — | ✅ PASS |
| mp-TC03 | "My customer asked for a joint plan of record — what should it include and can you create one?" | `ai-coach-engage-mutual-plan` | `ai-coach-engage-mutual-plan` | — | ✅ PASS |
| mp-TC04 | "Create a customer-facing plan document that shows the steps from contract signing to go-live for the IBM deal." | `ai-coach-engage-mutual-plan` | `ai-coach-engage-mutual-plan` | — | ✅ PASS |
| mp-TC05 | "I need a shared accountability document for my customer that both sides can track against — can you make one in Excel?" | `ai-coach-engage-mutual-plan` | `ai-coach-engage-mutual-plan` | — | ✅ PASS |

**Skill Result: 5/5 PASS · 0 co-fire · 0 FAIL**

---

### SKILL: `kahani-customer-reference-agent`
| Test ID | User Statement | Expected Skill | Predicted Skill | Co-Fires | Outcome |
|---|---|---|---|---|---|
| kah-TC01 | "I need a customer story I can share with a CIO at a retail company who's evaluating ServiceNow ITSM." | `kahani-customer-reference-agent` | `kahani-customer-reference-agent` | — | ✅ PASS |
| kah-TC02 | "Find me proof points for ServiceNow's impact on employee onboarding — my customer is in financial services." | `kahani-customer-reference-agent` | `kahani-customer-reference-agent` | — | ✅ PASS |
| kah-TC03 | "Do we have any customer references for healthcare companies using ServiceNow for asset management?" | `kahani-customer-reference-agent` | `kahani-customer-reference-agent` | — | ✅ PASS |
| kah-TC04 | "My customer's CFO is skeptical about ROI — can you find me a case study with specific dollar savings?" | `kahani-customer-reference-agent` | `kahani-customer-reference-agent` | — | ✅ PASS |
| kah-TC05 | "I need three customer success stories about ServiceNow reducing IT costs that I can use in my presentation tomorrow." | `kahani-customer-reference-agent` | `kahani-customer-reference-agent` | — | ✅ PASS |

**Skill Result: 5/5 PASS · 0 co-fire · 0 FAIL**

---

### SKILL: `ai-coach-engage-discovery`
| Test ID | User Statement | Expected Skill | Predicted Skill | Co-Fires | Outcome |
|---|---|---|---|---|---|
| disc-TC01 | "I have a first call with the CIO of Target next week — what discovery questions should I ask?" | `ai-coach-engage-discovery` | `ai-coach-engage-discovery` | `ai-coach-engage-meeting-prep` | ⚠️ CO-FIRE |
| disc-TC02 | "Help me prepare my discovery agenda for the Acme opportunity — we're focused on their ITSM challenges." | `ai-coach-engage-discovery` | `ai-coach-engage-discovery` | `ai-coach-engage-meeting-prep` | ⚠️ CO-FIRE |
| disc-TC03 | "What are the best questions to ask a CFO to uncover budget and decision-making authority?" | `ai-coach-engage-discovery` | `ai-coach-engage-discovery` | — | ✅ PASS |
| disc-TC04 | "I need 8 discovery questions right now for a call in 20 minutes — the company is a manufacturing firm." | `ai-coach-engage-discovery` | `ai-coach-engage-discovery` | — | ✅ PASS |
| disc-TC05 | "I'm qualifying a new prospect in the healthcare space — what questions should I ask to understand their current state?" | `ai-coach-engage-discovery` | `ai-coach-engage-discovery` | — | ✅ PASS |

**Skill Result: 3/5 PASS · 2 co-fire · 0 FAIL**

---

### SKILL: `analytics-data-connector`
*Note: This skill has NO user-facing triggers by design. Test cases validate internal routing only.*

| Test ID | User Statement | Expected Primary Skill | Predicted Primary | Internal Connector Call | Outcome |
|---|---|---|---|---|---|
| adc-TC01 | "What's the pipeline for my territory this quarter?" | `ai-coach-universal-strategy-coach` | `ai-coach-universal-strategy-coach` | Correct (via strategy-coach) | ✅ PASS |
| adc-TC02 | "Pull the account data for Boeing before we start discovery prep." | `ai-coach-engage-discovery` | `ai-coach-engage-discovery` | Correct (via account-lookup → connector) | ✅ PASS |
| adc-TC03 | "Create a mutual plan for the Walmart deal with actual pipeline data." | `ai-coach-engage-mutual-plan` | `ai-coach-engage-mutual-plan` | Correct (via mutual-plan) | ✅ PASS |
| adc-TC04 | "What sales plays should I run for Target this quarter?" | `ai-coach-grow-sales-plays` | `ai-coach-grow-sales-plays` | Correct (via sales-plays) | ✅ PASS |
| adc-TC05 | "Analyze my uploaded account plan for Nike with current contract data." | `ai-coach-plan-account-planning` | `ai-coach-plan-account-planning` | Correct (via account-planning) | ✅ PASS |

**Skill Result: 5/5 PASS · 0 co-fire · 0 FAIL**

---

### SKILL: `servicenow-corporate-pptx`
| Test ID | User Statement | Expected Skill | Predicted Skill | Co-Fires | Outcome |
|---|---|---|---|---|---|
| snpptx-TC01 | "Create a PSR deck for my Acme customer using the ServiceNow corporate template." | `servicenow-corporate-pptx` | `servicenow-corporate-pptx` | `pptx` | ⚠️ CO-FIRE |
| snpptx-TC02 | "I need a QBR presentation for the Boeing account — use the official ServiceNow branding with the dark blue background and green accents." | `servicenow-corporate-pptx` | `servicenow-corporate-pptx` | `pptx` | ⚠️ CO-FIRE |
| snpptx-TC03 | "Build a SAM training deck using the ServiceNow corporate slide template — 13 slides." | `servicenow-corporate-pptx` | `servicenow-corporate-pptx` | `pptx` | ⚠️ CO-FIRE |
| snpptx-TC04 | "I uploaded a ServiceNow corporate deck — can you update the cover slide with my customer's name and today's date?" | `servicenow-corporate-pptx` | `servicenow-corporate-pptx` | `pptx` | ⚠️ CO-FIRE |
| snpptx-TC05 | "Create an executive briefing deck for the Nike deal in the ServiceNow corporate format with a data table showing their case trends." | `servicenow-corporate-pptx` | `servicenow-corporate-pptx` | `pptx` | ⚠️ CO-FIRE |

**Skill Result: 0/5 PASS · 5 co-fire · 0 FAIL**

---

### SKILL: `ai-coach-engage-meeting-prep`
| Test ID | User Statement | Expected Skill | Predicted Skill | Co-Fires | Outcome |
|---|---|---|---|---|---|
| mprep-TC01 | "I have a meeting with the CIO of Walmart in 30 minutes — give me quick talking points." | `ai-coach-engage-meeting-prep` | `ai-coach-engage-meeting-prep` | — | ✅ PASS |
| mprep-TC02 | "Prepare a comprehensive executive brief for my meeting with Boeing's CHRO next Tuesday about HR transformation." | `ai-coach-engage-meeting-prep` | `ai-coach-engage-meeting-prep` | — | ✅ PASS |
| mprep-TC03 | "I just finished my call with the Target team — can you help me write up a meeting recap with action items?" | `ai-coach-engage-meeting-prep` | `ai-coach-engage-meeting-prep` | — | ✅ PASS |
| mprep-TC04 | "What should I talk about in my upcoming renewal meeting with Nike?" | `ai-coach-engage-meeting-prep` | `ai-coach-engage-meeting-prep` | `ai-coach-universal-strategy-coach` | ⚠️ CO-FIRE |
| mprep-TC05 | "Give me a two-minute brief on Acme Corp before I jump on a call with their VP of IT." | `ai-coach-engage-meeting-prep` | `ai-coach-engage-meeting-prep` | — | ✅ PASS |

**Skill Result: 4/5 PASS · 1 co-fire · 0 FAIL**

---

### SKILL: `ai-coach-engage-objection-handling`
| Test ID | User Statement | Expected Skill | Predicted Skill | Co-Fires | Outcome |
|---|---|---|---|---|---|
| obj-TC01 | "I want to role play handling a procurement objection about our pricing being too high — you play the procurement manager." | `ai-coach-engage-objection-handling` | `ai-coach-engage-objection-handling` | — | ✅ PASS |
| obj-TC02 | "Can we do a practice run for my legal negotiation tomorrow? I need to practice handling contract term pushback." | `ai-coach-engage-objection-handling` | `ai-coach-engage-objection-handling` | — | ✅ PASS |
| obj-TC03 | "Let's practice — I need to get better at handling 'we're happy with our current vendor' objections." | `ai-coach-engage-objection-handling` | `ai-coach-engage-objection-handling` | — | ✅ PASS |
| obj-TC04 | "Quiz me on handling budget freeze objections. I keep fumbling that one." | `ai-coach-engage-objection-handling` | `ai-coach-engage-objection-handling` | — | ✅ PASS |
| obj-TC05 | "Simulate a tough procurement call where they're pushing back on our data security clauses." | `ai-coach-engage-objection-handling` | `ai-coach-engage-objection-handling` | — | ✅ PASS |

**Skill Result: 5/5 PASS · 0 co-fire · 0 FAIL**

---

### SKILL: `ai-coach-grow-sales-plays`
| Test ID | User Statement | Expected Skill | Predicted Skill | Co-Fires | Outcome |
|---|---|---|---|---|---|
| sp-TC01 | "What sales plays should I be running for the Boeing account right now?" | `ai-coach-grow-sales-plays` | `ai-coach-grow-sales-plays` | — | ✅ PASS |
| sp-TC02 | "What's the hero play for Target this quarter?" | `ai-coach-grow-sales-plays` | `ai-coach-grow-sales-plays` | — | ✅ PASS |
| sp-TC03 | "What should I be selling to Walmart — what's the next best play?" | `ai-coach-grow-sales-plays` | `ai-coach-grow-sales-plays` | `ai-coach-universal-strategy-coach` | ⚠️ CO-FIRE |
| sp-TC04 | "Can you find me the pitch deck for the ITSM industry play? I need the SSC link." | `ai-coach-grow-sales-plays` | `ai-coach-grow-sales-plays` | `pptx` | ⚠️ CO-FIRE |
| sp-TC05 | "I uploaded a sales play deck — can you update the customer name and case study section for the Nike account?" | `ai-coach-grow-sales-plays` | `ai-coach-grow-sales-plays` | `pptx` | ⚠️ CO-FIRE |

**Skill Result: 2/5 PASS · 3 co-fire · 0 FAIL**

---

### SKILL: `ai-coach-plan-account-planning`
| Test ID | User Statement | Expected Skill | Predicted Skill | Co-Fires | Outcome |
|---|---|---|---|---|---|
| ap-TC01 | "I uploaded my account plan for Boeing — can you analyze it and tell me what's missing?" | `ai-coach-plan-account-planning` | `ai-coach-plan-account-planning` | — | ✅ PASS |
| ap-TC02 | "Update my account plan for Walmart with the latest contract data and pipeline information." | `ai-coach-plan-account-planning` | `ai-coach-plan-account-planning` | — | ✅ PASS |
| ap-TC03 | "I need to do account planning for my top three accounts before the QBR — can you help?" | `ai-coach-plan-account-planning` | `ai-coach-plan-account-planning` | `ai-coach-universal-strategy-coach` | ⚠️ CO-FIRE |
| ap-TC04 | "Can you review my uploaded account plan and suggest updates to the strategic objectives section?" | `ai-coach-plan-account-planning` | `ai-coach-plan-account-planning` | — | ✅ PASS |
| ap-TC05 | "I need to update the challenges and opportunities sections of my Nike account plan — I uploaded it." | `ai-coach-plan-account-planning` | `ai-coach-plan-account-planning` | — | ✅ PASS |

**Skill Result: 4/5 PASS · 1 co-fire · 0 FAIL**

---

### SKILL: `ai-coach-universal-compete-frontier-ai`
| Test ID | User Statement | Expected Skill | Predicted Skill | Co-Fires | Outcome |
|---|---|---|---|---|---|
| cfa-TC01 | "My customer is considering building their own AI workflows on OpenAI's API instead of buying ServiceNow — how do I compete?" | `ai-coach-universal-compete-frontier-ai` | `ai-coach-universal-compete-frontier-ai` | — | ✅ PASS |
| cfa-TC02 | "The CIO told me they're evaluating Google Gemini as their enterprise AI platform — what's our response?" | `ai-coach-universal-compete-frontier-ai` | `ai-coach-universal-compete-frontier-ai` | — | ✅ PASS |
| cfa-TC03 | "We're losing to Anthropic Claude in an AI agent evaluation — help me reposition ServiceNow." | `ai-coach-universal-compete-frontier-ai` | `ai-coach-universal-compete-frontier-ai` | — | ✅ PASS |
| cfa-TC04 | "My customer says they'd rather build on a foundation model than buy ServiceNow AI — how do I handle this?" | `ai-coach-universal-compete-frontier-ai` | `ai-coach-universal-compete-frontier-ai` | `ai-coach-universal-strategy-coach` | ⚠️ CO-FIRE |
| cfa-TC05 | "Create a compete card comparing ServiceNow AI to OpenAI for an enterprise use case." | `ai-coach-universal-compete-frontier-ai` | `ai-coach-universal-compete-frontier-ai` | — | ✅ PASS |

**Skill Result: 4/5 PASS · 1 co-fire · 0 FAIL**

---

### SKILL: `ai-coach-universal-compete-microsoft`
| Test ID | User Statement | Expected Skill | Predicted Skill | Co-Fires | Outcome |
|---|---|---|---|---|---|
| cms-TC01 | "My customer is consolidating on Microsoft 365 and thinks Copilot can replace ServiceNow — how do I respond?" | `ai-coach-universal-compete-microsoft` | `ai-coach-universal-compete-microsoft` | — | ✅ PASS |
| cms-TC02 | "The CIO wants to use Power Platform instead of ServiceNow for workflow automation — what's my compete strategy?" | `ai-coach-universal-compete-microsoft` | `ai-coach-universal-compete-microsoft` | — | ✅ PASS |
| cms-TC03 | "Give me a compete card for ServiceNow vs Microsoft Copilot for IT service management." | `ai-coach-universal-compete-microsoft` | `ai-coach-universal-compete-microsoft` | `ai-coach-universal-compete-frontier-ai` | ⚠️ CO-FIRE |
| cms-TC04 | "My customer is evaluating Agent 365 for their employee service center — how does ServiceNow compare?" | `ai-coach-universal-compete-microsoft` | `ai-coach-universal-compete-microsoft` | — | ✅ PASS |
| cms-TC05 | "The deal is at risk because Microsoft is throwing in Power Automate for free — how do I defend our position?" | `ai-coach-universal-compete-microsoft` | `ai-coach-universal-compete-microsoft` | — | ✅ PASS |

**Skill Result: 4/5 PASS · 1 co-fire · 0 FAIL**

---

### SKILL: `ai-coach-universal-compete-salesforce`
| Test ID | User Statement | Expected Skill | Predicted Skill | Co-Fires | Outcome |
|---|---|---|---|---|---|
| csf-TC01 | "Salesforce is in my deal at Boeing — what's our compete strategy?" | `ai-coach-universal-compete-salesforce` | `ai-coach-universal-compete-salesforce` | — | ✅ PASS |
| csf-TC02 | "Give me a compete card: ServiceNow vs Salesforce for CRM and customer service." | `ai-coach-universal-compete-salesforce` | `ai-coach-universal-compete-salesforce` | `ai-coach-crm-now-next` | ⚠️ CO-FIRE |
| csf-TC03 | "The customer's Salesforce team is pushing Salesforce Service Cloud as an alternative to ServiceNow CSM — how do I respond?" | `ai-coach-universal-compete-salesforce` | `ai-coach-universal-compete-salesforce` | — | ✅ PASS |
| csf-TC04 | "My customer just told me Salesforce gave them a huge discount to stay — what do I do?" | `ai-coach-universal-compete-salesforce` | `ai-coach-universal-compete-salesforce` | `ai-coach-universal-strategy-coach` | ⚠️ CO-FIRE |
| csf-TC05 | "What are the Four Plays against Salesforce and when do I use each one?" | `ai-coach-universal-compete-salesforce` | `ai-coach-universal-compete-salesforce` | — | ✅ PASS |

**Skill Result: 3/5 PASS · 2 co-fire · 0 FAIL**

---

### SKILL: `ai-coach-universal-partner-rtm`
| Test ID | User Statement | Expected Skill | Predicted Skill | Co-Fires | Outcome |
|---|---|---|---|---|---|
| rtm-TC01 | "Should I bring a partner into the Boeing deal and if so, which type of partner?" | `ai-coach-universal-partner-rtm` | `ai-coach-universal-partner-rtm` | — | ✅ PASS |
| rtm-TC02 | "What's the difference between a C&I partner and a Reseller partner for ServiceNow deals?" | `ai-coach-universal-partner-rtm` | `ai-coach-universal-partner-rtm` | — | ✅ PASS |
| rtm-TC03 | "My customer wants to work with Accenture on the implementation — how does that change my go-to-market approach?" | `ai-coach-universal-partner-rtm` | `ai-coach-universal-partner-rtm` | — | ✅ PASS |
| rtm-TC04 | "Should I run this deal through AWS Marketplace or direct? The customer is heavily AWS-invested." | `ai-coach-universal-partner-rtm` | `ai-coach-universal-partner-rtm` | — | ✅ PASS |
| rtm-TC05 | "How do I select the right partner for a mid-market customer who needs both implementation and ongoing support?" | `ai-coach-universal-partner-rtm` | `ai-coach-universal-partner-rtm` | — | ✅ PASS |

**Skill Result: 5/5 PASS · 0 co-fire · 0 FAIL**

---

### SKILL: `servicenow-brand-standards`
| Test ID | User Statement | Expected Skill | Predicted Skill | Co-Fires | Outcome |
|---|---|---|---|---|---|
| snb-TC01 | "Make sure this Word document follows ServiceNow brand guidelines — the right fonts, colors, and formatting." | `servicenow-brand-standards` | `servicenow-brand-standards` | `docx` | ⚠️ CO-FIRE |
| snb-TC02 | "What colors and fonts does ServiceNow use in its official documents?" | `servicenow-brand-standards` | `servicenow-brand-standards` | — | ✅ PASS |
| snb-TC03 | "I need to create an HTML page for internal use that matches ServiceNow's brand identity." | `servicenow-brand-standards` | `servicenow-brand-standards` | `frontend-design` | ⚠️ CO-FIRE |
| snb-TC04 | "Does this Excel report I made follow ServiceNow's visual standards? Check it against brand guidelines." | `servicenow-brand-standards` | `servicenow-brand-standards` | `xlsx` | ⚠️ CO-FIRE |
| snb-TC05 | "What are the rules for using the Wasabi Green color in ServiceNow documents?" | `servicenow-brand-standards` | `servicenow-brand-standards` | — | ✅ PASS |

**Skill Result: 2/5 PASS · 3 co-fire · 0 FAIL**

---

### SKILL: `smart-brevity-docx`
| Test ID | User Statement | Expected Skill | Predicted Skill | Co-Fires | Outcome |
|---|---|---|---|---|---|
| sb-TC01 | "Write a Word document summary of our Q3 results — keep it tight, no fluff, maximum 3 pages." | `smart-brevity-docx` | `smart-brevity-docx` | `docx` | ⚠️ CO-FIRE |
| sb-TC02 | "Create a concise memo in Word about the new IT security policy — leadership needs to be able to read it in under 2 minutes." | `smart-brevity-docx` | `smart-brevity-docx` | `docx` | ⚠️ CO-FIRE |
| sb-TC03 | "Make me a Word document brief for my executive sponsor — it needs to be scannable and to the point." | `smart-brevity-docx` | `smart-brevity-docx` | `docx` | ⚠️ CO-FIRE |
| sb-TC04 | "I need a Word document proposal — but please apply smart brevity principles to keep it under 5 pages." | `smart-brevity-docx` | `smart-brevity-docx` | `docx` | ⚠️ CO-FIRE |
| sb-TC05 | "Turn this 15-page report into a tight Word document that hits the key points only." | `smart-brevity-docx` | `smart-brevity-docx` | `docx` | ⚠️ CO-FIRE |

**Skill Result: 0/5 PASS · 5 co-fire · 0 FAIL**

---

### SKILL: `value-melody-coach`
| Test ID | User Statement | Expected Skill | Predicted Skill | Co-Fires | Outcome |
|---|---|---|---|---|---|
| vmc-TC01 | "I need to build a business case for ServiceNow at Walmart — they need to justify the investment to their CFO." | `value-melody-coach` | `value-melody-coach` | — | ✅ PASS |
| vmc-TC02 | "Create a Strategic Value Perspective for my executive meeting at Boeing next week." | `value-melody-coach` | `value-melody-coach` | — | ✅ PASS |
| vmc-TC03 | "My customer wants to see a BVA — can you help me build one for the Nike ITSM opportunity?" | `value-melody-coach` | `value-melody-coach` | — | ✅ PASS |
| vmc-TC04 | "Help me build a value story for the Target account that connects ServiceNow to their strategic priorities." | `value-melody-coach` | `value-melody-coach` | `ai-coach-universal-strategy-coach` | ⚠️ CO-FIRE |
| vmc-TC05 | "I have a validated financial model for the Acme deal but I need help with the strategic framing and storytelling." | `value-melody-coach` | `value-melody-coach` | — | ✅ PASS |

**Skill Result: 4/5 PASS · 1 co-fire · 0 FAIL**

---

### SKILL: `ai-coach-universal-strategy-coach`
| Test ID | User Statement | Expected Skill | Predicted Skill | Co-Fires | Outcome |
|---|---|---|---|---|---|
| sc-TC01 | "I have a massive renewal at Boeing coming up in 90 days — where do I even start?" | `ai-coach-universal-strategy-coach` | `ai-coach-universal-strategy-coach` | `ai-coach-engage-meeting-prep` | ⚠️ CO-FIRE |
| sc-TC02 | "I want to grow the Walmart account from $2M to $5M ACV this year — what's my strategy?" | `ai-coach-universal-strategy-coach` | `ai-coach-universal-strategy-coach` | — | ✅ PASS |
| sc-TC03 | "I'm trying to close a competitive deal against Salesforce at Target — what should I be doing right now?" | `ai-coach-universal-strategy-coach` | `ai-coach-universal-strategy-coach` | `ai-coach-universal-compete-salesforce` | ⚠️ CO-FIRE |
| sc-TC04 | "My deal has been stuck at proposal stage for 3 months — help me figure out how to get it moving." | `ai-coach-universal-strategy-coach` | `ai-coach-universal-strategy-coach` | — | ✅ PASS |
| sc-TC05 | "I just got assigned a new territory — how should I approach building my pipeline from scratch?" | `ai-coach-universal-strategy-coach` | `ai-coach-universal-strategy-coach` | — | ✅ PASS |

**Skill Result: 3/5 PASS · 2 co-fire · 0 FAIL**

---

### SKILL: `skill-creator`
| Test ID | User Statement | Expected Skill | Predicted Skill | Co-Fires | Outcome |
|---|---|---|---|---|---|
| sc2-TC01 | "I want to create a new skill for handling customer renewal conversations — can you help me build it from scratch?" | `skill-creator` | `skill-creator` | `skill-development` | ⚠️ CO-FIRE |
| sc2-TC02 | "The objection handling skill isn't performing well — can you help me improve it?" | `skill-creator` | `skill-creator` | — | ✅ PASS |
| sc2-TC03 | "I need to run an evaluation to see if the meeting-prep skill is triggering correctly — how do I do that?" | `skill-creator` | `skill-creator` | — | ✅ PASS |
| sc2-TC04 | "Can you benchmark how consistently the discovery skill triggers across 10 different user statements?" | `skill-creator` | `skill-creator` | — | ✅ PASS |
| sc2-TC05 | "I want to measure whether my rewritten skill descriptions actually reduce conflicts — can you design a test for that?" | `skill-creator` | `skill-creator` | — | ✅ PASS |

**Skill Result: 4/5 PASS · 1 co-fire · 0 FAIL**

---

## Consolidated Results Table

| Skill | Total | ✅ PASS | ⚠️ Co-Fire | ❌ FAIL | Clean Pass % |
|---|---|---|---|---|---|
| `docx` | 5 | 3 | 2 | 0 | 60% |
| `pdf` | 5 | 5 | 0 | 0 | 100% |
| `pptx` | 5 | 4 | 1 | 0 | 80% |
| `xlsx` | 5 | 5 | 0 | 0 | 100% |
| `product-self-knowledge` | 5 | 5 | 0 | 0 | 100% |
| `frontend-design` | 5 | 5 | 0 | 0 | 100% |
| `account-lookup` | 5 | 5 | 0 | 0 | 100% |
| `ai-coach-crm-now-next` | 5 | 5 | 0 | 0 | 100% |
| `ai-coach-crm-pursuit-plan` | 5 | 3 | 2 | 0 | 60% |
| `value-melody-analyst` | 5 | 3 | 2 | 0 | 60% |
| `ai-coach-engage-solution-mapping` | 5 | 3 | 2 | 0 | 60% |
| `ai-coach-engage-mutual-plan` | 5 | 5 | 0 | 0 | 100% |
| `kahani-customer-reference-agent` | 5 | 5 | 0 | 0 | 100% |
| `ai-coach-engage-discovery` | 5 | 3 | 2 | 0 | 60% |
| `analytics-data-connector` | 5 | 5 | 0 | 0 | 100% |
| `servicenow-corporate-pptx` | 5 | 0 | 5 | 0 | 0% |
| `ai-coach-engage-meeting-prep` | 5 | 4 | 1 | 0 | 80% |
| `ai-coach-engage-objection-handling` | 5 | 5 | 0 | 0 | 100% |
| `ai-coach-grow-sales-plays` | 5 | 2 | 3 | 0 | 40% |
| `ai-coach-plan-account-planning` | 5 | 4 | 1 | 0 | 80% |
| `ai-coach-universal-compete-frontier-ai` | 5 | 4 | 1 | 0 | 80% |
| `ai-coach-universal-compete-microsoft` | 5 | 4 | 1 | 0 | 80% |
| `ai-coach-universal-compete-salesforce` | 5 | 3 | 2 | 0 | 60% |
| `ai-coach-universal-partner-rtm` | 5 | 5 | 0 | 0 | 100% |
| `servicenow-brand-standards` | 5 | 2 | 3 | 0 | 40% |
| `smart-brevity-docx` | 5 | 0 | 5 | 0 | 0% |
| `value-melody-coach` | 5 | 4 | 1 | 0 | 80% |
| `ai-coach-universal-strategy-coach` | 5 | 3 | 2 | 0 | 60% |
| `skill-creator` | 5 | 4 | 1 | 0 | 80% |
| **TOTAL** | **145** | **108** | **37** | **0** | **74.5%** |

---

## Known Conflict Patterns Observed

| Conflict Group | Confirmed by Tests | Affected Test Cases |
|---|---|---|
| `docx` + `smart-brevity-docx` (Group 1) | ✅ YES | docx-TC01, TC03; sb-TC01–TC05 (7 co-fires) |
| Brand standards fires on doc creation (Group 2) | ✅ YES | snb-TC01, TC03, TC04 (3 co-fires) |
| `pptx` + `servicenow-corporate-pptx` (Group 3) | ✅ YES | snpptx-TC01–TC05 (5 co-fires) |
| `value-melody-coach` + `value-melody-analyst` (Group 4) | ✅ YES | vma-TC02, TC05 (2 co-fires) |
| `meeting-prep` + `discovery` (Group 5) | ✅ YES | disc-TC01, TC02 (2 co-fires) |
| `solution-mapping` + `objection-handling` (Group 6) | ✅ YES | sm-TC02, TC05 (2 co-fires) |
| `compete-microsoft` + `compete-frontier-ai` (Group 7) | ✅ YES | cms-TC03 (1 co-fire) |
| `strategy-coach` over-fires on deliverable requests (Group 8) | ✅ YES | crm-pp-TC01, sp-TC03, ap-TC03, sc-TC01, sc-TC03, mprep-TC04, cfa-TC04, csf-TC04, vmc-TC04 (9 co-fires) |
| `skill-creator` + `skill-development` (Group 9) | ✅ YES | sc2-TC01 (1 co-fire) |
