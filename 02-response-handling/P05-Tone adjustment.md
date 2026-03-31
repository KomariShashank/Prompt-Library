# 📄 P05 · Response tone adjustment and personalisation

**Section:** 02 — Response Handling  
**Workflow step:** Step 5 of 5 (refines draft response before sending)  
**Current version:** v1.2  
**Status:** ✅ Tested  
**Last updated:** March 2026  

---

## 📌 Prompt Text (v1.2 — current)

```
You are a customer experience specialist.

Improve the tone and clarity of the following customer response.

Original response: [RESPONSE_FROM_P04]  
Sentiment: [SENTIMENT_FROM_P02]  
Intensity: [INTENSITY_FROM_P02]

Adjust the response to:
1. Be more empathetic if sentiment is negative
2. Be polite and professional at all times
3. Sound natural and human (not robotic)
4. Maintain clarity and conciseness

Guidelines:
- Do not change the meaning of the response
- Do not add new information or promises
- Avoid overly generic phrases
- Keep the length under 120 words

Output only the improved response text.
```

---

## 🏢 Intended Workflow or Task

This prompt is **Step 5 in the customer response workflow** and acts as the final quality refinement stage before sending.

- **Trigger:** Runs after P04 (Response draft generator)  
- **Actor:** Customer support agent reviews final output  
- **Integration:** Output replaces or refines draft in CRM/email/chat system  
- **Timing:** Immediately before sending  

**Next step:**
- Message sent to customer  
- P09 (Ticket summary) logs interaction  
- P10 (Follow-up message) triggered after resolution  

Response drafted (P04) → [P05 RUNS]  
→ Tone refined and personalised  
→ Agent reviews → Sends to customer  

---

## ❗ Problem Being Solved

Even when responses are correct, they often sound **robotic, overly formal, or lacking empathy**.

At ~200 tickets/day:

- Inconsistent tone across agents  
- Negative customers receive neutral replies  
- Poor tone leads to escalations  

**Pain points addressed:**

- Lack of emotional intelligence  
- Inconsistent communication quality  
- Increased customer frustration  

---

## ⚡ Automation Potential

**Level:** Medium  

| Dimension | Assessment |
|----------|-----------|
| Repetitiveness | High — every response benefits |
| Data availability | Fully available |
| Human judgment needed | Medium — subjective |
| Integration possibility | Direct workflow integration |
| Estimated time saving | ~50% |

**Human-in-the-loop role:**
- Agent reviews tone before sending  

**Scaling note:**  
Consistent tone improves **CSAT and reduces escalations**

---

## ⚠️ Risks and Limitations

| Risk | Level | Mitigation |
|------|------|-----------|
| Over-polishing → unnatural tone | Medium | Limit to tone changes |
| Loss of details | Medium | Preserve original meaning |
| Excess empathy | Low | Balance with context |
| Subjectivity of tone | Medium | Human validation |

**Overall risk rating:** MEDIUM  

---

## 🔄 Version History

### v1.0 — Initial draft  
**Date:** 16 March 2026  

- Vague improvements  
- Changed meaning sometimes  
- Needed re-editing  

**Lesson:** Need constraints  

---

### v1.1 — Added tone guidelines  
**Date:** 19 March 2026  

- Improved readability  
- Sometimes added extra content  

**Lesson:** Restrict added information  

---

### v1.2 — Added strict constraints ✅ Current  
**Date:** 22 March 2026  

- Preserved meaning  
- Limited edits  
- Consistent output  

**Observed effect:**  
Editing reduced to ~1–2 minutes  

---

## 📊 A/B Test Results

**Test date:** 24 March 2026 | Sample: 40 responses  

| Criteria | v1.0 | v1.2 |
|----------|------|------|
| Tone quality | 2.5/5 | 4.8/5 |
| Naturalness | 2/5 | 4.7/5 |
| Accuracy | 2/5 | 4.6/5 |
| Editing time | Low | High |
| **Overall** | **2.1/5** | **4.7/5** |

---

## 🔗 Related Prompts

**Previous:**
- P04 — Response draft generator  

**Next:**
- P09 — Ticket summary generator  
- P10 — Follow-up message generator  

**Uses:**
- P02 — Sentiment detection  

**Parent section:** 02 — Response Handling  
**Library index:** README.md  
