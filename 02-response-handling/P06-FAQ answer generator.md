# 📄 P06 · FAQ answer generation with policy grounding

**Section:** 02 — Response Handling  
**Workflow step:** Step 3 of 5 (supports response drafting with verified information)  
**Current version:** v1.2  
**Status:** ✅ Tested  
**Last updated:** March 2026  

---

## 📌 Prompt Text (v1.2 — current)

```
You are a customer support knowledge assistant for an online retail company.

Answer the customer's question using ONLY the information provided in the FAQ or policy data below.

Customer question: [CUSTOMER_QUESTION]

FAQ / Policy data:
[FAQ_DATA]

Instructions:
1. Provide a clear and concise answer
2. Use only the information explicitly provided
3. If the answer is not found, respond:
   "Insufficient information — escalate or request clarification"
4. Keep the response under 100 words
5. Do not assume or add external knowledge

Tone: professional and helpful

Output only the final answer text.
```

---

## 🏢 Intended Workflow or Task

This prompt supports the **response generation stage** by ensuring answers are **factually accurate and policy-compliant**.

- **Trigger:** Used when queries relate to policies (refunds, delivery, returns)  
- **Integration:** Output feeds into P04 (Response draft generator)  
- **Timing:** Runs during response drafting  

**Next step:**
- P04 integrates answer into full response  
- P05 refines tone  

Customer question → [P06 RUNS using FAQ data]  
→ Verified answer generated  
→ P04 incorporates into response  
→ P05 refines tone  

---

## ❗ Problem Being Solved

Customer support agents frequently handle repetitive policy-based queries such as:

- Refund eligibility  
- Delivery timelines  
- Return conditions  

Manual lookup takes **2–4 minutes per query**, leading to:

- Slower responses  
- Inconsistent answers  
- Risk of incorrect information  

At ~200 tickets/day:

- 6–13 hours/day spent on repeated information retrieval  

---

## ⚡ Automation Potential

**Level:** Very High  

| Dimension | Assessment |
|----------|-----------|
| Repetitiveness | Extremely high |
| Data availability | Fully available in FAQ database |
| Human judgment needed | Low |
| Integration possibility | Direct knowledge base integration |
| Estimated time saving | ~90% |

**Human-in-the-loop role:**
- Agents verify edge cases  
- Update FAQ when gaps are found  

**Scaling note:**  
Improves accuracy, consistency, and reduces workload significantly.

---

## ⚠️ Risks and Limitations

| Risk | Level | Mitigation |
|------|------|-----------|
| Missing answers in FAQ | Medium | Use fallback response |
| Outdated FAQ data | High | Regular updates |
| Over-reliance on AI | Medium | Combine with agent review |
| Misinterpretation of questions | Medium | Ask clarification |

**Overall risk rating:** MEDIUM  

---

## 🔄 Version History

### v1.0 — Initial draft  
**Date:** 17 March 2026  

- Used external assumptions  
- Risk of incorrect answers  

**Lesson:** Restrict to verified data  

---

### v1.1 — Added grounding constraint  
**Date:** 20 March 2026  

- Limited to FAQ data  
- Reduced hallucination  

**Lesson:** Need fallback  

---

### v1.2 — Added fallback + constraints ✅ Current  
**Date:** 23 March 2026  

- Added fallback response  
- Improved reliability  

**Observed effect:**  
Better accuracy and trust  

---

## 📊 A/B Test Results

**Test date:** 25 March 2026 | Sample: 40 queries  

| Criteria | v1.0 | v1.2 |
|----------|------|------|
| Accuracy | 2.5/5 | 4.8/5 |
| Consistency | 2/5 | 4.7/5 |
| Policy compliance | 2/5 | 4.9/5 |
| Hallucination rate | High | Low |
| **Overall** | **2.1/5** | **4.8/5** |

---

## 🔗 Related Prompts

- Used by: P04 — Response draft generator  
- Next: P05 — Tone adjuster  
- Supports: Policy-based responses  
- Parent section: 02 — Response Handling  
- Library index: README.md  
