# 📄 P08 · Escalation summary generation

**Section:** 03 — Escalation Support  
**Workflow step:** Step 2 of 2 (follows escalation decision → feeds into manager review and action)  
**Current version:** v1.2  
**Status:** ✅ Tested  
**Last updated:** March 2026  

---

## 📌 Prompt Text (v1.2 — current)

```
You are a customer service escalation specialist.

Using ONLY the information provided below, write a structured escalation summary for a supervisor.

Do not infer, assume, or add information not explicitly stated.

Inputs:
Customer message: [CUSTOMER_MESSAGE]
Category: [CATEGORY_FROM_P01]
Priority: [PRIORITY_FROM_P03]
Sentiment: [SENTIMENT_FROM_P02]
Intensity: [INTENSITY_FROM_P02]
Previous actions taken: [OPTIONAL_AGENT_NOTES]

Required sections:
1. Issue summary (2–3 sentences)
2. Key facts (bullet points)
3. Actions already taken
4. Current status
5. Recommended next steps

Tone: factual, neutral, and concise  
Length: maximum 150 words  

If any section lacks sufficient data, write:
"Insufficient data — follow-up required"
```

---

## 🏢 Intended Workflow or Task

This prompt is **Step 2 in the escalation workflow** and prepares a structured briefing for supervisors.

- **Trigger:** Runs when P07 returns "Yes"  
- **Actor:** Agent or automated system generates summary  
- **Integration:** Output sent to supervisor dashboard/queue  
- **Timing:** Immediately after escalation decision  

**Next step:**
- Supervisor reviews summary  
- Decision taken (refund, compensation, legal escalation, etc.)  

Ticket processed → P07 (escalate = Yes) → [P08 RUNS]  
→ Summary generated  
→ Supervisor reviews → Takes action  

---

## ❗ Problem Being Solved

When issues are escalated, agents must manually prepare summaries.

This takes **5–10 minutes per case**, and summaries are often:

- Inconsistent  
- Missing key details  
- Hard to interpret quickly  

At scale:

- Delays in escalation handling  
- Increased workload  
- Risk of incorrect decisions  

---

## ⚡ Automation Potential

**Level:** Medium  

| Dimension | Assessment |
|----------|-----------|
| Repetitiveness | High — every escalation needs summary |
| Data availability | Depends on ticket completeness |
| Human judgment needed | High — accuracy critical |
| Integration possibility | Direct escalation system input |
| Estimated time saving | ~60% |

**Human-in-the-loop role:**
- Supervisors review summaries  
- Agents refine if needed  

**Scaling note:**  
Improves decision speed and consistency under high load.

---

## ⚠️ Risks and Limitations

| Risk | Level | Mitigation |
|------|------|-----------|
| Model infers missing info | High | Strict grounding rule |
| Incomplete input data | Medium | Use fallback message |
| Oversimplification | Medium | Supervisor review |
| Incorrect recommendations | High | Treat as draft only |

**Overall risk rating:** HIGH  

---

## 🔄 Version History

### v1.0 — Initial draft  
**Date:** 19 March 2026  

- Unstructured summaries  
- Missing key details  

**Lesson:** Need structure  

---

### v1.1 — Added structured sections  
**Date:** 22 March 2026  

- Improved readability  
- Still included assumptions  

**Lesson:** Restrict inference  

---

### v1.2 — Added grounding + fallback ✅ Current  
**Date:** 25 March 2026  

- Enforced factual output  
- Added missing data fallback  

**Observed effect:**  
Better trust and faster decisions  

---

## 📊 A/B Test Results

**Test date:** 27 March 2026 | Sample: 30 cases  

| Criteria | v1.0 | v1.2 |
|----------|------|------|
| Readability | 2.5/5 | 4.7/5 |
| Completeness | 2/5 | 4.6/5 |
| Accuracy | 2/5 | 4.8/5 |
| Usability | 2/5 | 4.7/5 |
| **Overall** | **2.1/5** | **4.7/5** |

---

## 🔗 Related Prompts

- Previous: P07 — Escalation decision  
- Triggered by: High-priority tickets (P03)  
- Used by: Supervisor decision workflow  
- Parent section: 03 — Escalation Support  
- Library index: README.md  
