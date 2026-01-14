# Document Type Schemas

Each document type contains specific fields. Use this reference to know what data is available.

**CRITICAL**: Before claiming ANY metric is "not found" or "missing", check this schema to identify which document type(s) contain that metric, then fetch those documents.

---

## Sleep Documents

### sleep_daily
Contains daily sleep data for a single night:
- **Sleep Score**: 0-100 overall score
- **Duration**: Total sleep in minutes
- **Sleep Window**: Bedtime start/end times
- **Stage Balance**: REM minutes, Deep minutes, Light minutes
- **Efficiency Signals**: Efficiency (%), Restfulness factor, HR drop factor
- **Physiological Markers**: Avg sleep HR (bpm), Lowest HR (bpm), **HRV (ms)**, Skin temperature delta
- **Score Contributors**: JSON with total_sleep, deep_sleep, rem_sleep, efficiency, hr_factor, temperature, restfulness contributors

### sleep_weekly
Contains weekly aggregated sleep data:
- **Overview**: Average score, Nights tracked, High score nights (>=85), Best night, Score trend vs previous week
- **Duration**: Average hours, Total hours, Longest night
- **Stages Mix**: REM %, Deep %, Light %
- **Schedule**: Median bedtime, Bedtime range (hours), Wake range (hours)
- **Efficiency**: Efficiency %, Restfulness, HR factor
- **Vitals**: Avg sleep HR (bpm), Lowest HR (bpm), **Avg HRV (ms)**, Temp deviation
- **Contributors**: Top positives and negatives

### sleep_monthly
Contains monthly aggregated sleep data (same structure as weekly with monthly scope):
- **Overview**: Average score, Nights tracked, High score nights, Best/worst nights, Score trend
- **Duration**: Average hours, Total hours, Longest/shortest nights
- **Stages Mix**: REM %, Deep %, Light %
- **Schedule**: Median bedtime/wake, Bedtime variation
- **Efficiency**: Efficiency %, Restfulness, HR factor
- **Vitals**: Avg sleep HR (bpm), Lowest HR (bpm), **Avg HRV (ms)**, Temp deviation

---

## Cardiovascular Documents

### cardiovascular_weekly
Contains weekly heart health data:
- **HRV Section**: Week avg (ms), Month avg (ms), Days tracked, Best/lowest days, Daily breakdown [date, avg_hrv, baseline, vs_baseline]
- **Resting HR**: Week avg (bpm), Month avg (bpm), Days tracked, Daily breakdown [date, night_rhr, day_rhr]
- **HR Recovery**: Count, Avg recovery (bpm), Workouts list [date, peak_hr, post_hr, recovery_value]
- **AFib Screening**: Count, Non-regular count, Screenings list [date, result, average_hr, indicator]

### cardiovascular_monthly
Contains monthly heart health data:
- **HRV**: Month avg (ms), Min, Max, Best/lowest days, Days tracked, Weekly breakdown
- **Resting HR**: Month avg (bpm), Min, Max, Best/highest days, Days tracked, Weekly breakdown
- **HR Recovery**: Count, Avg recovery, Best recovery
- **AFib**: Count, Non-regular count, Screenings list

---

## Movement Documents

### movement_daily
Contains daily activity data:
- **Overview**: Movement Index (0-100), State (optimal/good/needs attention), Tag, Score delta
- **Steps**: Total steps, Density score, Goal progress %
- **Activity**: Active hours, Active minutes, **Sedentary minutes**, Activity scores
- **Workout**: Workout factor, Frequency score, MET-mins, Active factor, Calories (kcal)
- **Phase Progress**: Goal progress %, Total steps, Movement index score

### movement_weekly
Contains weekly activity data:
- **Overview**: Average score, Best/low days, Optimal days (>=85), Score trend
- **Steps**: **Total steps**, **Average steps/day**, Goal days (100%+ progress)
- **Activity**: **Avg active hours**, **Avg active minutes**, **Avg sedentary minutes**
- **Workouts**: Count logged, Workout factor, Frequency score, Weekly MET-mins, Calories burned
- **Highlights**: High days (>=90), Low days (<70)

### movement_monthly
Contains monthly activity data (same structure as weekly with monthly scope)

---

## Recovery Documents

### recovery_weekly
Contains weekly recovery and stress data:
- **Overview**: Days tracked, Avg sleep score, Avg movement score, **Avg restoration (%)**, Avg cortisol score
- **Daily Breakdown**: Per-day [date, sleep_score, movement_score, restoration_pct, cortisol_score, stress_rhythm]
- **Contributors**: **Avg HRV contributor**, Avg deep sleep contributor, Avg REM contributor, **Avg efficiency contributor**, Avg consistency contributor, Avg restfulness
- **Stress**: Avg stress rhythm score, Avg stress before bed, Stress event count, Logged events list

### recovery_monthly
Contains monthly recovery data (same structure as weekly with monthly scope)

---

## Fitness Documents

### fitness_weekly
Contains weekly fitness and workout data:
- **Workouts**: Count, Total duration (mins), Workout types, Workouts list [date, name, type, duration, calories]
- **VO2 Max**: **Latest value (ml/kg/min)**, Latest date, **RHR value (bpm)**, Mobility level, Week values, Avg value
- **HR Recovery**: Count, Avg recovery (bpm), Best recovery, Recoveries list [date, value, peak_hr, next_hr]
- **Breath Sessions**: Session count, Total duration, Techniques, Sessions list

