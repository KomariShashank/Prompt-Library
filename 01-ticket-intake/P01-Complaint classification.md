# 📄 P01 · Complaint triage and classification

**Section:** 01 — Ticket Intake  
**Workflow step:** Step 1 of 5  
**Current version:** v1.2  
**Status:** ✅ Tested  
**Last updated:** March 2026  

---

## 📌 Prompt Text (v1.2 — current)

```
You are a customer service triage assistant for an online retail company.

Classify the following customer message into EXACTLY ONE category:
- Delivery issue
- Refund request
- Product defect
- Order status enquiry
- Payment issue
- Account issue
- General enquiry

Also extract:
1. A one-line summary of the issue (max 20 words)
2. Key details (order number, product name, dates if mentioned)

Customer message: [CUSTOMER_MESSAGE]

Respond in JSON only. Do not add any explanation outside the JSON.

{
  "category": "[chosen category]",
  "summary": "[one-line summary]",
  "key_details": ["detail 1", "detail 2"]
}
```
---

## 🏢 Intended Workflow or Task

This prompt is **Step 1 of the customer service ticket handling workflow**.

- **Trigger:** Customer message received via email, chat, or web form  
- **Integration:** JSON output is parsed by the CRM/ticketing system to automatically route the ticket  
- **Timing:** Runs instantly upon ticket creation (real-time automation)  

**Next step:**
- P02 (Sentiment detection) evaluates emotional tone  
- P03 (Priority assignment) determines urgency level  

Customer message received → [P01 RUNS] → JSON output generated  
→ CRM routes ticket  
→ P02 + P03 triggered  

---

## ❗ Problem Being Solved

Customer support teams manually read and classify incoming messages, which takes **3–5 minutes per ticket**.

At ~200 tickets/day, this results in:

- 10–17 hours of manual triage work daily  
- Delays in ticket routing during peak periods  
- Inconsistent classification across agents  

**Pain points addressed:**

- Tickets sent to wrong department  
- Slow response due to manual sorting  
- Increased workload on senior staff  

---

## ⚡ Automation Potential

**Level:** Very High  

| Dimension | Assessment |
|----------|-----------|
| Repetitiveness | Extremely high — required for every ticket |
| Data availability | Fully available in message |
| Human judgment needed | Low |
| Integration possibility | Direct CRM integration via JSON |
| Estimated time saving | ~95% |

**Human-in-the-loop role:**
- Review "General enquiry" cases  
- Weekly audit for accuracy  

**Scaling note:**  
At 200 tickets/day → saves **10–17 hours daily**

---

## ⚠️ Risks and Limitations

| Risk | Level | Mitigation |
|------|------|-----------|
| Misclassification of multi-issue messages | Medium | Use fallback category |
| Missing details in vague messages | Medium | Follow-up prompts |
| JSON errors | Medium | Strict output validation |
| Sensitive data risks | Medium | Secure deployment |

**Overall risk rating:** MEDIUM  

---

## 🔄 Version History

### v1.0 — Initial draft  
**Date:** 12 March 2026  
**Prompt:** Classify this customer message  

- Output: Unstructured  
- Issue: Not usable in system  
- Lesson: Need structure  

---

### v1.1 — Added structure  
**Date:** 15 March 2026  

- Added categories and summary  
- Output improved but inconsistent  
- Lesson: Need machine-readable format  

---

### v1.2 — JSON + constraints ✅ Current  
**Date:** 18 March 2026  

- Added JSON-only rule  
- Output consistent and usable  
- Successfully integrated  

---

## 📊 A/B Test Results

**Test date:** 20 March 2026 | Sample: 40 messages  

| Criteria | v1.0 | v1.2 |
|----------|------|------|
| Output consistency | 2/5 | 4.8/5 |
| Accuracy | 2.5/5 | 4.6/5 |
| Integration | Failed | Successful |
| Time saving | Low | High |
| **Overall** | **2.2/5** | **4.7/5** |

---

## 🔗 Related Prompts

- Next: P02 — Sentiment detection  
- Next: P03 — Priority assignment  
- Parent section: 01 — Ticket Intake  
- Library index: README.md  
