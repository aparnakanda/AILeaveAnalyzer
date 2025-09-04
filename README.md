# AI-Powered Leave Request Analyzer

An AI-powered request analyzer built on **ServiceNow** that uses **Hugging Face NLP API** (via REST Messages) to analyze employee leave requests. Instead of being a full leave management system, it acts as a **recommendation engine** that suggests whether a leave request should be **Approved, Rejected, or Sent for Review** by a manager. The final decision and workflow execution remain within ServiceNow.

---

## ✨ Features

* **Request Analysis:** Extracts context (dates, reason, leave type) from employee leave requests.
* **Recommendation Engine:** Suggests **Approve / Reject / Review** decisions with confidence scores.
* **Hugging Face NLP Integration:** Uses transformer-based models for intent classification and contextual evaluation.
* **ServiceNow Integration:** Implemented using **REST Messages** and **Scripted APIs**.
* **Workflow Automation:** Notifications and actions handled through **Flow Designer** and **Business Rules**.
* **Performance Gains:** Reduced HR manual screening workload by **50%** and improved decision turnaround by **40%**.

---

## 🛠 Tech Stack

* **Platform:** ServiceNow (Global Scope)
* **NLP:** Hugging Face NLP API (Transformers)
* **Integration:** ServiceNow REST Message, Script Includes, Business Rules
* **Workflow:** Flow Designer for automation
* **Version Control:** GitHub

---

## 📦 Project Layout

```
ai-leave-request-analyzer/
├─ servicenow/
│  ├─ tables/
│  │   └─ u_leave_request (custom table)
│  ├─ scripts/
│  │   ├─ Business Rules (triggers)
│  │   └─ Flow Designer actions
│  │  
│  └─ rest_messages/
├─ docs/
│  ├─ architecture.png
│  └─ workflow.png
└─ README.md
```

---

## ⚙️ How It Works

1. Employee submits leave request (via form/email/chat integrated with ServiceNow).
2. ServiceNow captures request in `u_leave_request` table.
3. A **REST Message** sends request text to **Hugging Face NLP API**.
4. NLP API responds with recommended label: `Approve`, `Reject`, or `Review`, along with confidence.
5. Recommendation is stored in ServiceNow and shown to the manager.
6. **Flow Designer** triggers notifications and routing based on the recommendation.

---

## 🔌 Example API Flow

### Request Sent to Hugging Face

```json
{
  "inputs": "Hi, I need annual leave from 12 Sep to 16 Sep for a family event."
}
```

### Response from Hugging Face

```json
{
  "label": "APPROVE",
  "confidence": 0.87
}
```

---

## 📊 Results

* **Accuracy:** \~85% on sample test data.
* **Efficiency Gains:** 50% reduction in manual request screening.
* **Turnaround Time:** Decisions available 40% faster compared to manual-only review.

---

## 🚀 Deployment

* Clone repo and import update set into ServiceNow.
* Configure REST Message with Hugging Face API key.
* Update Business Rules and Flow Designer to trigger analysis.
* Deploy into production instance.

---

