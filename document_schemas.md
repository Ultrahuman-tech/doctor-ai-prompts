# Document Schemas Reference

This reference describes what health metrics are available in each document type. Use this to:
1. Know where to look for specific metrics
2. Understand what data each document type contains
3. Verify data availability before claiming something is "missing"

---

## Sleep Data

### sleep_daily
Nightly sleep metrics:
- Sleep score (overall quality rating)
- Total sleep duration
- Sleep stages: Deep, REM, Light sleep (minutes and percentages)
- Sleep efficiency and restfulness
- Time to fall asleep, wake-ups
- Heart rate during sleep
- HRV during sleep
- Skin temperature during sleep

### sleep_weekly
Weekly aggregated sleep:
- Average sleep score
- Average duration and stage breakdown
- Sleep schedule consistency
- Weekly trends and patterns
- Best/worst nights

### sleep_monthly
Monthly sleep summary:
- Monthly averages for all sleep metrics
- Long-term trend analysis
- Month-over-month comparisons

---

## Movement & Activity Data

### movement_daily
Daily activity metrics:
- Movement score/state
- Step count and density throughout day
- Activity balance (sedentary vs active)
- Training load
- Calories burned
- Active minutes

### movement_weekly
Weekly activity summary:
- Total steps
- Workout count and details
- Activity trends
- Highlight days

### movement_monthly
Monthly movement overview:
- Monthly step totals
- Workout frequency
- Long-term activity patterns

---

## Cardiovascular Health

### cardiovascular_weekly
Weekly heart metrics:
- HRV trends (average, baseline comparison)
- Resting heart rate (day/night)
- Heart rate recovery from workouts
- AFib screening results (if available)

### cardiovascular_monthly
Monthly cardiovascular overview:
- HRV and RHR trend analysis
- Heart rhythm screening history
- Long-term cardiovascular health trends

---

## Recovery & Stress

### recovery_weekly
Weekly recovery metrics:
- Body signals score
- HRV and RHR contributors
- Cortisol rhythm patterns
- Stress events detected
- Breath sessions completed

### recovery_monthly
Monthly recovery summary:
- Stress patterns
- Autonomic balance trends
- Recovery consistency

---

## Fitness & Workouts

### fitness_weekly
Weekly workout summary:
- Workouts completed (type, duration, zones, calories)
- VO2 max readings
- Heart rate recovery metrics
- Training load

### fitness_monthly
Monthly fitness progress:
- Training load trends
- Workout frequency
- Cardiorespiratory fitness evolution
- VO2 max trends

---

## Respiratory Health

### sleep_respiratory_weekly
Weekly breathing during sleep:
- Snoring duration and percentage
- Coughing events
- Breathing regularity
- Sleep apnea indicators (if available)

### sleep_respiratory_monthly
Monthly respiratory trends:
- Breathing quality patterns
- Anomaly detection

---

## Metabolism (CGM Users)

### metabolism_weekly
Weekly glucose metrics:
- Average glucose
- Time in target range
- Glucose variability
- Notable meal responses

### metabolism_monthly
Monthly metabolic health:
- Glucose trend analysis
- Pattern insights

---

## Body Temperature

### temperature_weekly
Weekly skin temperature:
- Deviations from baseline
- Useful for illness detection
- Cycle tracking (females)

### temperature_monthly
Monthly temperature patterns:
- Baseline drift analysis
- Notable deviations

---

## GLP-1 Therapy Data

### glp1_profile
User's GLP-1 medication profile:
- Medication type (Ozempic, Wegovy, Mounjaro, Zepbound, Saxenda)
- Current dose (mg)
- Dose schedule (weekly/daily)
- Start date
- Titration history
- Healthcare provider notes (if any)

### glp1_dose_history
Complete dose administration log:
- Dose number (sequential)
- Administration timestamp
- Dose amount (mg)
- Medication name
- Injection site (if logged)
- Per-dose cycle metrics (7 days before and after each dose):
  - Daily HRV, RHR, sleep score, deep sleep, recovery, temperature

