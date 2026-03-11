# Sample Scenario: George & Sarah

This is a canonical worked example for validating the retirement projections skill. Use this scenario to verify that the model, scripts, and deliverables produce reasonable results.

## Client Data

**People:**
- George, age 55 (born 1971)
- Sarah, age 52 (born 1974)

**Target:** George retires at 67 (year 12), Sarah retires at 65 (year 13)

**Accounts:**
| Account | Type | Balance | Allocation |
|---------|------|---------|-----------|
| George's 401(k) | Traditional | $850,000 | 65/30/5 |
| Sarah's 401(k) | Traditional | $620,000 | 60/35/5 |
| Joint taxable | Brokerage | $380,000 | 70/25/5 |
| Joint Roth IRA | Roth | $150,000 | 80/20/0 |
| Emergency fund | Cash | $60,000 | 0/0/100 |
| **Total** | | **$2,060,000** | |

**Income:**
- George: $285,000/year (software engineering)
- Sarah: $165,000/year (marketing director)
- Combined: $450,000/year

**Social Security (FRA estimates from ssa.gov):**
- George: $3,800/month ($45,600/year) at FRA 67
- Sarah: $2,700/month ($32,400/year) at FRA 67

**401(k) Contributions:**
- Both maxing out with catch-up (age 50+): $30,500/person/year
- George's employer match: 4% of salary
- Sarah's employer match: 3% of salary

**State:** Virginia (progressive brackets, top rate 5.75%)

## Spending

**Obligatory (non-negotiable):**
| Category | Annual |
|----------|--------|
| Mortgage (payoff at George age 63, year 8) | $42,000 |
| Property tax + insurance | $14,000 |
| Healthcare premiums | $12,000 |
| Utilities | $7,200 |
| Food | $18,000 |
| Transportation (2 cars) | $12,000 |
| Insurance (life, umbrella) | $4,800 |
| **Obligatory total** | **$110,000** |

**Discretionary:**
| Category | Annual |
|----------|--------|
| Travel | $25,000 |
| Dining out | $12,000 |
| Entertainment/hobbies | $8,000 |
| Gifts/charitable | $10,000 |
| Clothing | $5,000 |
| **Discretionary total** | **$60,000** |

**Total current spending:** $170,000/year

**Post-mortgage spending (year 8+):** $128,000/year obligatory drops to $68,000/year

## One-Time Expenses

| Expense | Year | Amount | Funding Source |
|---------|------|--------|---------------|
| Daughter's college (4 years) | 7-10 | $50,000/year ($200K total) | 529 ($85K) + taxable |
| Kitchen renovation | 5 | $45,000 | Taxable |
| Car replacement (George) | 8 | $40,000 | Cash/taxable |
| Car replacement (Sarah) | 11 | $35,000 | Cash/taxable |

## Expected Outputs

### Key Metrics (approximate)
- Portfolio at retirement (year 12): ~$3.8-4.2M
- George SS at claiming (year 12 with COLA): ~$61,000-65,000
- Sarah SS at claiming (year 15 with COLA): ~$46,000-49,000
- Combined SS at year 30 (George 84): ~$180,000-200,000

### Sanity Checks
- **Working year effective tax rate:** 24-30% on $450K combined income (with 401k deductions)
- **Portfolio growth:** Should roughly double from $2.06M to ~$4M over 12 years (401k contributions add ~$1.2M, returns add ~$1M)
- **Late-life SS coverage:** By age 85+, SS with COLA should cover 100%+ of realistic spending
- **Post-mortgage impact:** Obligatory expenses drop significantly at year 8, improving all metrics

### What to Validate
1. SS at George's claiming year should be ~$61K, not $45.6K (COLA missing if flat)
2. 401(k) contributions should reduce taxable income from $450K to ~$389K
3. College expenses should show portfolio dips in years 7-10
4. Mortgage payoff at year 8 should visibly reduce expenses
5. Virginia state tax should use progressive brackets (not flat 5%)
6. RMDs should start at age 75 (born 1960+) for both
7. Withdrawal strategy comparison should show $50-150K+ tax difference

## Using with Validation Scripts

Generate projections JSON in the format shown in `sample-projections.json`, then run:

```bash
python scripts/validate_model.py examples/sample-projections.json 12
python scripts/historical_backtest.py examples/sample-projections.json 12 30
```
