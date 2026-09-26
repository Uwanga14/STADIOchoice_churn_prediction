# Feature Engineering

## Objective

The objective of feature engineering is to create meaningful variables that better represent subscriber engagement and churn risk.

## Input Dataset

**Input File:** `preprocessed.csv`

## Engineered Features

### 1. Engagement Score

```python
engagement_score = watch_hours * avg_watch_time_per_day
```

Measures overall platform engagement.

---

### 2. Watch Intensity

```python
watch_intensity = watch_hours / (number_of_profiles + 1)
```

Measures viewing activity relative to account sharing.

---

### 3. Inactive Customer

```python
inactive_customer = (last_login_days > 30)
```

Identifies subscribers who have not used the platform for an extended period.

---

### 4. Multiple Profiles

```python
multiple_profiles = (number_of_profiles > 2)
```

Identifies accounts shared by multiple users.

---

### 5. Recency Score

```python
recency_score = 1 / (last_login_days + 1)
```

Measures how recently a subscriber has used the platform.

---

### 6. Low Engagement

```python
low_engagement = (watch_hours < 5)
```

Identifies subscribers with very low activity levels.

---

### 7. High Engagement

```python
high_engagement = (watch_hours > 20)
```

Identifies highly active subscribers.

---

### 8. Shared Account

```python
shared_account = (number_of_profiles >= 3)
```

Represents accounts likely used by multiple viewers.

---

### 9. Daily Engagement Ratio

```python
daily_engagement_ratio = avg_watch_time_per_day / (watch_hours + 1)
```

Measures viewing consistency across the month.

## Feature Importance Findings

The strongest churn indicators were:

- Last Login Days
- Watch Hours
- Recency Score
- Low Engagement
- High Engagement

These results suggest that platform activity and engagement behaviour are the primary drivers of customer churn.

## Output Dataset

**Output File:** `feature_engineered.csv`

## Related Script

**File:** `feature_engineering.py`

## How to Run

```bash
python feature_engineering.py
```

## Expected Benefit

The engineered variables improve the representation of customer behaviour and engagement patterns, which are strongly associated with subscriber churn.
