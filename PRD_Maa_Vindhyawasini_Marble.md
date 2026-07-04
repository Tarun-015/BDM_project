# PRD: Maa Vindhyawasini Marble — Sales & Inventory Analytics Dashboard

**Author:** Tarun Chaudhary
**Course context:** BDM Capstone Project, IIT Madras BS Degree Program
**Tools:** Python (Pandas, Matplotlib), Power BI, Excel

---

## 1. Title
Retail Sales & Inventory Analytics for Maa Vindhyawasini Marble — a data analysis project and dashboard built to help a 20+ year old tiles/marble/sanitary dealership in Ghazipur, UP understand its sales trends and stop losing money to unsold stock.

---

## 2. Problem Statement
The shop's owner, Mrs. Anju Saraf, has been running the business on instinct for two decades. She knows sales go up and down but has no idea *why*, and she has never systematically checked whether the stock she's buying actually matches what sells. Two concrete symptoms:

1. She can't tell if a bad month is a one-off or the start of a real decline — so she can't plan.
2. Money is stuck in slow-moving or dead stock (tiles/marble that just sit in the store), which she can't quantify, so cash flow gets tight without a clear reason why.

There is currently zero structured record-keeping analysis — everything is in raw billing books/registers, not usable for decisions.

---

## 3. Background
Maa Vindhyawasini Marble is an authorized Varmora dealer, family-run, now second-generation, employing 20–25 people. It sells to both individual home builders and contractors. Tiles/marble/sanitary retail is a high-ticket, low-frequency, inventory-heavy business — a wrong bulk purchase call ties up real capital for months. Competition in Ghazipur has increased pricing pressure recently, which is what pushed the owner to want a real look at the numbers instead of gut feel.

This project reuses the 5 years of sales + purchase billing data described in the original BDM proposal (product name, quantity, price for both sales and purchases) as the raw input.

---

## 4. Goals & Objectives
- Understand whether revenue over the last 5 years is growing, flat, declining, or seasonal.
- Identify which products (out of 30+ categories) actually drive revenue vs. which just sit on shelves.
- Quantify how much stock is dead/slow-moving and how much capital that represents.
- Give the owner a simple, non-technical dashboard she can actually check monthly — not a one-time PDF she reads once and forgets.
- Turn the analysis into 3–5 concrete, actionable purchasing recommendations (not just "sales are down").

---

## 5. Success Metrics
Being honest about what's *known* vs. *targeted*, since no analysis has been run yet:

| Metric | Status | Notes |
|---|---|---|
| 5-year revenue trend classified (growth/flat/decline/seasonal) | Target — output of analysis | Not yet known |
| % of SKU categories classified as dead/slow-moving (FSN) | Target — output of analysis | Do NOT assume 25%; that number isn't in your source data yet. Report whatever the data shows. |
| Revenue share concentration (ABC — e.g. what % of revenue comes from top 20% of SKUs) | Target — output of analysis | |
| EOQ/ROP recommendations delivered for top revenue-driving SKUs | Target deliverable | e.g. "for top 10 ABC-A items" |
| Dashboard usable by owner without help (self-check) | Target — qualitative | Ask her directly after handover |
| Estimated capital freed up if recommendations followed | Target — to calculate from dead stock value | Only claim a number once you calculate it from real purchase-price × dead-stock-quantity data |

If, once the real analysis is done, you get a number like "22% of inventory value is dead stock" — great, that becomes a genuine, defensible resume line. Don't pre-write the number now.

---

## 6. Target Users
- **Primary:** Mrs. Anju Saraf (owner) — needs simple visual answers, not raw data tables.
- **Secondary:** Any family member/manager who helps with purchasing decisions day-to-day.

There is no external customer-facing user here — be honest that this is a one/two-user internal tool, not a multi-persona product.

---

## 7. User Personas
Only two realistic personas exist for this project — don't inflate this section.

**Persona 1 — The Owner (Mrs. Saraf)**
- Non-technical, decades of tacit market knowledge, limited time.
- Wants: "Is my business okay? What should I stop buying?"
- Will not open Python or raw Excel sheets. Needs Power BI dashboard or a printed one-pager.

**Persona 2 — The Purchasing Decision-Maker** (could be the same person or staff)
- Needs: reorder points and quantities for top-selling products, in plain numbers ("reorder when stock hits X units").

---

