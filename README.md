# SKU Risk & Review Prioritization Analysis

## Business Problem

Retail and supply chain teams manage hundreds or thousands of SKUs, but analyst and planner time is limited.  
While all SKUs generate operational noise, **not all SKUs contribute equally to demand volatility, inventory instability, or business risk**.

The core challenge this project addresses:

- Which SKUs actually deserve review first?
- How can teams distinguish structural risk from random noise?
- Where should analysts focus to maximize operational impact?

This project develops a **data-driven SKU prioritization framework** that identifies high-risk SKUs, quantifies volatility concentration, and translates analytical insight into clear operational review priorities.

---

## Project Objectives

- Classify SKUs into actionable risk tiers (High, Medium, Low)
- Quantify demand and inventory volatility at the SKU level
- Rank SKUs by review urgency within each risk tier
- Determine whether volatility is broadly distributed or concentrated
- Convert analytical findings into defensible, operational decisions

---

## Analytical Approach

This project follows a **business-first analytics workflow** aligned with real-world planning and operations teams.

### Data Preparation (SQL)

- Cleaned SKU-level demand, pricing, promotion, and inventory data
- Engineered volatility metrics including:
  - Demand Coefficient of Variation (CV)
  - Discount volatility
  - Inventory stability measures
- Used SQL window functions to support ranking, cumulative contribution, and prioritization logic

### Risk Tier Construction

SKUs were segmented into risk tiers based on combined volatility signals:

- **High Risk:** Persistently volatile demand and unstable behavior
- **Medium Risk:** Moderate volatility with situational risk
- **Low Risk:** Stable demand and inventory behavior

### Prioritization Framework

Within each risk tier, SKUs were ranked by:

- Overall volatility contribution
- Review Priority Within Tier (1 = highest urgency)

This framework allows teams to focus on SKUs that **actually drive operational risk** while safely deprioritizing low-impact items.

---

## Dashboard 1: SKU Risk Tier Volatility Analysis

**Purpose:**  
Identify where risk exists and how demand volatility behaves across SKU risk tiers.

### Key Visuals and Insights

#### SKU Risk Prioritization Map
- Plots Demand CV against Days Inventory on Hand
- Highlights clustering of high-risk SKUs in volatile regions
- Shows low-risk SKUs exhibiting stable demand and inventory behavior

#### SKU Risk Tier Distribution
- Displays how SKUs are distributed across risk tiers
- Insight: High-risk SKUs represent a **small but critical subset**

#### Demand Volatility Concentration by Risk Tier
- Cumulative volatility curves show:
  - High-risk SKUs reach 80% of volatility very quickly
  - Low-risk volatility is spread across many SKUs
- Confirms that volatility is **concentrated, not evenly distributed**

#### Pricing and Promotion Consistency
- Pricing, discounting, and promotion rates are nearly identical across tiers
- Key insight: Demand volatility is **not driven by pricing behavior**
- Risk appears structural rather than promotional

---

## Dashboard 2: SKU Review Prioritization and Volatility Contribution

**Purpose:**  
Translate risk insights into **clear, actionable review decisions**.

### Key Visuals and Insights

#### SKU Risk and Review Priority Summary
- Consolidates risk tier, volatility metrics, inventory behavior, and review priority
- Designed for analyst handoff and operational planning review

#### Demand Volatility Concentration Within Risk Tiers
- Shows how volatility accumulates *within* each tier
- Insight: High-risk tiers require fewer SKU reviews to address most volatility

#### High-Risk SKU Review Priority
- Explicit ranking of high-risk SKUs by urgency
- Converts analytical insight directly into an actionable review order

---

## Quantified Business Impact (Estimated)

While this analysis uses a synthetic dataset, the prioritization framework is designed to translate directly to real-world operational environments. The following estimates illustrate how this approach would impact decision-making at scale.

### Review Efficiency Gains

- High-risk SKUs represent approximately **8% of total SKUs**
- These SKUs account for **~80% of cumulative demand volatility**
- Targeting reviews to this subset allows teams to:
  - Reduce SKU review volume by **~90%**
  - Maintain coverage over the majority of operational risk

**Illustrative example:**  
A planning team reviewing 500 SKUs weekly could narrow focus to ~40 high-impact SKUs without materially increasing risk exposure.

---

### Analyst and Planner Time Savings

Assuming:
- 20–30 minutes per SKU review
- Weekly or biweekly review cadence

Prioritized reviews enable:
- **15–25 analyst hours saved per review cycle**
- **700–1,200 hours saved annually** for a small planning team

Freed capacity can be reallocated to:
- Root-cause analysis
- Forecast adjustments
- Cross-functional planning support

---

### Inventory and Volatility Risk Reduction

By identifying SKUs with:
- High demand variability
- Low inventory coverage
- Disproportionate volatility contribution

Teams can intervene earlier through:
- Inventory buffer adjustments
- Forecast overrides
- Supplier or replenishment policy changes

**Expected outcome:**  
Reduced likelihood of stockouts, overstocks, and emergency replenishment actions.

---

### Decision Quality Improvements

Without prioritization:
- SKU reviews are evenly distributed
- Analyst effort is diluted across low-impact items

With this framework:
- Review decisions are ranked, transparent, and defensible
- Stakeholders can clearly justify why specific SKUs are reviewed first
- Discussions shift from *what to review* to *how to fix issues*

---

## Key Business Takeaways

- A small subset of SKUs drives the majority of demand volatility
- Pricing and promotions are not the primary drivers of instability
- Risk-aware prioritization significantly reduces review overhead
- Demand volatility is highly concentrated in a small subset of High-risk SKUs, enabling targeted intervention rather than broad inventory changes.
- Low-risk SKUs account for the majority of inventory but contribute disproportionately less volatility, suggesting current inventory buffers are sufficient.
- Focused SKU reviews improve operational efficiency and decision quality

---

## Tools and Technologies

- **SQL:** Data cleaning, window functions, ranking and cumulative logic
- **Tableau:** Exploratory analysis and interactive dashboards
- **Business Analytics:** Risk segmentation and prioritization modeling

---

## Practical Use Case

In a production environment, this analysis would support:

- Weekly SKU review meetings
- Demand planning workflows
- Exception-based inventory management
- Executive reporting on operational risk

---

## Potential Extensions

- Time-series tracking of SKU risk tier movement
- Automated alerts for volatility threshold breaches
- Integration with forecast accuracy metrics
- Scenario testing for inventory policy changes