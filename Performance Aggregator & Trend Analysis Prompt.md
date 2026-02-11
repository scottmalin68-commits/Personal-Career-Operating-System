# Performance Aggregator & Trend Analysis Prompt
Author: Scott M
Version: 1.1
Last Updated: 2026-02-11

---

## Goal

Aggregate multiple structured Daily Performance Log markdown entries and generate:

- Reliable performance dashboard metrics
- Trend analysis with statistical safeguards
- Initiative distribution analysis
- Promotion-signal extraction (evidence-based only)
- Burnout & sustainability signal detection
- Anomaly and workload spike identification
- Data continuity analysis

This system must prioritize analytical integrity over optimism.

Never fabricate activity.
Never inflate impact.
Never assume missing data equals zero.

---

## How To Use This Prompt

1. Paste this full prompt into the AI.
2. Below the divider line, paste:
   - Multiple structured Daily Performance Log markdown entries.
3. Optionally specify:
   - A quarter (e.g., "Analyze Q1 2026")
   - A date range (e.g., "2026-01-01 to 2026-03-31")
4. The AI will:
   - Filter entries if requested
   - Validate dataset sufficiency
   - Aggregate supported metrics
   - Detect patterns and anomalies
   - Produce structured output

IMPORTANT:
- Do not paste unstructured notes.
- This prompt expects standardized daily log markdown entries only.

---

## Changelog

### v1.1
- Added incomplete metric coverage detection
- Added low sample-size statistical warnings
- Added repeated-behavior requirement for promotion signals
- Added burnout variance & overlap detection
- Added anomaly spike detection
- Added data continuity gap detection
- Strengthened anti-inflation safeguards

### v1.0
- Initial aggregation framework
- Dashboard metrics
- Initiative distribution
- Promotion signal detection
- Burnout signal detection

---

## Recommended AI Engines (Best → Worst for Aggregation & Pattern Detection)

1. GPT-5 class models (strongest reasoning discipline & trend control)
2. Claude 3.x class models (excellent long-context synthesis)
3. Gemini Advanced class models (good counting, may over-infer patterns)
4. Smaller / mini models (adequate for counting, weaker for disciplined inference)

Quarterly and annual analysis strongly recommended on highest-tier reasoning models.

---

## AI Responsibilities

### 1. Dataset Validation

Before analysis:

- Count total entries.
- If total entries < 5:
    - Flag: "Insufficient data for reliable trend analysis."
    - Downgrade overall confidence to low.
- If total entries < 10:
    - Flag initiative distribution as low statistical confidence.

Detect date gaps:
- Identify gaps > 7 days between consecutive entries.
- Report "Data continuity gaps detected" if present.

---

### 2. Metric Aggregation Rules

Aggregate only explicitly stated numeric values.

If a metric field is absent in an entry:
- Treat as unknown.
- Do NOT treat as zero.

If >20% of entries lack quantified metrics:
- Flag: "Incomplete metric coverage; totals may underrepresent activity."

Calculate totals for:
- Alerts investigated
- Scripts created
- Detection rules modified
- Meetings attended
- Estimated hours saved (label cumulative as estimated)
- Risk-reduction actions
- Cross-team engagements

Never extrapolate missing values.

---

### 3. Initiative Distribution Analysis

Calculate percentage distribution of:
- reactive
- proactive
- strategic

Safeguards:
- If total entries < 10 → mark distribution as low confidence.
- Report absolute counts alongside percentages.

Example:
Reactive: 6 days (60%)

---

### 4. Work Distribution Estimation

Estimate category distribution using:

Primary weighting:
- Quantified workload metrics (alerts volume, scripts count, meetings count)

Secondary weighting:
- Section frequency only if metrics unavailable

Always label as:
"Estimated Work Distribution"

Never imply time allocation precision.

---

### 5. Anomaly & Spike Detection

Identify:

- Impact_score ≥ 9 days (High-impact events)
- Days where alerts investigated ≥ 2× period average
- Consecutive high reactive_load_estimate = high
- Clusters of high meeting load

Label as:
"Operational Spike Events"

Do not interpret cause beyond data.

---

### 6. Burnout & Sustainability Signal Detection

Analyze:

- Average energy score
- Energy variance (high volatility)
- Sustained low energy (3+ consecutive ≤ 5)
- Overlap of:
    - High reactive load
    - High meeting load
    - Low energy
- Downward energy trend slope (if ≥ 10 entries)

Do NOT diagnose burnout.
Only report observable patterns.

---

### 7. Promotion Signal Extraction (Strict Evidence Mode)

Only count behaviors as strength indicators if:

- Behavior appears 2+ times across dataset
OR
- Single instance clearly documented as systemic or strategic in scale

Otherwise label as:
"Isolated Example"

Identify:

Senior-Level Behaviors:
- Reusable automation
- Detection improvements
- Cross-team influence (repeated)
- Risk-reduction ownership
- Operational efficiency improvements

Strategic Behaviors:
- Designing controls
- Driving process changes
- Long-term automation initiatives
- Measurable systemic shifts

Also identify missing or underrepresented behaviors.

Never speculate beyond documented evidence.

---

## Output Format (Strict)

# Aggregated Performance Report

## Scope Analyzed
- Date Range:
- Total Entries:
- Data Continuity Gaps Detected: yes | no

---

## Dataset Reliability
- Entry Count Assessment:
- Metric Coverage Assessment:
- Statistical Confidence Level:

---

## Executive Summary
Evidence-based overview only.

---

## Quantified Metrics
- Total Alerts Investigated:
- Total Scripts Created:
- Total Detection Rules Modified:
- Total Meetings Attended:
- Cumulative Estimated Hours Saved:
- Risk-Reduction Actions:
- Cross-Team Engagements:

---

## Initiative Distribution
- Reactive: X days (X%)
- Proactive: X days (X%)
- Strategic: X days (X%)

Confidence Commentary:

---

## Estimated Work Distribution
- Incident Response:
- Engineering / Automation:
- Risk / Compliance:
- Collaboration:

Method note included.

---

## Operational Spike Events
- High Impact Days:
- Alert Volume Spikes:
- Consecutive High Reactive Periods:
- High Meeting Clusters:

---

## Promotion-Level Signals

### Strength Indicators (Repeated Evidence)
-

### Isolated Examples
-

### Missing or Underrepresented Signals
-

---

## Burnout & Sustainability Signals
- Average Energy:
- Energy Variance:
- Sustained Low Energy:
- Reactive/Meeting Overlap:
- Downward Energy Trend:

---

## Overall Confidence Level
low | medium | high

Explain limitations clearly.

---

Paste Daily Log Entries Below This Line
---------------------------------------------------------
