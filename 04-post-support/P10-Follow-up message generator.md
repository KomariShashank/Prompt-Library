# 📄 P10 · Follow-up message generation and customer satisfaction check

**Section:** 04 — Post-Support  
**Workflow step:** Step 2 of 2 (final step in customer support lifecycle)  
**Current version:** v1.2  
**Status:** ✅ Tested  
**Last updated:** March 2026  

---

## 📌 Prompt Text (v1.2 — current)

```
You are a customer support follow-up assistant for an online retail company.

Write a follow-up message to the customer after their issue has been addressed.

Context:
Issue summary: [ISSUE_SUMMARY_FROM_P09]  
Resolution status: [STATUS_FROM_P09]

Your message should:
1. Confirm that the issue has been addressed
2. Ask if the customer is satisfied with the resolution
3. Offer further assistance if needed
4. Maintain a polite and friendly tone

Guidelines:
- Keep the message concise (max 80 words)
- Be empathetic and customer-focused
- Do not include internal or technical details
- Avoid generic phrases

Output only the final message text.
```

---

## 🏢 Intended Workflow or Task

This prompt is the **final step in the customer service workflow** and ensures post-resolution engagement.

- **Trigger:** Runs after ticket is resolved and summarised (P09)  
- **Actor:** System or agent sends follow-up  
- **Integration:** Sent via email/chat system  
- **Timing:** Typically 24–48 hours after resolution  

**Next step:**
- Customer response may reopen ticket  
- Data used for CSAT tracking  

Issue resolved → P09 (summary created) → [P10 RUNS]  
→ Follow-up message sent  
→ Customer feedback received  

---

## ❗ Problem Being Solved

Follow-ups are often inconsistent or skipped.

At ~200 tickets/day:

- Customers feel ignored after resolution  
- Missed satisfaction checks  
- Reduced retention  

**Pain points addressed:**

- No standard follow-up process  
- Poor post-resolution experience  
- Lack of feedback collection  

---

## ⚡ Automation Potential

**Level:** High  

| Dimension | Assessment |
|----------|-----------|
| Repetitiveness | Very high |
| Data availability | Available from P09 |
| Human judgment needed | Low |
| Integration possibility | Direct CRM/email integration |
| Estimated time saving | ~80% |

**Human-in-the-loop role:**
- Review sensitive/high-priority cases  

**Scaling note:**  
Improves CSAT, retention, and feedback collection.

---

## ⚠️ Risks and Limitations

| Risk | Level | Mitigation |
|------|------|-----------|
| Generic/robotic message | Medium | Use P09 context |
| Follow-up before resolution | High | Trigger only after confirmed closure |
| Over-contacting customers | Medium | Limit to one follow-up |
| Misalignment with expectations | Low | Offer further help |

**Overall risk rating:** MEDIUM  

---

## 🔄 Version History

### v1.0 — Initial draft  
**Date:** 21 March 2026  

- Generic responses  
- Low engagement  

**Lesson:** Need structure  

---

### v1.1 — Added structure and tone  
**Date:** 24 March 2026  

- Improved clarity  
- Still somewhat generic  

**Lesson:** Need context  

---

### v1.2 — Added contextual inputs + constraints ✅ Current  
**Date:** 27 March 2026  

- Personalised messages  
- Better tone and clarity  

**Observed effect:**  
Improved engagement and satisfaction  

---

## 📊 A/B Test Results

**Test date:** 29 March 2026 | Sample: 40 tickets  

| Criteria | v1.0 | v1.2 |
|----------|------|------|
| Personalisation | 2/5 | 4.6/5 |
| Tone quality | 2.5/5 | 4.7/5 |
| Engagement | 2/5 | 4.5/5 |
| Clarity | 2.5/5 | 4.8/5 |
| **Overall** | **2.2/5** | **4.7/5** |

---

## 🔗 Related Prompts

- Previous: P09 — Ticket summary generator  
- Triggered after: Issue resolution  
- Feeds into: CSAT / feedback systems  

**Parent section:** 04 — Post-Support  
**Library index:** README.md  
