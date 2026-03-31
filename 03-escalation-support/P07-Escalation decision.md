# 📄 P07 · Escalation decision and routing

**Section:** 03 — Escalation Support  
**Workflow step:** Step 1 of 2 (feeds into escalation summary → manager review)  
**Current version:** v1.2  
**Status:** ✅ Tested  
**Last updated:** March 2026  

---

## 📌 Prompt Text (v1.2 — current)

```
You are a customer service escalation assistant for an online retail company.

Determine whether the following customer issue should be escalated to a supervisor.

Inputs:
Category: [CATEGORY_FROM_P01]
Sentiment: [SENTIMENT_FROM_P02]
Intensity: [INTENSITY_FROM_P02]
Priority: [PRIORITY_FROM_P03]
Customer message: [CUSTOMER_MESSAGE]

Escalation criteria:
- High priority issues
- Strong negative sentiment with high intensity
- Legal threats, complaints about discrimination, or financial loss
- Repeated unresolved issues

Output:

{
  "escalate": "[Yes / No]",
  "reason": "[one short sentence]"
}

Rules:
- Be conservative: escalate if there is any risk or uncertainty
- Do not assume information not present
- Keep the reason under 20 words
- Do not add text outside JSON
```

---

## 🏢 Intended Workflow or Task

This prompt is **Step 1 in the escalation workflow** and determines whether a ticket requires **supervisor intervention**.

- **Trigger:** Runs after P03 (Priority assignment)  
- **Integration:** Output routes tickets to supervisor queue in CRM  
- **Timing:** Immediately after prioritisation  

**Next step:**
- If Yes → P08 (Escalation summary)  
- If No → Continue with P04/P05  

Ticket processed → P01 → P02 → P03 → [P07 RUNS]  
→ escalate = Yes → P08 triggered  
→ escalate = No → continue workflow  

---

## ❗ Problem Being Solved

Agents often struggle to decide when to escalate issues under time pressure.

At ~200 tickets/day:

- Critical issues may not be escalated  
- Minor issues may be escalated unnecessarily  
- Inconsistent decision-making  

**Pain points addressed:**

- Lack of clear escalation criteria  
- Delayed handling of high-risk cases  
- Increased supervisor workload  

This leads to slower resolution and potential risk exposure.

---

## ⚡ Automation Potential

**Level:** Medium  

| Dimension | Assessment |
|----------|-----------|
| Repetitiveness | High — applied to many tickets |
| Data availability | Available from earlier prompts |
| Human judgment needed | High — risk-based |
| Integration possibility | Direct CRM routing |
| Estimated time saving | ~50% |

**Human-in-the-loop role:**
- Supervisors validate escalated cases  
- Agents can override decisions  

**Scaling note:**  
Improves speed for critical issues and reduces unnecessary escalation.

---

## ⚠️ Risks and Limitations

| Risk | Level | Mitigation |
|------|------|-----------|
| Failure to escalate critical issues | High | Conservative rule |
| Over-escalation | Medium | Clear criteria |
| Misinterpretation of tone | Medium | Use sentiment + intensity |
| Over-reliance on automation | High | Mandatory review |

**Overall risk rating:** HIGH  

---

## 🔄 Version History

### v1.0 — Initial draft  
**Date:** 18 March 2026  

- Inconsistent decisions  
- No justification  

**Lesson:** Need criteria  

---

### v1.1 — Added escalation criteria  
**Date:** 21 March 2026  

- Improved decisions  
- Still inconsistent in edge cases  

**Lesson:** Include more signals  

---

### v1.2 — Added structured inputs + conservative rule ✅ Current  
**Date:** 24 March 2026  

- Combined multiple inputs  
- Added safety rule  

**Observed effect:**  
Better detection of high-risk cases  

---

## 📊 A/B Test Results

**Test date:** 26 March 2026 | Sample: 40 tickets  

| Criteria | v1.0 | v1.2 |
|----------|------|------|
| Accuracy | 2.5/5 | 4.5/5 |
| Consistency | 2/5 | 4.6/5 |
| Critical detection | 2/5 | 4.7/5 |
| Trust | 2/5 | 4.5/5 |
| **Overall** | **2.1/5** | **4.6/5** |

---

## 🔗 Related Prompts

**Previous:**
- P03 — Priority assignment  
- P02 — Sentiment detection  

**Next:**
- P08 — Escalation summary  

**Alternative path:**
- If not escalated → P04 — Response draft generator  

**Parent section:** 03 — Escalation Support  
**Library index:** README.md  
