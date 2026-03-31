# 📄 P04 · Customer response draft generator

**Section:** 02 — Response Handling  
**Workflow step:** Step 4 of 5 (feeds into tone refinement → customer reply → follow-up)  
**Current version:** v1.2  
**Status:** ✅ Tested  
**Last updated:** March 2026  

---

## 📌 Prompt Text (v1.2 — current)

```
You are a customer support agent for an online retail company.

Using the information below, write a clear, professional response to the customer.

Customer message: [CUSTOMER_MESSAGE]  
Category: [CATEGORY_FROM_P01]  
Priority: [PRIORITY_FROM_P03]  

Include:
1. Acknowledgement of the issue
2. Clear explanation or next steps
3. Reassurance or apology where appropriate
4. Closing statement offering further help

Tone:
- Professional and polite
- Empathetic for negative sentiment
- Concise and solution-focused

Length: maximum 120 words.

Do not:
- Make promises you cannot guarantee
- Include internal system details
- Use overly generic phrases

If insufficient information is available, ask a clarifying question instead of assuming.
```

---

## 🏢 Intended Workflow or Task

This prompt is **Step 4 in the customer service workflow** and represents the core interaction point with the customer.

- **Trigger:** Runs after P01 (classification), P02 (sentiment), and P03 (priority)  
- **Actor:** Customer support agent reviews and sends response  
- **Integration:** Output can be inserted into CRM/email/chat system  
- **Timing:** Within minutes of ticket assignment  

**Next step:**
- P05 (Tone adjuster) refines message  
- P09 (Ticket summary) logs interaction  
- P10 (Follow-up message) after resolution  

Ticket classified → prioritised → [P04 RUNS]  
→ Draft response generated  
→ Agent reviews → Sends to customer  
→ P05 (optional refinement)  

---

## ❗ Problem Being Solved

Customer support agents spend **5–10 minutes per ticket** drafting responses.

At ~200 tickets/day:

- 16–33 hours/day spent writing responses  
- Inconsistent tone across agents  
- Missing important information  
- Slow response times  

**Pain points addressed:**

- Repetitive manual drafting  
- Variation in communication quality  
- Delayed responses affecting satisfaction  

---

## ⚡ Automation Potential

**Level:** High  

| Dimension | Assessment |
|----------|-----------|
| Repetitiveness | Very high — similar structure |
| Data availability | Fully available from previous prompts |
| Human judgment needed | Medium — approval required |
| Integration possibility | Direct CRM/email integration |
| Estimated time saving | ~70% |

**Human-in-the-loop role:**
- Agent reviews and sends response  
- Minimal editing required  

**Scaling note:**  
At 200 tickets/day → saves **10–20 hours daily**

---

## ⚠️ Risks and Limitations

| Risk | Level | Mitigation |
|------|------|-----------|
| Generic responses | Medium | Use P05 (tone adjustment) |
| Incorrect information | Medium | Agent verification |
| Over-promising | High | Explicit constraints |
| Policy misalignment | Medium | Use P06 grounding |

**Overall risk rating:** MEDIUM  

---

## 🔄 Version History

### v1.0 — Initial draft  
**Date:** 15 March 2026  

- Generic output  
- No structure  
- Required full rewrite  

**Lesson:** Need structure + tone guidance  

---

### v1.1 — Added structure and tone  
**Date:** 18 March 2026  

- Improved clarity  
- Still inconsistent length  

**Lesson:** Need constraints  

---

### v1.2 — Added constraints and clarity ✅ Current  
**Date:** 21 March 2026  

- Word limit added  
- Clear rules introduced  
- Output concise and usable  

**Observed effect:**  
Editing reduced to ~2–3 minutes  

---

## 📊 A/B Test Results

**Test date:** 23 March 2026 | Sample: 40 tickets  

| Criteria | v1.0 | v1.2 |
|----------|------|------|
| Readability | 2.5/5 | 4.7/5 |
| Completeness | 2/5 | 4.6/5 |
| Tone | 2.5/5 | 4.8/5 |
| Send-ready | 1/5 | 4.2/5 |
| **Overall** | **2.3/5** | **4.6/5** |

---

## 🔗 Related Prompts

**Previous:**
- P01 — Complaint classification  
- P02 — Sentiment detection  
- P03 — Priority assignment  

**Next:**
- P05 — Tone adjuster  
- P09 — Ticket summary  
- P10 — Follow-up message  

**Also uses:**  
- P06 — FAQ answer generator  

**Parent section:** 02 — Response Handling  
**Library index:** README.md  
