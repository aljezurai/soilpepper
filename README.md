# 🌲 Tuscan Permaculture — Static Site

A self-contained static site for the 1ha Tuscan permaculture design tools. Ready to serve via any web server.

## Quick Start (local testing)

```bash
cd /opt/data/www
python3 -m http.server 8080
```

Open `http://localhost:8080` in your browser. All internal links work.

## Serving via Nginx Proxy Manager (Umbrel)

### 1. Install Nginx Proxy Manager

From the Umbrel App Store → install **Nginx Proxy Manager**.

### 2. Serve the files

The files are at `/opt/data/www/` inside the Hermes container. NPM runs in its own container, so you have **two options**:

**Option A: Sync files to a volume NPM can read**

Use `docker cp` or set up a shared volume between containers. The cleanest approach:

```bash
# Copy the www directory to a location NPM can reach
docker cp hermes:/opt/data/www /path/on/host
```

Then configure NPM to serve that directory as a static site.

**Option B: Use the included Python HTTP server**

A lightweight server already runs on port 8888 inside the Hermes container. Configure NPM to reverse-proxy to:

```
http://hermes:8888
```

(Replace `hermes` with the actual container name or host IP.)

### 3. Configure NPM

1. Open the NPM admin interface (port 81 by default)
2. Add a **Proxy Host** or **Static Site**
3. Set domain/subdomain (e.g. `permaculture.umbrel.local` or a real domain)
4. Point to the server serving these files
5. Enable SSL via Let's Encrypt if using a public domain

### 4. (Optional) Public access via Cloudflare Tunnel

1. Install **Cloudflare Tunnel** from the Umbrel App Store
2. Configure it to route your domain to NPM
3. No port forwarding needed — Cloudflare handles external access

## File Structure

```
/opt/data/www/
├── index.html              ← Entry point (Juniper Ridge dashboard)
├── design-proposal.html    ← Aranya Step 6 master document
├── sector-analysis.html    ← 9-sector radial analysis
├── helicopter-view.html    ← Master overlay with toggles
├── orchard-placement.html  ← 24 species positioned
├── guild-diagrams.html     ← 13 tree guilds + 19 companions
├── veg-planner.html        ← 12-bed drag-and-drop garden planner
├── veg-design.html         ← Vegetable garden design view
├── zone-2b.html            ← 15 species × 7 layers
├── water-management.html   ← 4 sources, 4 swales
├── species-filter.html     ← 110 species filter tool
├── site-layout.html        ← Base map with zones
├── plants.json             ← Shared species database (110 species)
├── design-report.md        ← Full design report
├── species-catalogue.md    ← Italian cultivar database
└── suitability-assessment.md ← Plant suitability assessment
```

## Updating

The source of truth is the Obsidian vault at:
`/opt/data/obsidian-vault/Captures/`

When tools are updated there, re-run the export:

```bash
/opt/data/scripts/export-www.sh
```

This script will be created once the export process is finalized.