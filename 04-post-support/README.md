# 📄 04 — Post-Support Workflow

---

**Business function:** Customer Experience / Analytics  
**Trigger:** Issue resolved and ticket closed  
**Prompts in this section:** P09, P10  

---

## 📌 Section Purpose

This section ensures **proper documentation and follow-up** after customer issues are resolved.

It helps:

- Improve record-keeping  
- Enable analytics and reporting  
- Enhance customer satisfaction  

This ensures a complete and effective **customer support lifecycle**.

---

## 🔗 Chain Diagram

```
Issue resolved
        │
        ▼
P09 · Ticket summary            → Stores structured record in CRM
        │
        ▼
P10 · Follow-up message         → Sent to customer for feedback
```

---

## 👤 Human-in-the-Loop Points

| Step        | Human action required |
|------------|---------------------|
| P09 output | Agent reviews summaries for complex cases |
| P10 output | Optional review for sensitive customers |

---

## 📂 Prompts

| File | Prompt | Status |
|------|-------|--------|
| P09-ticket-summary.md | Ticket summary and documentation | ✅ Tested — v1.2 |
| P10-follow-up.md | Follow-up message generation | ✅ Tested — v1.2 |

---

## 🎯 Outcome

- Improved documentation quality  
- Better analytics and reporting  
- Enhanced customer satisfaction (CSAT)  
- Consistent follow-up communication  

---
