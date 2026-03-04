---
name: retirement-projections
description: "Build a retirement financial plan with cash flow projections, Monte Carlo analysis, tax-optimized withdrawal strategies, and historical backtesting"
arguments:
  - name: scenario
    description: "Optional: brief description of the scenario to model (e.g., 'couple, ages 55 and 52, want to retire at 60')"
    required: false
---

Use the `retirement-projections` skill to build a comprehensive retirement financial plan for the user.

{{#if scenario}}
The user wants to model this scenario: {{scenario}}

Begin by confirming the details provided and gathering any missing required inputs per the skill's Step 1 (Gather Client Data).
{{else}}
Begin by gathering the required client data per the skill's Step 1. Ask the user about their retirement planning goals and collect all required inputs before proceeding.
{{/if}}

Follow the complete skill workflow through all 10 steps. Do not skip steps or silently default required inputs.
