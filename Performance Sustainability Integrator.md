# Performance Sustainability Integrator – Cross-Engine Conflict Detector
Author: Scott M
Version: 1.0
Last Updated: 2026-02-11

---

## GOAL

Integrate outputs from the Promotion Evaluator and Burnout Deep Analyzer to:

1. Detect conflicts between performance growth and long-term sustainability.
2. Highlight areas where high promotion signals may be driven by unsustainable effort.
3. Identify safe growth opportunities and risk zones.
4. Provide actionable recommendations to align career growth with sustainability.

This engine does **not** re-analyze raw logs. It works only from structured outputs of the other engines.

---

## CHANGELOG

### v1.0
- Initial cross-engine integration.
- Conflict detection framework based on promotion readiness vs burnout risk.
- Alignment scoring system.
- Strategic guidance and projection modeling.
- Fully neutral; does not inflate risk or readiness.

---

## RECOMMENDED AI ENGINES

1. GPT-5 – best multi-engine reasoning.
2. Claude Opus 4 – strong narrative framing.
3. Gemini Advanced – adequate, less conservative on conflict interpretation.
4. GPT-4-class models – use with caution; may under-detect subtle conflicts.

---

# HOW TO USE

1. Run the **Promotion Evaluator** for the target role and copy structured output.
2. Run the **Burnout Deep Analyzer** for the same period and copy trend snapshot + risk assessment.
3. Paste both structured outputs into this prompt.
4. Run monthly or quarterly, aligned with the frequency of the other engines.

---

# REQUIRED INPUTS

- Promotion Evaluator Output:
  - Readiness Level
  - Repeated vs isolated evidence
  - Initiative distribution
  - Strategic contribution frequency
  - Market competitiveness score
  - Salary positioning
- Burnout Deep Analyzer Output:
  - Burnout Risk Level
  - Energy slope and volatility
  - Reactive & meeting clustering
  - Sustainability status
  - Trend snapshot metrics
  - Forecasted next-period risk

---

# ANALYSIS FRAMEWORK

### 1. Alignment Scoring

Generate a **Growth–Sustainability Alignment Score** based on:

| Factor | Score | Evidence |
|--------|-------|---------|
| Promotion Readiness vs Burnout Risk |
| Strategic Work Sustainability |
| Reactive Work Overload |
| Initiative Growth vs Energy Trend |
| Capacity Stability |

Score scale: 1–5 (1 = misaligned, 5 = fully aligned)

Overall Alignment:
- Fully Aligned
- Mostly Aligned
- Mild Conflict
- Significant Conflict
- High Risk Conflict

---

### 2. Conflict Pattern Detection

Evaluate structured outputs for these patterns:

1. **High Promotion Signals + Elevated Burnout Risk**
   - Ready Now / Above Level + Elevated or Critical Risk
   - Label: Performance–Sustainability Conflict: High

2. **Strategic Growth but Declining Energy**
   - Increasing strategic contribution + declining energy slope
   - Label: Growth Sustainability Imbalance

3. **High Market Competitiveness Driven by Reactive Load**
   - Strong external score but dominated by reactive tasks
   - Label: Operational Overextension

4. **Low Burnout Risk but Low Promotion Readiness**
   - Stable energy but stagnating development
   - Label: Comfort Zone Plateau

5. Other conflicts as evidenced by trends or forecasted next-period risk.

---

### 3. Projection Modeling

Based on trend snapshots:

- Predict next 3–6 months:
  - Promotion readiness trajectory
  - Burnout risk trajectory
  - Capacity stability
- Highlight areas likely to produce conflict if patterns continue.

---

### 4. Strategic Recommendations

Provide actionable guidance in three tiers:

- **Sustain & Scale** – low risk, high alignment
- **Scale with Guardrails** – moderate conflict; maintain growth safely
- **Stabilize Before Scaling** – elevated conflict; reduce reactive load, prioritize energy
- **Reset & Rebalance** – high/critical conflict; urgent intervention needed

Recommendations must reference **evidence from the structured outputs**.

---

### 5. Optional Supervisor Communication Support

If conflict is significant or high-risk:

- Draft talking points
- Draft professional email
- Highlight risk without dramatization
- Suggest constructive mitigation steps

---

# OUTPUT FORMAT

## 1. Growth–Sustainability Alignment Score

Overall Alignment:  
Score: X/5  
Evidence Summary:

---

## 2. Conflict Analysis

- High Promotion + Burnout Risk Conflicts:
- Strategic Growth + Declining Energy Conflicts:
- Reactive Work Overextension:
- Comfort Zone Plateaus:

---

## 3. 3–6 Month Projection

- Promotion Probability:
- Burnout Probability:
- Capacity Stability:

---

## 4. Strategic Recommendations

- Tiered Recommendations (Sustain, Guardrails, Stabilize, Reset)
- Actionable next steps with rationale

---

## 5. Optional Supervisor Communication

- Talking Points:
- Draft Email:
- Conversation Script:

---

# FINAL RULES

- Only use structured outputs from other engines.
- Do not re-analyze raw logs.
- Prioritize evidence over inference.
- Clearly label confidence and assumptions.
- Do not inflate promotion readiness or burnout risk.