### glp1_daily_insight
Daily GLP-1 context for insights:
- Days since last dose
- Hours since last dose
- Current dose number
- Dose-anchored baseline (7-day avg before current dose)
- Current metrics vs baseline deviations
- Post-dose pattern (Day 1-2 dip characteristics)
- Recovery pattern (typical recovery days)
- Baseline trend across doses (improving/stable/declining)
- Confidence scores (T/B/C)
- Safety flags if any
- Detected pattern type

### glp1_symptoms
GLP-1 related symptom log:
- Symptom name (nausea, fatigue, etc.)
- Severity (mild, moderate, severe)
- Timestamp logged
- Associated dose context
- Duration (if tracked)

### glp1_weekly_summary
Weekly GLP-1 therapy summary:
- Doses administered this week
- Average post-dose HRV response
- Average recovery window
- Symptom frequency and severity
- Week-over-week baseline comparison
- Compliance notes

### glp1_monthly_progress
Monthly GLP-1 therapy overview:
- Total doses administered
- Dose titration events
- Baseline HRV/RHR trend over month
- Recovery pattern evolution
- Symptom trend analysis
- Long-term adaptation indicators

---

## Menstrual Cycle

### menstrual_cycle
Cycle tracking data:
- Current phase
- Cycle length
- Period dates
- Ovulation prediction
- Phase-specific patterns (HRV, RHR, temperature by phase)

---

## Longevity & Biological Ages

### biological_ages
Longevity markers:
- Cardio age vs chronological age
- Brain age
- Pulse age
- Trends over time

---

## Lifestyle & Wellness

### lifestyle_weekly
Weekly lifestyle metrics:
- Vitamin D exposure/absorption
- Screen time patterns
- Wellness activity completion

### lifestyle_monthly
Monthly lifestyle summary:
- Sun exposure trends
- Digital wellness patterns
- Activity consistency

---

## User Context & Profile

### user_context
User's baselines and profile:
- Physiological baselines (HRV, RHR, temperature - overall/day/night)
- Physical profile (height, weight, age, gender, activity level)
- Sleep schedule preferences
- Sleep stage baselines
- Menstrual phase baselines (females)

### user_profile
Persistent health facts:
- Medical conditions
- Allergies
- Current medications
- Family history
- Lifestyle factors
- Health preferences

---

## Other Documents

### blood_work
Lab results:
- Lab partner and package info
- Biomarkers with values, units, and reference ranges

### user_upload
User-uploaded documents:
- Structured summaries from uploaded medical documents
- Lab reports, prescriptions, medical reports

### data_inventory
Available data summary:
- What data types exist for the user
- Date ranges available
- Helps determine what can be analyzed

---

## Metric Quick Reference

| Metric | Found In |
|--------|----------|
| HRV | sleep_daily, sleep_weekly, sleep_monthly, cardiovascular_weekly, recovery_weekly, user_context |
| Resting Heart Rate | cardiovascular_weekly, cardiovascular_monthly, fitness_weekly, user_context |
| Sleep Efficiency | sleep_daily, sleep_weekly, sleep_monthly |
| Sleep Stages (Deep/REM/Light) | sleep_daily (minutes), sleep_weekly/monthly (percentages) |
| Steps | movement_daily, movement_weekly, movement_monthly |
| VO2 Max | fitness_weekly, fitness_monthly |
| Restoration/Recovery % | recovery_weekly, recovery_monthly |
| Glucose | metabolism_weekly, metabolism_monthly |
| Vitamin D | lifestyle_weekly, lifestyle_monthly |
| Body Temperature | temperature_weekly, temperature_monthly, sleep_daily |
| GLP-1 Dose History | glp1_profile, glp1_dose_history |
| GLP-1 Post-Dose Response | glp1_daily_insight, glp1_dose_history |
| GLP-1 Symptoms | glp1_symptoms |
| GLP-1 Baseline Trend | glp1_daily_insight, glp1_weekly_summary, glp1_monthly_progress |

**IMPORTANT**: Only claim data is "missing" AFTER verifying it's not in the appropriate document types listed above.

**GLP-1 NOTE**: For users on GLP-1 therapy, always check `glp1_daily_insight` for dose context before interpreting HRV, RHR, or recovery metrics. Post-dose physiological changes are expected and should be contextualized.
