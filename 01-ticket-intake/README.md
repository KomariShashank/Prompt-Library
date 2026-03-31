# 📄 01 — Ticket Intake Workflow

---

**Business function:** Customer Service / Contact Centre  
**Trigger:** Customer message received via email, chat, or web form  
**Prompts in this section:** P01, P02, P03  

---

## 📌 Section Purpose

This section automates the **initial intake and processing of customer queries**.

In high-volume environments (~200 tickets/day), manual triage leads to:

- Delays in response  
- Inconsistent handling  
- Incorrect routing  

These prompts ensure:

- Accurate classification  
- Sentiment-aware processing  
- Proper prioritisation  

---

## 🔗 Chain Diagram

```
Customer message received
        │
        ▼
P01 · Complaint classification     → Categorises issue for routing
        │
        ▼
P02 · Sentiment detection          → Identifies tone and urgency
        │
        ▼
P03 · Priority assignment          → Determines urgency level
```

---

## 👤 Human-in-the-Loop Points

| Step        | Human action required |
|------------|---------------------|
| P01 output | Agent reviews "General enquiry" or unclear classifications |
| P02 output | Spot-check emotionally sensitive messages |
| P03 output | Override incorrect priority if needed |

---

## 📂 Prompts

| File | Prompt | Status |
|------|-------|--------|
| P01-complaint-classification.md | Complaint classification and routing | ✅ Tested — v1.2 |
| P02-sentiment-detection.md | Sentiment detection and intensity | ✅ Tested — v1.2 |
| P03-priority-assignment.md | Priority assignment and urgency scoring | ✅ Tested — v1.2 |

---

## 🎯 Outcome

- Faster ticket processing  
- Improved routing accuracy  
- Better prioritisation of urgent issues  
- Reduced manual workload  

---
