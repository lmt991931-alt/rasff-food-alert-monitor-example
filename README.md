# RASFF Food & Feed Safety Alert Monitor — example

Sample input/output for the **[RASFF Food & Feed Safety Alert Monitor](https://apify.com/yuancore/rasff-food-alert-monitor)** Apify actor, which turns the EU's public **RASFF** (Rapid Alert System for Food and Feed) notifications — recalls, border rejections, contamination alerts — into clean, structured, schedulable data, with a **change-monitoring** mode.

## Why
The official RASFF Window UI lets you browse notifications one page at a time, but has **no bulk export and no change feed**. The actor reads the **public, no-auth** RASFF API (`webgate.ec.europa.eu/rasff-window/backend/public/...`), normalizes each notification, and — uniquely — with `monitorSince` returns only alerts validated on/after a date (a daily food-safety alert feed). Export to JSON / CSV / Excel.

- 🔗 **Actor:** https://apify.com/yuancore/rasff-food-alert-monitor
- 📄 [`sample_input.json`](./sample_input.json) — the change-monitoring mode
- 📄 [`sample_output.json`](./sample_output.json) — real notifications pulled from the public API

## Fields (per notification)
`ecValidationDate`, `reference`, `subject`, `productCategory`, `productType`, `riskDecision`, `notificationClassification`, `notifyingCountry`, `originCountries`, `notifId`.

## Use cases
Food importers / retailers / QA monitoring recalls and border rejections for their product categories and sourcing countries; supply-chain due diligence; food-safety market intelligence.

## Caveats
Public EU transparency data, reused under **CC BY 4.0** (attribute *European Commission – RASFF*). Notification-level (product / hazard / country) — not personal data. **Not affiliated with the European Commission.** The public API is undocumented and can change without notice — the actor ships a schema-drift guard for exactly that.