## 8. User Stories
- As the owner, I want to see whether this year's sales are better or worse than last year, so I know if I should worry.
- As the owner, I want to see which products just sit in my store for months, so I stop reordering them.
- As the purchasing person, I want a reorder quantity/reorder point per major product, so I don't run out or over-order.
- As the owner, I want the dashboard in simple language (not "ABC classification jargon") so I can actually use it without someone explaining it every time.

---

## 9. Scope
- Cleaning and structuring 5 years of sales + purchase records into an analyzable format.
- Sales trend analysis (monthly/yearly, seasonality check).
- ABC analysis on revenue contribution across 30+ product categories.
- FSN analysis to flag dead/slow stock.
- EOQ and ROP/safety stock calculation for top revenue-driving categories.
- A Power BI dashboard (or Excel dashboard if Power BI access is a constraint) summarizing all of the above for the owner.
- A short set of written recommendations (3–5 concrete actions).

---

## 10. Out of Scope
- Real-time/live data integration (billing system stays manual; this is a periodic/manual-refresh analysis, not a live system).
- Multi-store or multi-branch analysis (this is a single showroom).
- Automated reordering/procurement system — this project *recommends* reorder points, it does not execute purchases.
- Customer-level CRM or loyalty analysis — out of scope, not part of the original data.
- Forecasting demand for brand-new (never-sold-before) products.

---

## 11. Functional Requirements
1. Data cleaning pipeline (Python/Pandas) to standardize 5 years of sales + purchase data into one structured table.
2. Sales trend module: monthly/yearly revenue charts, YoY comparison, seasonality flags.
3. ABC classification module: rank all 30+ categories by revenue contribution, split into A/B/C tiers.
4. FSN classification module: rank/tag products by movement speed (fast/slow/non-moving), based on last-sold date and turnover rate.
5. EOQ calculator: for each ABC-A product, compute economic order quantity given estimated ordering + holding cost assumptions.
6. ROP/Safety stock calculator: reorder point per ABC-A product based on lead time and demand variability.
7. Dashboard (Power BI): revenue trend view, ABC breakdown view, FSN/dead-stock view, and a recommendations summary page — built so the owner can filter by product category and by year.
8. Exportable one-pager (PDF/Excel) recommendation sheet, since the owner may not always have Power BI open.

---