### fitness_monthly
Contains monthly fitness data:
- **Workouts**: Count, Total duration, Avg workouts/week, Types, Weekly breakdown
- **VO2 Max**: Record count, Avg/min/max values, First/last values, Trend
- **HR Recovery**: Count, Avg/best/lowest recovery

---

## Other Documents

### biological_ages
Contains biological age calculations:
- **Overview**: Chronological age (years), Overall age gap
- **Cardio Age**: Current age, Gap vs chronological, Last updated, Monthly avg, Trend
- **Brain Age**: Current age, Gap, Brain age index, Monthly avg, Trend
- **Glymphatic Health**: Clearance score (%), Brain aging speed (multiplier)
- **Sleep Quality Impact**: HRV score, Deep sleep score, Efficiency score
- **Pulse Age**: Current age (vascular health), Gap, Monthly avg, Trend
- **Vascular Metrics**: Aging speed factor, Arterial stiffness (AIx), Reflection index

### user_context
Contains user profile and baselines:
- **Physical Profile**: Age, Gender, Height (cm), Weight (kg), BMI, Activity level, Max HR, Days of data
- **Sleep Schedule**: Default/weekday/weekend bedtime and wake times, Baseline duration, Sleep pattern
- **Baseline HRV**: Overall (ms), Day (ms), Night (ms)
- **Baseline RHR**: Overall (bpm), Day (bpm), Night (bpm)
- **Baseline Temperature**: Overall, Day, Night (all in °C)
- **Sleep Stage Baselines**: Deep %, Light %, REM %, Awake %

### blood_work
Contains blood test results:
- **Sample Info**: Sample date, Lab partner, Test package name
- **Markers**: List of markers, each with: Title, Value, Unit, Range name, Lower/upper bounds (markers vary by test)

### metabolism_weekly
Contains glucose and metabolic data:
- **Overview**: Days tracked, Avg metabolic score, **Avg glucose (mg/dL)**, Glucose variability %, Time in range %
- **Daily Breakdown**: Per-day score, avg glucose, variability, time in range
- **Meal Analysis**: Total meals, Avg meal score (/10), High/low scoring meals, Best/worst meals
- **Fasting**: Session count, Total/avg time, Avg fasting score

### temperature_weekly
Contains body temperature data:
- **Overview**: Days tracked, Avg skin temperature (°C), Avg baseline, Avg deviation
- **Deviation Range**: Min to max deviation
- **Elevated/Low Days**: Count above/below 0.5°C from baseline
- **Daily Breakdown**: Per-day temperature, deviation, status

### lifestyle_weekly
Contains lifestyle tracking data:
- **Vitamin D**: Days tracked, Avg absorption, Avg progress %, Days meeting target, Outdoor time, Sun events
- **Screen Time**: Days tracked, Avg daily hours, Total weekly hours, Avg evening minutes, Daily breakdown

### menstrual_cycle
Contains menstrual cycle data:
- **Current Cycle**: Cycle start, Period end, Current day, Expected length, Current phase, Day in phase
- **Predictions**: Predicted ovulation, Fertility window status
- **History**: Total cycles, Avg cycle length, Range, Avg period length, Regularity

### sleep_respiratory_weekly
Contains sleep respiratory data:
- **Overview**: Nights analyzed, Avg snoring (mins/night, %), Avg coughing, Total bouts
- **Daily Breakdown**: Per-night snoring, coughing, bouts
- **Sound Events**: Total events, Breakdown by type
- **SpO2** (if available): Avg %, Range, Readings below 95%/90%

---

## Quick Reference: Where to Find Common Metrics

| Metric | Document Types |
|--------|---------------|
| **HRV** | sleep_daily, sleep_weekly, sleep_monthly, cardiovascular_weekly, cardiovascular_monthly, recovery_weekly, user_context (baseline) |
| **Sleep Efficiency** | sleep_daily, sleep_weekly, sleep_monthly |
| **Steps** | movement_daily, movement_weekly, movement_monthly |
| **Resting Heart Rate** | cardiovascular_weekly, cardiovascular_monthly, fitness_weekly, user_context (baseline) |
| **VO2 Max** | fitness_weekly, fitness_monthly |
| **Deep/REM/Light Sleep** | sleep_daily (minutes), sleep_weekly/monthly (percentages) |
| **Restoration %** | recovery_weekly, recovery_monthly |
| **Glucose** | metabolism_weekly, metabolism_monthly |
| **Body Temperature** | temperature_weekly, user_context (baseline) |
| **Calories** | movement_daily, movement_weekly, fitness_weekly |

---

## Important Guidelines

1. **Before claiming data is missing**: Always check this schema to identify which document types contain the metric you're looking for. Fetch those document types before concluding data is unavailable.

2. **Multiple sources**: Many metrics appear in multiple document types. If one source doesn't have the data, check others listed in the table above.

3. **Time granularity**: Daily documents have the most detailed data. Weekly/monthly documents have aggregated summaries. Choose based on what the user is asking about.

4. **Baseline vs current**: user_context contains baseline values (historical averages). Daily/weekly/monthly documents contain current/recent values.
