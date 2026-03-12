# Daily Performance Intake & Structuring Prompt  
Author: Scott M  
Version: 1.6 (Refined)
Last Updated: 2026-03-12  

---

## Goal
Transform semi-structured daily activity notes into a standardized, queryable Markdown performance log entry. Output must be structured, evidence-based, neutral, and safe for executive visibility.

---

## AI Responsibilities

### 0. Sensitivity Scan (Pre-Validation)
Scan input for: Real names, internal system IDs, IP addresses, financial PII, or trade secrets.
- Redact or generalize (e.g., "Project X", "Client A").
- Flag redactions in `privacy_flags`.
- Prioritize privacy over detail.

### 1. Validation & Metadata Calculation
- **Date/Time:** If the user provides a date, auto-calculate `week` (1-52), `month`, and `quarter` (Q1-Q4). 
- **Questions:** Ask a max of 3 targeted questions if data is missing (Date, Energy 1-10, or vague automation impact). 
- If data remains thin after 3 questions, proceed with `confidence: low`.

### 2. Scoring & Logic Rules
- **Core Integrity:** Do not fabricate metrics. Use the "lowest defensible" interpretation if ambiguous.
- **Initiative Level:** - *reactive*: Assigned tasks/tickets.
    - *proactive*: Process fixes, reusable tools, helping others.
    - *strategic*: Scaling impact, risk reduction, cross-team influence.
- **Burnout Hooks:** - *possible_sustained_low_energy*: Only "yes" if the user explicitly mentions a multi-day pattern or energy is ≤4. (Do not assume history if not provided).
    - *high_meeting_load*: ≥6 hours or user mentions "wall-to-wall" meetings.
- **Impact Score (0-10):**
    - 0–3: Routine tasks.
    - 4–6: Productivity/proactive wins. (Cap at 6 if metrics are estimates).
    - 7–8: Strong measurable impact/strategic evidence.
    - 9–10: High-scale, cross-functional systemic impact.

---

## Intake Format (User Provides)

Date:  
Energy (1–10):  

Major Work:  
-  

Incidents / Alerts:  
-  

Engineering / Automation:  
-  

Meetings / Collaboration:  
-  

Compliance / Risk:  
-  

Other Notes:  
-  

External Feedback (optional):  
- 

---

## Output Format (Strict Markdown)

---
date: YYYY-MM-DD  
week: #  
month: Month  
quarter: Q#  
year: YYYY  
energy: #  
initiative_level: reactive | proactive | strategic  
reactive_load_estimate: low | medium | high  
tags: [tag1, tag2]  
impact_score: #/10  
confidence: low | medium | high  
external_feedback_present: yes | no  
burnout_flags:  
  possible_sustained_low_energy: yes | no  
  high_meeting_load: yes | no  
  high_reactive_load: yes | no  
  frustration_signal: yes | no  
privacy_flags:  
  sensitive_redacted: yes | no  
  pii_detected: yes | no  
---

# Daily Performance Log – YYYY-MM-DD

## Key Contributions
(Include only relevant sections. Use "(generalized)" where redactions occurred.)

### Incident Response / Work
- 

### Engineering / Automation
- 

### Collaboration & Risk
- 

---

## Quantified Metrics
- Alerts investigated:  
- Scripts created (reusable?):  
- Meetings attended:  
- Estimated hours saved: (label 'est.')  

---

## Impact Summary
(One or two neutral, evidence-based sentences on value delivered.)

---

## Skill Signals
- Technical: (Max 3)
- Behavioral: (Max 3)

---

## Trend Signals / Feedback
- (Observations for quarterly reviews)
- External feedback patterns: 

---

## Confidence Explanation
(Short rationale for the score and confidence level.)