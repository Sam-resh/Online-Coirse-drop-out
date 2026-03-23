# Metrics & OKR Framework
## LearnOS — Course Completion Engine

---

## North Star Metric

**Weekly Courses Completed (WCC)**

*Definition*: The number of distinct courses marked as 100% complete by unique learners in a given week.

*Why this*: It captures both retention (learners must return) and depth (they must finish). It is immune to enrollment inflation (a learner who enrolls 10 courses and completes 0 contributes 0 WCC). It directly correlates with NPS and referral rate — our two biggest growth levers.

*Current baseline*: 4,200 WCC/week  
*12-month target*: 22,000 WCC/week (+424%)

---

## OKR Framework — FY2025

### Objective 1: Make LearnOS the platform where learners actually finish

| Key Result | Baseline | Q1 Target | Q2 Target | Year Target |
|-----------|----------|-----------|-----------|------------|
| KR1.1: Course completion rate | 12% | 18% | 25% | 35% |
| KR1.2: Learners with 7-day streak | 0 | 80K | 200K | 500K |
| KR1.3: Cohort enrollment rate | 0% | 5% of new | 15% of new | 30% of new |
| KR1.4: Smart Resume usage rate | — | 60% of eligible | 70% | 75% |

### Objective 2: Build a habit-forming learning experience

| Key Result | Baseline | Q1 Target | Q2 Target | Year Target |
|-----------|----------|-----------|-----------|------------|
| KR2.1: Day-7 learner retention | 18% | 26% | 34% | 42% |
| KR2.2: Day-30 learner retention | 8% | 13% | 18% | 24% |
| KR2.3: Avg sessions per learner/week | 1.2 | 1.8 | 2.5 | 3.8 |
| KR2.4: % learners with fixed learning time | 14% | 25% | 38% | 52% |

### Objective 3: Convert learning value into revenue

| Key Result | Baseline | Q1 Target | Q2 Target | Year Target |
|-----------|----------|-----------|-----------|------------|
| KR3.1: Trial → Paid conversion | 6% | 8% | 11% | 14% |
| KR3.2: Annual churn rate (Pro) | 38% | 35% | 30% | 26% |
| KR3.3: Net Revenue Retention | 94% | 97% | 103% | 112% |
| KR3.4: NPS score | 22 | 30 | 40 | 55 |

---

## Metric Hierarchy

```
NORTH STAR
Weekly Courses Completed (WCC)
         │
    ┌────┴────┐
    │         │
Input Metrics   Output Metrics
(we control)    (we track)
    │               │
    ├── D7 Retention     ├── NPS
    ├── Streak adoption  ├── Referral rate
    ├── Sessions/week    ├── Churn rate
    └── Resume usage     └── ARR
```

---

## Guardrail Metrics

These must NOT be hurt. Any feature release is rolled back if these breach thresholds.

| Guardrail | Threshold | Why |
|-----------|-----------|-----|
| Enrollment completion rate | Must not drop > 5% | Features can't add friction to starting |
| Instructor earnings | Must not drop > 3% | Creator economy health |
| Support ticket volume | Must not increase > 10% | Signals confusion or bugs |
| App store rating | Must stay ≥ 4.3 stars | Brand signal |
| Notification opt-out rate | Must not exceed 25% | Signals we're being too pushy |

---

## Measurement Infrastructure

| Metric | Tool | Update Frequency | Dashboard |
|--------|------|-----------------|-----------|
| WCC, completion rate | Data Warehouse (BigQuery) | Daily | Looker |
| Retention curves | Amplitude | Real-time | Amplitude |
| Feature adoption | Mixpanel | Real-time | Mixpanel |
| NPS | Delighted | Monthly survey | Delighted |
| Revenue metrics | Stripe + internal | Daily | Looker |
| A/B test results | Optimizely | Continuous | Optimizely |

---

*Reviewed by: VP Product, Head of Data, Growth Lead | March 2025*
