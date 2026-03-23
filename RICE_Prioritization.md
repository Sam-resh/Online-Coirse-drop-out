# RICE Prioritization Framework
## LearnOS — Course Completion Engine Features

---

**RICE Score = (Reach × Impact × Confidence) / Effort**

- **Reach**: How many users affected per quarter (1–10 scale, 10 = all users)
- **Impact**: Effect on the north star metric (1=minimal, 3=low, 6=medium, 9=high, 10=massive)
- **Confidence**: How sure are we the impact estimate is right (%, based on research quality)
- **Effort**: Person-weeks of engineering + design work

---

## Feature Scoring

| Feature | Reach | Impact | Confidence | Effort | RICE Score | Priority |
|---------|-------|--------|-----------|--------|-----------|----------|
| **Milestone Celebrations** | 10 | 6 | 90% | 1 | **54.0** | P0 🔴 |
| **Smart Resume Engine** | 10 | 7 | 90% | 2 | **31.5** | P0 🔴 |
| **Commitment Contract** | 8 | 8 | 75% | 2 | **24.0** | P0 🔴 |
| **Learning Streak System** | 9 | 9 | 85% | 3 | **22.95** | P0 🔴 |
| **Accountability Buddy** | 7 | 7 | 75% | 3 | **12.25** | P1 🟡 |
| **Cohort Enrollment** | 6 | 9 | 70% | 5 | **7.56** | P1 🟡 |
| **Modality Switcher** | 7 | 7 | 65% | 5 | **6.37** | P1 🟡 |
| **Daily Lesson Surface** | 8 | 8 | 65% | 7 | **5.94** | P2 🟢 |
| **AI Pacing Engine** | 8 | 9 | 60% | 8 | **5.40** | P2 🟢 |
| **Vacation Mode** | 6 | 5 | 85% | 2 | **12.75** | P1 🟡 |
| **Progress Export / Resume PDF** | 4 | 4 | 80% | 2 | **6.4** | P3 ⚪ |

---

## Scoring Rationale

### Milestone Celebrations (RICE: 54.0)
- **Reach=10**: Every learner who hits 25/50/75/100% is affected
- **Impact=6**: Medium-high; proven in gaming/fitness apps to reinforce completion behavior
- **Confidence=90%**: Strong analogous evidence from Fitbit, Duolingo, Headspace
- **Effort=1**: Primarily front-end animation + analytics event; no new API required

### Smart Resume Engine (RICE: 31.5)
- **Reach=10**: Every returning learner hits this
- **Impact=7**: Directly addresses the "re-entry friction" root cause from research
- **Confidence=90%**: Diary studies + session data confirm re-entry is a drop-off trigger
- **Effort=2**: Needs new recommendation layer, but data already exists

### Commitment Contract (RICE: 24.0)
- **Reach=8**: Applied to new enrollees; existing users would need a separate prompt
- **Impact=8**: Research shows high intent at enrollment; capturing it has proven impact
- **Confidence=75%**: Strong theory, but no A/B test evidence yet on LearnOS users
- **Effort=2**: Enrollment flow addition + pacing plan generator

### Learning Streak System (RICE: 22.95)
- **Reach=9**: Visible to most active users
- **Impact=9**: Highest potential impact — Duolingo data shows 8x retention lift
- **Confidence=85%**: Very strong analogous evidence; some risk of wrong tone for professional learning
- **Effort=3**: New microservice required; timezone complexity; streak shield mechanic

---

## Priority Sequence (Recommended)

### Phase 1 — Ship First (Highest RICE, Lowest Risk)
1. Milestone Celebrations
2. Smart Resume Engine
3. Commitment Contract
4. Vacation Mode (low effort, reduces churn)

### Phase 2 — Ship Second (High Impact, Medium Effort)
5. Learning Streak System (build new service)
6. Accountability Buddy
7. Cohort Enrollment

### Phase 3 — Ship Later (Strategic Bets, High Effort)
8. Modality Switcher
9. Daily Lesson Surface
10. AI Pacing Engine

---

## Trade-off Decisions

**Why Streaks aren't P0 despite high impact**: The streak service requires new infrastructure (microservice + timezone logic). Milestone Celebrations and Smart Resume ship faster and establish trust before the bigger bet.

**Why AI Pacing is P2 despite high impact**: 6-week Data Science build time. We need behavioral data from Phase 1 features to train the model effectively. Ship foundation first.

**Why Cohort is P1 not P0**: Community moderation is a new operational capability LearnOS doesn't have. Needs policy, tooling, and headcount that aren't ready in Q1.
