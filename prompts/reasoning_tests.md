# Reasoning Test Scenarios

## Objective

Evaluate the AI Travel Planner's ability to perform logical reasoning, numerical calculations, and generate realistic travel itineraries.

The model should produce plans that are internally consistent, practical, and logically correct.

---

## R-001: Budget Calculation

### Prompt

Plan a 3-day Goa trip for two people within a budget of INR 20,000.

Provide separate costs for:
- Hotel
- Food
- Transport
- Sightseeing

Also provide the final total.

### What to Check

- Individual costs are calculated correctly.
- Final total equals the sum of all categories.
- Budget is not exceeded.

### Failure Condition

The calculated total is incorrect or exceeds the budget.

---

## R-002: Arrival Time

### Prompt

I will arrive in Jaipur at 4:00 PM on Day 1.

Create a 3-day itinerary starting from my arrival.

### What to Check

- No activity is scheduled before arrival.
- Day 1 timing is realistic.

### Failure Condition

The itinerary contains activities before 4:00 PM.

---

## R-003: Departure Time

### Prompt

My train leaves Kochi at 9:00 AM on Day 4.

Plan a 4-day Kerala itinerary.

### What to Check

- Day 4 schedule allows enough time to reach the station.
- Activities do not conflict with departure.

### Failure Condition

The model schedules sightseeing after the departure time.

---

## R-004: Travel Distance

### Prompt

Plan a one-day Mumbai itinerary covering:

- Gateway of India
- Sanjay Gandhi National Park
- Juhu Beach
- Marine Drive

### What to Check

- Travel sequence is realistic.
- The itinerary is achievable in one day.

### Failure Condition

The itinerary is impractical or ignores travel time.

---

## R-005: Conflicting Requirements

### Prompt

Plan a luxury 5-day Maldives trip for two people with a total budget of INR 10,000.

### What to Check

- Does the model identify the conflict?
- Does it explain why the request is unrealistic?

### Failure Condition

The model pretends the request is achievable instead of identifying the limitation.

---

## R-006: Context Retention

### Prompt

I am planning a Goa trip.

My budget is INR 18,000.

I only eat vegetarian food.

(Next prompt)

Suggest restaurants for Day 2.

### What to Check

- Budget is still respected.
- Vegetarian requirement is remembered.

### Failure Condition

The model forgets previously provided constraints.

---

## Result Recording

For every reasoning failure, record:

- Prompt
- Expected behaviour
- Actual behaviour
- Evidence
- Severity
- User impact