## 12. Non-Functional Requirements
- **Usability:** Dashboard must be understandable by a non-technical retail owner in under 5 minutes of walkthrough — no analytics jargon on the visible dashboard labels (e.g., say "Slow-moving stock" not "FSN-tagged N-category").
- **Data privacy:** Sales/purchase figures are business-sensitive; data stored locally, not uploaded to public repos or shared drives without owner's consent.
- **Reproducibility:** Python scripts should be re-runnable on updated data (e.g., next year's records) without a rewrite.
- **Performance:** Not a concern at this data volume (a few thousand rows over 5 years) — no need to over-engineer for scale.
- **Maintainability:** Excel/Power BI file structured so a non-programmer (owner's staff) could refresh it with new monthly data.

---

## 13. Assumptions
- 5 years of sales and purchase billing records are complete enough (no major missing months/years) to support trend analysis.
- Product categorization in the raw records is consistent enough over 5 years to compare like-for-like (if product names/SKUs changed over time, this needs cleanup work).
- The owner is willing to share actual price/cost data, not just quantities (needed for margin and EOQ analysis).
- Ordering cost and holding cost inputs for EOQ will have to be estimated/approximated with the owner (they likely don't have a formal cost accounting system) — these will be assumptions stated openly in the report, not verified accounting figures.

---

## 14. Dependencies
- Timely access to raw sales/purchase registers from the shop (physical or digital).
- Owner's availability for periodic interviews to sanity-check findings and validate qualitative context (e.g., "was this dip because of a local event, not a real decline?").
- Access to Power BI (desktop, free version is enough) and Python environment (Pandas/Matplotlib) for the analysis.

---

## 15. Constraints
- Single-person academic project — no team, so scope must stay realistic for one person over the semester timeline.
- Real business data with likely inconsistencies (handwritten registers, missing entries, informal product naming) — expect significant time spent on data cleaning, more than the "textbook" version of this project would need.
- No formal ERP/accounting system at the shop — cost/margin figures may be approximations, not exact.
- Academic deadline constraints (per your Gantt chart, roughly Jan–June 2026).

---

## 16. User Flow
1. Owner/staff opens the Power BI dashboard (or receives the PDF one-pager).
2. Lands on a summary page: this year vs last year revenue, in one line + one chart.
3. Clicks into "Product Performance" → sees ABC tiers (which products earn the most).
4. Clicks into "Dead Stock" → sees which products haven't moved and how much capital is stuck.
5. Clicks into "Reorder Guide" → sees simple reorder point/quantity per top product.
6. Reads a final "Recommendations" page in plain language.

---

## 17. Wireframes / Mockups
Not building interactive mockups for this — a Power BI dashboard IS the interface, so wireframing separately is redundant effort. Recommended page layout instead:

- **Page 1 – Overview:** Revenue trend line (5 years), YoY % change callout, seasonality note.
- **Page 2 – Product Performance (ABC):** Bar chart of category revenue share, A/B/C tier table.
- **Page 3 – Inventory Health (FSN):** Fast/Slow/Non-moving breakdown, dead stock value estimate.
- **Page 4 – Reorder Guide:** Table of top products with EOQ, ROP, safety stock.
- **Page 5 – Recommendations:** 3–5 bullet, plain-language action points.

---

## 18. Acceptance Criteria
- All 5 years of sales and purchase data are represented in the cleaned dataset with no unexplained gaps.
- Revenue trend classification is stated with a clear reasoned basis (e.g., "declining in the last 2 years, driven by category X"), not a vague impression.
- ABC and FSN classifications are computed from actual data, with visible methodology (not asserted without calculation).
- EOQ/ROP numbers are calculated with stated formulas and stated cost assumptions (assumptions must be documented, not hidden).
- Dashboard is reviewed by the owner and she confirms she understands each page without additional explanation.
- Final report ties every recommendation back to a specific data finding — no recommendation should be generic advice that isn't backed by the shop's own numbers.

---

## 19. Edge Cases
- Missing or illegible records for certain months/years — decide and document how these are handled (excluded vs. estimated).
- Products discontinued or renamed mid-period (e.g., Varmora changes a tile line name) — may distort trend/ABC results if not reconciled.
- One-off bulk contractor orders that spike a single month's revenue — should be flagged separately so they don't get misread as a "trend."
- Products with very few transactions (can't reliably classify as fast/slow with only 2–3 sales in 5 years) — need a minimum-transaction threshold before classifying.

---

## 20. Risks
- **Data quality risk:** Real shop registers are rarely clean; underestimating cleaning time is the single biggest risk to the timeline.
- **Cost assumption risk:** EOQ/ROP calculations depend on ordering/holding cost estimates that aren't formally tracked by the business — results could be directionally right but not precisely accurate. State this limitation openly rather than presenting EOQ numbers as exact.
- **Owner engagement risk:** If the owner isn't available for interviews/data access at the right time, qualitative context (why sales dipped, competitor actions) will be missing.
- **Overclaiming risk:** Don't publish an "X% sales increase" claim unless it's actually been measured post-implementation — recommendations are projected impact, not verified results, until acted on and re-measured.

---

## 21. Milestones / Timeline
Based on your own Gantt chart in the proposal:
- Jan 2026 — Discussion with shop owner
- Feb 2026 — Data collection (sales & purchase records)
- Feb–Mar 2026 — Data cleaning & structuring
- Mar 2026 — Preliminary analysis & mid-term submission
- Apr 2026 — Detailed financial & inventory analysis
- May 2026 — Report drafting, review & final submission
- Jun 2026 — PPT preparation & viva prep

---

## 22. Open Questions
- Does the shop have cost data (purchase price) reliably recorded, or only selling price? This materially affects margin and EOQ accuracy.
- What lead time does the shop actually experience from supplier order to delivery (needed for ROP)? This is currently unknown and needs an owner interview.
- Will the owner actually use a Power BI file going forward, or would a simpler Excel dashboard get more real-world use? Worth asking her directly rather than assuming.
- Is "5–7% sales increase" something you're claiming as a projected estimate from your recommendations, or as an actual measured result? This needs to be resolved before it goes on a resume — projected and achieved are not interchangeable claims.

---

## 23. Appendix / References
- Source proposal: "Analytical Study of a Wholesale and Retail Marble, Tiles, and Sanitary Shop" — BDM Capstone Proposal, Tarun Chaudhary, Roll No. 24f3004421, IIT Madras.
- Business: Maa Vindhyawasini Marble, Paraspura, Ghazipur, UP. Owner: Mrs. Anju Saraf.
- Methods referenced: ABC Analysis, FSN Analysis, EOQ, ROP/Safety Stock — standard inventory management techniques.
