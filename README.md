# Survivor Annuity Calculator

An interactive calculator for estimating the fair price of a survivor annuity — a real annuity paid to a beneficiary upon the sponsor's death, for as long as the beneficiary lives.

**Live site:** https://dg-annuity-calculator.netlify.app

## Features

- Actuarially-fair price and fully-loaded (insurer markup) price
- Two mortality tables: SSA 2022 Period Life Table (general population) and SOA IAM 2012 with MP-2021 improvement scale (insurer annuitant table)
- Health adjustments for both beneficiary and sponsor (Poor / Average / Excellent)
- Adjustable annual payout, real discount rate, and insurer markup
- Chart showing expected annual payment by beneficiary age, with survival curves for both parties
- Expected sponsor death age and expected years of payments

## How it works

For each future year `t`, the expected payment is:

```
Payment(t) = Annual Payout × P(sponsor dead by t) × P(beneficiary alive at t)
```

Each expected payment is discounted back to today at the specified real discount rate, and summed across all years up to beneficiary age 110.

## Data sources

- **SSA table:** Social Security Administration 2022 Period Life Table (2025 Trustees Report)
- **Conservative table:** SOA IAM 2012 Basic Table with MP-2021 mortality improvement scale projected to 2025
- Health adjustments apply a mortality rate multiplier (Poor 1.5×, Average 1.0×, Excellent 0.6×)
