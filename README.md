# Late Delivery Analysis — Supply Chain Performance

🚧 **In progress.** Page 1 (Delivery Performance) is built. Root cause analysis and a what-if recommendation page are in development.

**Question:** Which parts of the fulfilment network drive late deliveries, and what would fixing them change?

---

## Context
Late deliveries cost more than a delayed parcel. They trigger SLA penalties, expediting costs and customer churn, and in a large network they are rarely spread evenly: a few shipping modes, regions or product lines usually account for a disproportionate share. This project looks for where those concentrations are, drawing on day-to-day experience monitoring fulfilment KPIs and SLA performance in logistics operations.

## Approach
- **Data:** DataCo Smart Supply Chain dataset (public, Kaggle): order-item level records covering orders, shipping, customers and products. See [`/data`](data/README.md).
- **Cleaning (Power Query):** removed customer personal data and unused columns, parsed order and shipping dates with the correct (US) locale, set numeric types, and added a **DelayDays** column (actual shipping days − scheduled shipping days).
- **Key measures so far:** On-Time Rate, Late Orders, Avg Delay (late orders only), Total Orders (Shipped), On-Time Rate change vs prior period.

## Report Pages

| Page | Status | Question it answers |
|---|---|---|
| Delivery Performance | ✅ Built | Are we hitting SLA, and is it getting better or worse? |
| Root Cause | 🚧 In progress | Which shipping modes, regions, markets and categories have the highest late rates? |
| Recommendation | 🚧 In progress | What happens to on-time performance if the worst segment improves? |

**Delivery Performance** shows headline KPIs (on-time rate and its change vs the prior period, late orders, average delay on late orders, total shipped orders), late orders by market, region and shipping mode, a late-order trend over time, and an order-level detail table by category, product and shipping mode.

## Coming Next
- Late rate (not just late order count) broken down by shipping mode, region, market and category, to isolate which segments are disproportionately late rather than just high-volume
- A what-if page: modelling the on-time rate impact of improving the worst-performing segment
- Verifying order counts use distinct orders rather than order-item rows, since this dataset has one row per line item
- Full findings and a recommendation, once the above is in place

## Tools
Power BI Desktop (Power Query, DAX)

---
**Author:** Oluchukwu Ejiofor · [Email](mailto:Oluchukwu.b.ejiofor@gmail.com)
