# Instruction Adherence Test Scenarios

## Objective

Check whether the AI Travel Planner follows all important requirements provided by the user.

The model should not ignore or modify a constraint just to generate a convenient itinerary.

---

## IA-001: Budget Constraint

### Prompt

Plan a 4-day Goa trip for 2 people with a total budget of INR 25,000.

The budget must include:
- Hotel
- Food
- Local transport
- Sightseeing

Do not exceed INR 25,000.

### What to Check

- Total cost stays within INR 25,000
- All requested expense categories are included
- Cost calculation is correct

### Failure Condition

Fail if the estimated total exceeds the budget or if a required expense is excluded to make the itinerary appear within budget.

---

## IA-002: Dietary Restriction

### Prompt

Plan a 3-day Jaipur trip for a vegetarian couple. We do not eat eggs or non-vegetarian food. Suggest meals and restaurants for each day.

### What to Check

- Vegetarian requirement is followed
- Eggs are not recommended
- Non-vegetarian dishes are not recommended

### Failure Condition

Fail if the model recommends food that violates the stated dietary requirements.

---

## IA-003: Transport Restriction

### Prompt

Plan a 5-day Kerala trip. I do not want to travel by flight anywhere during the trip.

### What to Check

Check the complete response, including optional recommendations and alternatives.

### Failure Condition

Fail if a flight is recommended anywhere in the itinerary despite the explicit restriction.

---

## IA-004: Multiple Constraints

### Prompt

Plan a 3-day Goa trip for a couple.

Requirements:
- Maximum budget: INR 20,000
- Vegetarian food only
- No water sports
- Stay near Candolim
- At least one fort
- At least one beach every day

### What to Check

Verify every requirement individually.

### Failure Condition

Fail if one or more explicit requirements are missed or contradicted.

---

## IA-005: Exclusion Constraint

### Prompt

Plan a 2-day Mumbai itinerary.

Do not include:
- Gateway of India
- Marine Drive
- Elephanta Caves

Suggest other places instead.

### What to Check

The excluded attractions should not appear as itinerary recommendations.

### Failure Condition

Fail if the model includes any explicitly excluded attraction in the itinerary.

---

## IA-006: Preference vs Requirement

### Prompt

Plan a 3-day Goa trip.

I prefer staying near the beach, but my hotel MUST cost less than INR 2,500 per night.

### What to Check

The mandatory hotel budget should take priority over the optional beach preference if both cannot be satisfied.

### Failure Condition

Fail if the model violates the mandatory INR 2,500 limit just to satisfy the preferred location.

---

## Result Recording

For every failure, record:

- Requirement that was given
- Model response
- Requirement that was missed
- Exact evidence from the response
- Severity
- User impact
