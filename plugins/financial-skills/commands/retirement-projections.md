---
description: "Build a retirement financial plan with cash flow projections, Monte Carlo analysis, tax-optimized withdrawal strategies, and historical backtesting"
argument-hint: "<scenario description>"
---

Use the `retirement-projections` skill to build a comprehensive retirement financial plan for the user.

{{#if arguments}}
The user wants to model this scenario: {{arguments}}

Begin by confirming the details provided and gathering any missing required inputs per the skill's Step 1 (Gather Client Data).
{{else}}
Begin by gathering the required client data per the skill's Step 1. Ask the user about their retirement planning goals and collect all required inputs before proceeding.
{{/if}}

Follow the complete skill workflow through all 10 steps. Do not skip steps or silently default required inputs.
