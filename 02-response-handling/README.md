# 📄 02 — Response Handling Workflow

---

**Business function:** Customer Support Operations  
**Trigger:** Ticket processed and ready for response  
**Prompts in this section:** P04, P05, P06  

---

## 📌 Section Purpose

This section automates the **generation of customer responses** while ensuring:

- Accuracy  
- Tone consistency  
- Policy compliance  

It helps:

- Reduce response drafting time  
- Improve communication quality  
- Maintain consistency across support teams  

---

## 🔗 Chain Diagram

```
Ticket ready for response
        │
        ▼
P06 · FAQ answer generation       → Provides policy-based answer
        │
        ▼
P04 · Response draft generator    → Creates full response
        │
        ▼
P05 · Tone adjustment             → Refines tone and clarity
```

---

## 👤 Human-in-the-Loop Points

| Step        | Human action required |
|------------|---------------------|
| P04 output | Agent reviews and approves response before sending |
| P05 output | Agent checks tone for appropriateness |
| P06 output | Agent verifies FAQ accuracy in edge cases |

---

## 📂 Prompts

| File | Prompt | Status |
|------|-------|--------|
| P04-response-draft.md | Customer response draft generator | ✅ Tested — v1.2 |
| P05-tone-adjuster.md | Response tone adjustment | ✅ Tested — v1.2 |
| P06-faq-answer.md | FAQ answer generation (grounded) | ✅ Tested — v1.2 |

---

## 🎯 Outcome

- Faster response generation  
- Improved response quality and tone  
- Consistent policy-based communication  
- Reduced agent workload  

---
