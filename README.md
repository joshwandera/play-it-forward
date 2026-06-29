# Play It Forward

A minimalist e-commerce site for **Play It Forward**, a community initiative of the **Wandera & Friends Cup** — a table tennis tournament that brought together players from Kenya, Uganda, Tanzania and Zanzibar in March 2026.

The site sells Cup merchandise, with proceeds going toward equipment for upcoming table tennis players across East Africa. The goal is to make the initiative ongoing and sustainable between tournaments.

## What's here

This is a single-page static website — no build step, no framework, no backend. Everything lives in one file:

- `index.html` — the entire site (HTML, CSS and JavaScript in one file)
- `images/` — product and event photos (added as they're shot)

## Viewing it locally

No server or installation needed. Just open the file:

1. Download or clone this repo
2. Double-click `index.html` — it opens in your browser

To edit, open `index.html` in a code editor (e.g. VS Code) and refresh the browser after saving.

## How it's built

The site has these sections: a hero with an animated rally, a product shop, the Play It Forward "chain" explainer, an impact section showing where the money goes, monthly "fund a player" pledge tiers, and a trust/contact area.

A few things worth knowing for anyone editing it:

- **Colours** are defined once at the top of the `<style>` block as CSS variables (`--ink`, `--paper`, `--clay`, `--net`). Change a colour there and it updates everywhere.
- **Products** live in a JavaScript array (`products`) near the bottom of the file. Each product's name, price, cause contribution (`give`), and image are set there. The shop is generated from this array.
- **Product images** use a fallback: if a photo file exists in `images/`, it shows; if not, a built-in SVG drawing is shown instead. This means photos can be added one at a time without breaking anything.
- **The impact dashboard** (the "Where your money goes" section) is driven entirely by one `impact` object in the script. It shows an all-time raised total, the current outcome-based goal with a progress bar, headline stats, an allocation ledger, and an archive of completed goals.

## Important: how the money figures work

Every amount shown as "raised" is **net profit to the cause, not gross sales**. For each confirmed, paid order the figure is:

```
gross received  −  cost of goods  −  transaction/delivery  =  net to the cause
```

Example: a tee sold for KSh 1,500 that cost KSh 1,000 to make and brand contributes KSh 500 — only that 500 is counted. The per-product `give` field is this same net margin. Counting full sale prices would overstate the total and make the initiative unsustainable, so it's deliberately avoided.

Goals are **sequential and outcome-framed**. When a goal hits its target it isn't reset or deleted — it's marked complete, moves into the "Goals completed" archive with what it funded, and a new goal opens. The all-time total only ever increases, across every goal. Past goals are kept as a record, not discarded.

## Status

This is currently a front-end prototype. The cart, checkout, pledges and email signup are illustrative.

The impact dashboard runs on placeholder figures held in the `impact` object so the layout can be seen. Going live requires a backend that:

- integrates M-Pesa (Daraja, STK Push) to take payments,
- records each confirmed, paid order along with its costs, and stores the **net** contribution,
- exposes the running totals, current goal, and completed-goals archive for the page to fetch.

When that exists, the single `impact` object in the script is replaced by a fetch returning the same shape — no layout changes needed. The code comment above that object documents the exact structure and rules.

## About

Built in Nairobi for East African table tennis. Awards at the Cup are supported by The Friends Behind the Cup; equipment for upcoming players comes from registration fees and, going forward, from merchandise and pledges.
