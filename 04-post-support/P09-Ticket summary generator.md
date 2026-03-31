# 📄 P09 · Ticket conversation summary and documentation

**Section:** 04 — Post-Support  
**Workflow step:** Step 1 of 2 (follows response → feeds into records and analytics)  
**Current version:** v1.2  
**Status:** ✅ Tested  
**Last updated:** March 2026  

---

## 📌 Prompt Text (v1.2 — current)

```
You are a customer support documentation assistant.

Summarise the following customer interaction into a structured internal record.

Conversation transcript: [CONVERSATION_HISTORY]

Include:
1. Issue summary (1–2 sentences)
2. Key actions taken (bullet points)
3. Final resolution status (resolved / pending / escalated)
4. Any follow-up required

Tone: concise, factual, and internal-use only  
Length: maximum 100 words  

Rules:
- Do not include unnecessary details
- Do not assume missing information
- If unclear, write: "Insufficient data — follow-up required"
- Focus only on relevant information for internal records

Output format:

{
  "issue_summary": "",
  "actions_taken": [],
  "status": "",
  "follow_up": ""
}
```

---

## 🏢 Intended Workflow or Task

This prompt is **Step 1 in the post-support workflow** and ensures every interaction is properly documented.

- **Trigger:** Runs after response is sent (P04/P05)  
- **Integration:** Output stored in CRM/ticketing system  
- **Timing:** Immediately after resolution or closure  

**Next step:**
- P10 (Follow-up message)  
- Data used for analytics and reporting  

Customer interaction completed → [P09 RUNS]  
→ Structured summary stored in CRM  
→ Used for analytics + follow-up (P10)  

---

## ❗ Problem Being Solved

Agents manually summarise conversations, taking **2–5 minutes per ticket**.

At ~200 tickets/day:

- 6–16 hours/day spent on documentation  
- Inconsistent summaries  
- Missing records  
- Poor historical analysis  

**Pain points addressed:**

- Time-consuming documentation  
- Lack of standardisation  
- Poor visibility into past interactions  

---

## ⚡ Automation Potential

**Level:** High  

| Dimension | Assessment |
|----------|-----------|
| Repetitiveness | Very high — every ticket |
| Data availability | Fully available in transcript |
| Human judgment needed | Low–Medium |
| Integration possibility | Direct CRM storage |
| Estimated time saving | ~75% |

**Human-in-the-loop role:**
- Review complex cases  

**Scaling note:**  
Improves data quality, reporting, and operational insights.

---

## ⚠️ Risks and Limitations

| Risk | Level | Mitigation |
|------|------|-----------|
| Loss of details | Medium | Structured format + review |
| Incorrect status | Medium | Validate with system |
| Over-simplification | Medium | Allow manual edits |
| Misinterpretation | Low | Use full transcript |

**Overall risk rating:** MEDIUM  

---

## 🔄 Version History

### v1.0 — Initial draft  
**Date:** 20 March 2026  

- Unstructured summaries  
- Hard to use  

**Lesson:** Need structure  

---

### v1.1 — Added structured output  
**Date:** 23 March 2026  

- Improved clarity  
- Issues with missing data  

**Lesson:** Need fallback  

---

### v1.2 — Added constraints + fallback ✅ Current  
**Date:** 26 March 2026  

- Structured + reliable  
- Better integration  

**Observed effect:**  
Improved data quality  

---

## 📊 A/B Test Results

**Test date:** 28 March 2026 | Sample: 40 interactions  

| Criteria | v1.0 | v1.2 |
|----------|------|------|
| Readability | 2.5/5 | 4.7/5 |
| Consistency | 2/5 | 4.8/5 |
| Completeness | 2.5/5 | 4.6/5 |
| Reporting value | 2/5 | 4.7/5 |
| **Overall** | **2.2/5** | **4.7/5** |

---

## 🔗 Related Prompts

**Previous:**
- P04 — Response draft generator  
- P05 — Tone adjuster  

**Next:**
- P10 — Follow-up message generator  

**Used for:**
- Analytics, reporting, record-keeping  

**Parent section:** 04 — Post-Support  
**Library index:** README.md  
