cat > README.md << 'EOF'
# Aspen Covers Tracker

Internal dashboard for tracking spa cover inventory and daily activity at Aspen Spas Service Department.

**Live URL**: https://aspenservices.github.io/Aspen-Cover-Tracker/

## What it does

- Tracks the lifecycle of every spa cover: pending → arrived at warehouse → scheduled → out for delivery → delivered → installed
- Generates the **Daily Cover Activity Report** email sent to the whole team
- Syncs with Firebase Realtime Database in real-time across devices
- Integrates with TECH-TICKETS for automatic Service Log ticket creation
- Reads & merges from the Inventory_A_B_Covers_Saunas.xlsx spreadsheet
- Tracks 45+ day-old covers as critical alerts
- Shares customer database with the Invoice Tracker

## Tech stack

- Single-file HTML + vanilla JavaScript (no build step, no frameworks)
- Firebase Realtime Database (invoice-daily-f170e, shared with Invoice Tracker)
- SheetJS (xlsx) for Excel import/export
- GitHub Pages for hosting
- PWA-installable

## Integrations

| System | Path / URL | Purpose |
|---|---|---|
| Firebase RTDB | coversTracker/covers | Source of truth for cover state |
| Firebase RTDB | invoiceTracker/customers | Shared customer DB for autocomplete |
| TECH-TICKETS | aspenservices.github.io/TECH-TICKETS/ | Service Log for techs |
| Invoice Tracker | aspenservices.github.io/invoice-tracker/ | Sibling app for invoices |

## Daily report recipients

- TO: service1@aspenspas.com
- CC: manu, peyton, dan, lana, seth, neil, service, tom, sam @aspenspas.com

## Workflow

1. Cover ordered (in shipment list)
2. Cover arrives at warehouse → Mark arrived → Sent to TECH-TICKETS Service Log (pending)
3. Alberto coordinates with customer in TECH-TICKETS → schedules date + assigns tech
4. Tech delivers → Mark delivered → Install ticket

## Maintained by

Service Department · Aspen Spas · St. Louis, MO
EOF
