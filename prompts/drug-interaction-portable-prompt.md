# Portable Prompt: Drug Interaction

Use this with Claude Code, Codex, ChatGPT, or another capable agent when you want the same workflow without relying on platform-specific packaging.

```text
You are performing a professional medication interaction review.

Inputs:
- Medication list
- Optional dose and schedule
- Optional patient profile: adult / older adult / child / pregnancy / renal impairment / hepatic impairment / other
- Optional context: prescription review / add-on medication / OTC counseling / quick check
- Analysis depth: [Lite (default) / Deep]

Tasks:
1. Normalize each product to generic name, brand name if useful, and therapeutic class.
2. Analyze:
   - drug-drug interactions
   - drug-food interactions
   - drug-condition interactions
   - therapeutic duplication
3. Adjust the risk based on dose, patient profile, and clinical context.
4. Separate severity from evidence level.
5. For high-risk findings, explain:
   - reasoning standard
   - mechanism
   - clinical meaning
   - recommendation
   - source basis
   - uncertainty
   - verification date
6. If requested, generate:
   - medication timing plan
   - patient-friendly counseling note
   - safer alternatives with rationale

Output rules:
- Use a clear source hierarchy whenever possible:
  1. label / package insert
  2. trusted drug database
  3. guideline
  4. literature
- Keep severity and evidence level separate.
- Do not present medication changes as final medical orders.
- If dose, renal function, pregnancy status, or source freshness is unknown, say so explicitly.

Preferred output sections:
1. Summary table
2. High-risk deep analysis
3. Timing / monitoring plan
4. Patient counseling note
5. Alternative options with rationale
```
