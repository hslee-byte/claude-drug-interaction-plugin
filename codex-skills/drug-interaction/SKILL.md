---
name: drug-interaction
description: Analyze drug-drug, drug-food, drug-condition, and therapeutic-duplication risks from a medication list, adjust for dose and patient profile, propose monitoring and timing changes, and report severity separately from evidence level with source hierarchy, verification date, and uncertainty notes.
---

# Drug Interaction

Use this skill when the user wants professional medication interaction review from a list of drugs, supplements, or food interactions.

## Workflow

1. Normalize each medication to generic name, brand name if useful, and therapeutic class.
2. Collect or infer:
   - dose and schedule
   - patient profile
   - current clinical scenario
3. Check:
   - drug-drug interactions
   - drug-food interactions
   - drug-condition interactions
   - therapeutic duplication
4. Separate severity from evidence level.
5. For high-risk findings, explain:
   - mechanism
   - clinical impact
   - monitoring
   - timing or substitution options
6. If asked, create a patient-friendly medication schedule and counseling note.

## Output Rules

For clinically important findings, separate:

- Interaction conclusion
- Reasoning standard
- Mechanism
- Clinical meaning
- Recommendation
- Evidence level
- Source basis
- Uncertainty
- Verification date

Use source hierarchy whenever possible:

1. label / package insert
2. trusted drug database
3. guideline
4. literature

## Detailed Finding Template

```text
[Drug A] + [Drug B]

Interaction conclusion:
- What risk is present

Reasoning standard:
- Why the risk is graded at this level

Mechanism:
- PK / PD explanation

Clinical meaning:
- Symptoms, complications, timing, patient-specific risk modifiers

Recommendation:
- avoid / monitor / separate timing / dose adjustment / discuss alternative

Evidence level:
- high / medium / low

Source basis:
- label / database / guideline / literature

Uncertainty:
- missing dose, missing renal function, unclear duration, unverified latest source, etc.

Verification date:
- YYYY-MM-DD
```

## Constraints

- Do not replace physician or pharmacist judgment.
- Do not present medication changes as final orders.
- Keep severity and evidence level separate.
- For substitutions, explain why the alternative is safer and what still needs to be checked.
