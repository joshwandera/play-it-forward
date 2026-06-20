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

## Status

This is currently a front-end prototype. The cart, checkout, pledges and email signup are illustrative — a live version would need M-Pesa (Daraja) integration for payments and a backend to record orders and track funds raised.

## About

Built in Nairobi for East African table tennis. Awards at the Cup are supported by The Friends Behind the Cup; equipment for upcoming players comes from registration fees and, going forward, from merchandise and pledges.
