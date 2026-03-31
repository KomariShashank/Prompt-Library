# 📄 P02 · Sentiment detection and emotional intensity

**Section:** 01 — Ticket Intake  
**Workflow step:** Step 2 of 5  
**Current version:** v1.2  
**Status:** ✅ Tested  
**Last updated:** March 2026  

---

## 📌 Prompt Text (v1.2 — current)

```
You are a customer service sentiment analysis assistant for an online retail company.

Analyse the emotional tone of the following customer message.

Classify sentiment into EXACTLY ONE of:
- Positive
- Neutral
- Negative

Also classify emotional intensity:
- Low
- Medium
- High

Provide:
1. Sentiment classification
2. Emotional intensity
3. One-line justification (max 20 words, based only on message content)

Customer message: [CUSTOMER_MESSAGE]

Respond in JSON only. Do not add any explanation outside the JSON.

{
  "sentiment": "[Positive / Neutral / Negative]",
  "intensity": "[Low / Medium / High]",
  "reason": "[one short sentence]"
}

Rules:
- Do not assume intent beyond the message
- If mixed tone, choose the dominant sentiment
- Use "High" intensity for strong language, threats, or frustration
```

---

## 🏢 Intended Workflow or Task

This prompt is **Step 2 in the customer service workflow**.

- **Trigger:** Runs automatically after P01 (Complaint classification)  
- **Integration:** Output feeds into CRM system for priority assignment and tone adjustment  
- **Timing:** Real-time (within seconds of ticket creation)  

**Next step:**
- P03 (Priority assignment) uses sentiment + category  
- P04 (Response draft generator) adapts tone accordingly  

Customer message → P01 (classification) → [P02 RUNS]  
→ Sentiment + intensity generated  
→ Priority calculated (P03)  
→ Response tone adjusted (P04)  

---

## ❗ Problem Being Solved

Customer support agents often misinterpret emotional tone, especially under high workload.

At ~200 tickets/day:

- Urgent or frustrated customers may be overlooked  
- Negative sentiment treated as routine  
- Poor tone matching leads to escalation  

**Pain points addressed:**

- Inconsistent emotional interpretation  
- Delayed prioritisation of urgent complaints  
- Generic responses to sensitive issues  

This reduces customer satisfaction and increases escalation rates.

---

## ⚡ Automation Potential

**Level:** Very High  

| Dimension | Assessment |
|----------|-----------|
| Repetitiveness | Extremely high — required for every ticket |
| Data availability | Fully available in message |
| Human judgment needed | Low for clear signals |
| Integration possibility | Direct CRM integration |
| Estimated time saving | ~90% |

**Human-in-the-loop role:**
- Review ambiguous cases  
- Flag high-intensity negative tickets  

**Scaling note:**  
Improves prioritisation and reduces escalation rates at scale.

---

## ⚠️ Risks and Limitations

| Risk | Level | Mitigation |
|------|------|-----------|
| Misinterpretation of sarcasm | Medium | Combine with category + review |
| Cultural/language differences | Medium | Standardisation + oversight |
| Overestimating intensity | Medium | Use simple scale |
| Over-reliance on automation | Low | Human review for sensitive cases |

**Overall risk rating:** MEDIUM  

---

## 🔄 Version History

### v1.0 — Initial draft  
**Date:** 13 March 2026  

- Binary sentiment only  
- Missed neutral/mixed tones  
- Lesson: Need more categories  

---

### v1.1 — Added sentiment categories  
**Date:** 16 March 2026  

- Added Positive / Neutral / Negative  
- Still lacked urgency signal  
- Lesson: Need intensity  

---

### v1.2 — Added intensity + JSON output ✅ Current  
**Date:** 19 March 2026  

- Added intensity scale  
- Structured JSON output  
- Improved prioritisation and tone alignment  

---

## 📊 A/B Test Results

**Test date:** 21 March 2026 | Sample: 40 messages  

| Criteria | v1.0 | v1.2 |
|----------|------|------|
| Accuracy | 2.5/5 | 4.7/5 |
| Consistency | 2/5 | 4.8/5 |
| Usefulness | 2/5 | 4.8/5 |
| Integration readiness | Low | High |
| **Overall** | **2.2/5** | **4.8/5** |

---

## 🔗 Related Prompts

- Previous: P01 — Complaint classification  
- Next: P03 — Priority assignment  
- Used by: P04 — Response draft generator  
- Parent section: 01 — Ticket Intake  
- Library index: README.md  
