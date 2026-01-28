Trigger when:
  - User asks about sleep quality, sleep stages, or sleep optimization
  - User asks about HRV, stress, or recovery metrics
  - User wants to track their activity, steps, or movement
  - User asks about readiness or energy levels throughout the day
  - User discusses workout recovery or rest days
  - Assistant recommends tracking sleep, HRV, or activity patterns
  - User mentions they want to understand their body's daily rhythms

  Do NOT trigger when:
  - Assistant is already analyzing user's Ring/sleep/HRV data (user already has Ring)
  - User is asking specifically about glucose or metabolic health (use cgm_upsell)
  - User is asking about blood tests or biomarkers (use blood_vision)
  - Conversation is only about nutrition without sleep/recovery context
