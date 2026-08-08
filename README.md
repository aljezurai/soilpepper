# 🌶️ SOILPEPPER — Permaculture Design Toolkit

Free, browser-based permaculture design tools. Plan a site from blank plot to garden beds — **no account, no server, your data never leaves your device.**

👉 **Live site: https://soilpepper.com/** (also: https://aljezurai.github.io/soilpepper/)

## What it is

A suite of self-contained HTML tools (no build step, no backend) built on **Aranya's step-by-step permaculture design method**:

| Tool | Purpose |
|---|---|
| 🗺️ **Master Plan Grid** | Divide any plot into a 10×10m cell grid; assign functions (guild / vegetable garden / water / road / construction), paint zones |
| 📄 **Design Proposal** | Aranya Step 6 master document — generated live from your brief, water and plan data |
| 🧭 **Sector Analysis** | 9-sector radial analysis (wind, sun, water, wildlife, fire, noise, viewsheds, access, frost) |
| 🗺️ **Helicopter View** | Master overlay with layer toggles rendered from your plan |
| 💧 **Water Management** | Catchment, pond/tank sizing, gravity pressure, grid-snapped swale placement, what-if sliders |
| 🔗 **Guild Matrix** | Companion relationships + mutual-benefit scores across 256 species |
| 🌿 **Guild Diagrams** | 13 tree guilds with companion rings — printable for the field |
| 🔍 **Species Filter** | 256 species × 11 filter dimensions |
| 🥕 **Veg Planner** | Real-world garden model: 75cm beds in 10m cells, modules, join toggles, sowing specs (pattern/spacing/depth/thinning), per-slot capacity, offline field-view export |
| 🌳 **Orchard Placement** | Zone-based tree placement with frost/wind/sun/water scoring |

## Privacy

Everything runs client-side. Site plans, water calculations and garden layouts live in **your browser's localStorage** — nothing is uploaded anywhere. Use the **Export Field View / Export** buttons to produce standalone HTML/JSON you can carry to the garden, phone or printer.

## Region presets

- 🇮🇹 **Tuscany** — Mediterranean (Zone 8b–9a, silty-sand, ~800mm rain)
- 🇳🇱 **Netherlands** — Temperate maritime (Zone 7b–8a)

Switch with `?region=tuscany|netherlands` on any tool.

## Development

The suite is maintained as a private repo (design vault) and exported to this public repo. Tools are single-file HTML + `plants.json` (the species truth database). No build step — open in any browser, works offline via `file://`.

Built with the Aranya method — [*Permaculture Design: A Step-by-Step Guide*](https://www.permaculture.co.uk/books/permaculture-design-step-step-guide).

