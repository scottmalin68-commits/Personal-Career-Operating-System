# Burnout Deep Analyzer – Trend & Forecast Edition
Author: Scott M
Version: 1.2
Last Updated: 2026-02-11

## GOAL
Analyze structured v1.2 Daily Performance Logs over a defined period to:
1. Detect observable sustainability & burnout pattern signals
2. Track longitudinal energy and workload trends
3. Provide conservative forward-looking risk projection (if data sufficient)
4. Suggest evidence-based mitigation options
5. (Optional) Prepare neutral, data-only talking points for supervisor discussion

Strict rules:
- Evidence only – never diagnose medical/psychological conditions
- Never exaggerate risk
- Never fabricate patterns
- Clearly flag low-confidence outputs

---

## CHANGELOG

### v1.2 (major revision)
- Added explicit thresholds/formulas for slope, volatility, clusters, overlap
- Defined point-based Burnout Risk Level rubric
- Constrained forecasting to linear trend continuation + confidence rules
- Added composite confidence rubric
- Added two worked examples
- Added input validation for v1.2 logs
- Integrated optional self-reported stress/satisfaction score
- Strengthened supervisor draft rules (data-only, strong disclaimers)

### v1.1
- Added trend snapshot markdown
- Added forecasting fields
- Added supervisor communication draft

---

## RECOMMENDED AI ENGINES

1. GPT-5 class (strongest conservative reasoning & trend discipline)
2. Claude 3.x / 4 class (excellent long-context pattern control)
3. Gemini Advanced (good aggregation, occasional optimism risk)

---

## HOW TO USE

1. Paste multiple v1.2 Daily Performance Log entries
2. Optional: Append current self-reported Stress (1–10) and/or Job Satisfaction (1–10)
3. Run monthly/quarterly and append snapshot to personal tracking file

If <5 valid entries: limit to basic stats + strong low-confidence warning  
If <10 entries: downgrade trend & forecast confidence significantly

---

## ANALYSIS RESPONSIBILITIES

### 1. Input & Data Validation
- Validate entries match v1.2 format (date: YYYY-MM-DD header + sections)
- Reject malformed entries and report count
- Sort by date, detect gaps >7 calendar days
- If optional Stress/Satisfaction provided: record latest value

### 2. Key Calculations (Strict Definitions)

- Average Energy: mean of all energy scores
- Energy Volatility: sample standard deviation (high ≥ 2.5)
- Energy Slope: if ≥10 entries → simple linear regression slope (points/day);
  - Declining: ≤ –0.15/day
  - Stable: –0.14 to +0.14/day
  - Increasing: ≥ +0.15/day
- Sustained Low Energy: number of periods of **4+ consecutive** days with energy ≤ 5 (gaps reset streak)
- Reactive Clustering: number of periods of **4+ consecutive** days with reactive_load_estimate = high
- Meeting Clustering: number of periods of **4+ consecutive** days with high_meeting_load = yes
- High Impact + Low Energy Overlap: number of periods of **3+ consecutive** days with (impact_score ≥ 9 AND energy ≤ 5)

### 3. Burnout Risk Level Rubric

Points-based (max 12):  
+4 – Any sustained low energy period (4+ days)  
+3 – High energy volatility (std dev ≥ 2.5)  
+3 – Downward energy slope (≤ –0.15/day) AND ≥10 entries  
+2 – Each reactive or meeting cluster (4+ days)  
+2 – Each high-impact + low-energy overlap (3+ days)  
+1 – Optional self-reported Stress ≤ 4 (if provided)

Risk Level:  
- Low: 0–2 points  
- Moderate: 3–5 points  
- Elevated: 6–8 points  
- High: 9–10 points  
- Critical: 11–12 points

Confidence downgrade if:  
- <15 entries → -2 points max risk = Elevated  
- High volatility OR large gaps → cap at High

### 4. Sustainability & Forecast

Workload Balance:  
- Sustainable: Low risk + stable/increasing energy  
- Mild Strain: Moderate risk  
- Unsustainable Pattern Emerging: Elevated risk  
- Unsustainable: High/Critical risk  

Capacity Projection (only if ≥15 entries & slope calculable):  
- If declining slope + current risk ≥ Elevated → "Increasing risk likely next 30 days if trend continues"  
- Always include: "Projection is simple linear extrapolation – actual outcomes depend on many unmeasured factors."

---

## OUTPUT FORMAT (Strict)

# Burnout & Sustainability Analysis – [Period]

## 1. Data Integrity & Confidence
- Valid Entries: X (Y rejected)
- Time Span: [start – end]
- Data Gaps (>7 days): Yes/No (details: largest X days)
- Optional Self-Reported: Stress X/10 | Satisfaction X/10
- Overall Confidence: High / Moderate / Low  
  Rubric: ≥20 entries + low gaps + low volatility = High; <10 entries = Low

## 2. Energy & Workload Trends
- Average Energy: X.X
- Energy Slope: declining / stable / increasing (slope –X.XX/day)
- Energy Volatility: X.X (high if ≥2.5)
- Sustained Low Energy Periods: X (longest X days)
- Reactive Clustering: X periods (longest X days)
- Meeting Clustering: X periods (longest X days)
- High Impact + Low Energy Overlap: X periods

## 3. Burnout Risk Assessment
Risk Level: Low / Moderate / Elevated / High / Critical
Points Breakdown: [list]
Confidence: [level]
Evidence Summary:
- 

## 4. Sustainability & Projection
Workload Balance: Sustainable / Mild Strain / Unsustainable Pattern Emerging / Unsustainable
Forecasted Risk Next 30 Days: [statement or "Insufficient data for projection"]
Key Caveats: 

## 5. Trend Snapshot (Appendable Markdown)

Use this exact structure when appending to your master tracking file:

## Burnout Trend Snapshot – [start] to [end]
- Average Energy: X.X
- Energy Slope: [direction] (–X.XX/day)
- Energy Volatility: X.X
- Sustained Low Energy: X periods
- Reactive Clustering: X periods
- Meeting Clustering: X periods
- High Impact + Low Energy Overlap: X periods
- Burnout Risk Level: [level]
- Confidence: [level]
- Forecasted Risk Next Period: [brief]
- Notes / Recommendations:

## 6. Mitigation Recommendations

### Immediate (next 1–2 weeks)
- 

### Structural / Longer-Term
- 

### Strategic / Career-Oriented (only if risk ≥ Elevated)
- 

## 7. Optional Supervisor Discussion Prep (only if risk ≥ Elevated)

**Strong disclaimer:** This is a data-only draft. Edit heavily. Do not use emotional language. Focus on performance sustainability.

### A. Neutral Talking Points
1. Observed patterns from personal tracking logs
2. Objective data highlights
3. Proposed adjustments to maintain high performance

### B. Draft Email (data-focused, professional)
Subject: Discussion on Workload Sustainability & Performance Support

[short neutral body – 4–6 sentences max]

### C. Conversation Script Bullets (5–7 max)
- 

---

## FINAL RULES
- If <5 entries: output only basic stats + "Insufficient data for meaningful trend or risk assessment."
- Never use diagnostic language ("burnout", "exhaustion", etc.) – only patterns & signals.
- Prioritize conservatism over actionability.