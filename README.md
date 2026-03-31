# 📚 Prompt Library — Customer Service Automation

> **Assessment 1 | AI for Business**  
> Student: Shashank Komari | Business Field: Customer Service Automation (Online Retail)  
> Model tested on: GPT-5.3  
> Last updated: March 2026

---

## What This Library Does

This prompt library supports workflow automation in **customer service operations for an online retail business**. It contains **10 documented, tested, and iterated prompts** organised by the business function they support.

Each prompt entry follows the same structure:
- The exact prompt text (with placeholders)
- The workflow task it supports
- The problem it solves
- Its automation potential
- Known risks and mitigations
- Version history and test results

---

## 📂 Folder Structure

<pre>
prompt-library/
│
├── README.md                        ← You are here (library index)
│
├── 01-ticket-intake/
│   ├── README.md
│   ├── P01-complaint-classification.md
│   ├── P02-sentiment-detection.md
│   └── P03-priority-assignment.md
│
├── 02-response-handling/
│   ├── README.md
│   ├── P04-response-draft.md
│   ├── P05-tone-adjuster.md
│   └── P06-faq-answer.md
│
├── 03-escalation-support/
│   ├── README.md
│   ├── P07-escalation-decision.md
│   └── P08-escalation-summary.md
│
└── 04-post-support/
    ├── README.md
    ├── P09-ticket-summary.md
    └── P10-follow-up.md
</pre>

---

## 📊 Library Summary Table

| ID | Prompt Name | Workflow | Automation Level | Risk Level | Status |
|----|-------------|----------|-----------------|------------|--------|
| P01 | Complaint classification | Ticket intake | Very High | Medium | ✅ Tested |
| P02 | Sentiment detection | Ticket intake | Very High | Low | ✅ Tested |
| P03 | Priority assignment | Ticket intake | High | Medium | ✅ Tested |
| P04 | Response draft generator | Response handling | High | Medium | ✅ Tested |
| P05 | Tone adjustment | Response handling | Medium | Low | ✅ Tested |
| P06 | FAQ answer generator | Response handling | Very High | Medium | ✅ Tested |
| P07 | Escalation decision | Escalation support | Medium | High | ✅ Tested |
| P08 | Escalation summary | Escalation support | Medium | High | ✅ Tested |
| P09 | Ticket summary generator | Post-support | High | Low | ✅ Tested |
| P10 | Follow-up message generator | Post-support | High | Low | ✅ Tested |

**Automation levels:** Very High / High / Medium / Low  
**Risk levels:** High (always needs human review) / Medium (spot-check recommended) / Low (can automate with audit)

---

## 🔗 Prompt Chaining Map

Some prompts in this library are designed to work in sequence. The chains below show how outputs from one prompt feed the next.


CUSTOMER SUPPORT CHAIN
P01 (Complaint classification) → P02 (Sentiment detection) → P03 (Priority assignment) → P04 (Response draft generator) → P05 (Tone adjustment)

ESCALATION CHAIN
P03 (Priority assignment) → P07 (Escalation decision) → P08 (Escalation summary)

KNOWLEDGE SUPPORT CHAIN
P06 (FAQ answer generator) → P04 (Response draft generator)

POST-SUPPORT CHAIN
P04 (Response draft generator) → P09 (Ticket summary generator) → P10 (Follow-up message generator)


---

## ⚙️ Prompting Strategies Used

| Strategy | Prompts | Why chosen |
|----------|---------|------------|
| RACE framework (Role–Action–Context–Evaluation) | P01, P04, P10 | Ensures structured and consistent outputs |
| Grounding constraint ("use only provided data") | P06, P08 | Prevents hallucination and ensures factual accuracy |
| JSON output format | P01, P03 | Enables CRM/system integration |
| Word/format limits | All | Ensures output is concise and production-ready |
| Step-by-step reasoning | P02, P07 | Improves decision-making accuracy |

---

## 📝 Iteration Evidence

All prompt versions are documented and refined through iterative testing. See individual prompt files for version histories.  
**Commit history = version log** — each version reflects improvements made during testing.

| Prompt | Versions | Key improvement |
|--------|----------|----------------|
| P01 | v1.0 → v1.2 | Added structured categories and JSON output for automation |
| P03 | v1.0 → v1.1 | Introduced priority rules to improve consistency |
| P04 | v1.0 → v1.2 | Added tone constraints and structured response format |
| P05 | v1.0 → v1.2 | Restricted edits to tone only to preserve meaning |
| P06 | v1.0 → v1.1 | Added grounding constraint to prevent hallucination |
| P07 | v1.0 → v1.2 | Added escalation criteria and conservative decision rules |

---

