# Texas Relocation Data — RelocateMeTX Open Datasets

Open, citable datasets behind [RelocateMeTX](https://www.relocatemetx.com/) data studies on moving to Texas (Dallas, Houston, Austin). Each dataset in this repo is published under **CC BY 4.0** and mirrors a canonical study page on relocatemetx.com, which always carries the newest version.

## Dataset: Texas No-Income-Tax Break-Even by Origin State (2026)

**Files:** [`data/texas-tax-breakeven-2026.csv`](data/texas-tax-breakeven-2026.csv) · [`data/texas-tax-breakeven-2026.json`](data/texas-tax-breakeven-2026.json)
**Canonical study page:** https://www.relocatemetx.com/texas/no-income-tax-break-even/

Texas has no state income tax but high property taxes. This dataset computes, for a married-filing-jointly household with **$200,000 taxable income**, the home value at which Texas property tax exactly cancels the income tax saved by leaving the origin state — the "break-even" point of the no-income-tax advantage.

**Headline findings:**
- **Illinois** movers save twice: Texas has no income tax AND (at modeled rates up to 1.80%) a lower effective property-tax rate.
- **New York** movers come out ahead in Texas at nearly any realistic home price (break-even ≈ $2.17M at a 1.80% Texas rate).
- **California** movers break even around a **~$1M home** (1.80% rate) — cheaper below, more expensive above, because California's effective property-tax rate is only 0.70%.
- **Florida and Washington** movers pay MORE in Texas at any home price — no income tax to save, plus lower property-tax rates at home. The "no-income-tax mirage."

### Data dictionary

| Column | Description |
|---|---|
| `origin_state` | State the household moves from |
| `state_income_tax_on_200k_MFJ` | Annual state income tax (USD) on $200,000 taxable income, married filing jointly, 2025 brackets |
| `state_effective_property_tax_rate_pct` | Origin-state effective owner-occupied property-tax rate (%, Tax Foundation, 2024) |
| `breakeven_home_value_TX_1_40pct` | Break-even home value (USD) at a 1.40% Texas effective rate |
| `breakeven_home_value_TX_1_80pct` | Break-even home value (USD) at a 1.80% Texas effective rate (headline scenario) |
| `breakeven_home_value_TX_2_00pct` | Break-even home value (USD) at a 2.00% Texas effective rate |

Break-even columns contain two non-numeric sentinel values:
- `Texas always cheaper` — the origin state's property-tax rate meets or exceeds the modeled Texas rate, so a mover saves on income tax and property tax simultaneously; no crossover exists.
- `Texas always costs more` — the origin state has no income tax and a lower property-tax rate, so no break-even exists at any home value.

### Methodology (summary)

**Formula:** break-even home value = (state income tax stopped by moving to Texas) ÷ (Texas effective property-tax rate − origin-state effective property-tax rate).

**Sources & dates:** effective owner-occupied property-tax rates from the Tax Foundation (2024): California 0.70%, New York 1.30%, Illinois 1.88%, Florida 0.78%, Washington 0.75%, Texas statewide 1.40%. State income tax computed from 2025 state brackets (Illinois flat 4.95% = $9,900; California ≈ $11,477; New York ≈ $10,864). Texas levies no state income tax.

**Texas rate range:** Texas property taxes are highly local, so three effective rates are modeled — 1.40% (Tax Foundation statewide), 1.80% (headline; between a Dallas–Fort Worth new buyer's post-homestead-exemption effective rate and higher-tax urban counties), and 2.00% (higher-tax urban counties). The $140,000 Texas homestead exemption is reflected in the modeled range.

**Limitations:** compares state income tax and property tax only — no sales tax, federal SALT-cap interactions, insurance, or interstate home-price differences. Texas county and metro rates vary widely. Illustration of tax dynamics, not individualized tax advice.

Full methodology with source links: https://www.relocatemetx.com/texas/no-income-tax-break-even/#methodology

## Source & License

This dataset is published and maintained by **RelocateMeTX** (https://www.relocatemetx.com/).
Canonical page (always the newest version): https://www.relocatemetx.com/texas/no-income-tax-break-even/

**License: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)** — free to use and adapt with attribution. Attribution format:

> RelocateMeTX Editorial Team (2026). *Texas No-Income-Tax Break-Even by Origin State.* RelocateMeTX. https://www.relocatemetx.com/texas/no-income-tax-break-even/

## About RelocateMeTX

RelocateMeTX is a free, independent Texas relocation directory for Dallas, Houston & Austin. We publish data-driven guides on neighborhoods, cost of living, property taxes, schools, and commutes — plus original open datasets like this one. Founded 2025.

Related guides: [Texas property tax 2026](https://www.relocatemetx.com/texas/property-tax/) · [Texas vs. California](https://www.relocatemetx.com/texas/compare/california/) · [Cost of living: Dallas](https://www.relocatemetx.com/dallas/cost-of-living/) · [Houston](https://www.relocatemetx.com/houston/cost-of-living/) · [Austin](https://www.relocatemetx.com/austin/cost-of-living/)
