# EVEAIO — EVE Online All-In-One Desktop App

**Version 0.37**

A multi-account desktop companion for EVE Online. Log in with EVE SSO, sync your characters, and access manufacturing analysis, market tools, structure management, skill planning, and more — all from one window.

---

## Table of Contents

- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [First-time Setup](#first-time-setup)
- [Running from Source](#running-from-source)
- [Building the Executable](#building-the-executable)
- [Data & Configuration](#data--configuration)
- [Crash Reporting](#crash-reporting)

---

## Features

### Dashboard
Overview of your accounts at a glance:
- Current wallet balances, daily profit/loss summary
- Fuel alerts for structures running low
- Upcoming moon extraction timers
- Recent regional trader flips

---

### Manufacturing

#### Industry (Manufacturing)
- Manufacturing and invention profit calculator using SDE data
- Jita contract prices for blueprint originals and copies
- Job ledger — view active and completed industry jobs across all characters
- Material efficiency and time efficiency factors applied per-job

#### BP Research / Copy
- Track Blueprint Original research (ME/TE levels) and copy jobs
- Show contract BPC/BPO prices from Jita public contracts
- Calculate build costs vs buy costs for items

#### Reactions
- Reaction chain profit calculator
- Input material costs vs output sell prices
- Copy-to-multibuy for buying mats in bulk

#### PI Mining
- Planetary Interaction production chain calculator
- Colony overview synced from ESI (`Sync All`)
- System PI planner — compare output value across systems
- Extractor setup viewer

---

### Market

#### Station Trading
- Find profitable buy/sell spreads within a single station
- Filter by min profit, min margin %, min daily volume
- Supports all major trade hubs and custom structures
- Uses character's ESI broker fee and sales tax skills

#### Regional Trading
- Find items with a price gap between source and destination hubs
- Full Source / Destination hub selector — choose any combination of hubs independently
- **Waypoints** — enable to detect trade hubs lying on the stargate route between source and destination; highlights items you could pick up cheaper en route (saves a trip)
- Filters: min profit, min margin %, min volume, max capital, freight/m³ cost, blacklist, whitelist, favourites
- Profit calculated net of broker fees, sales tax, and hauling costs
- Uses character's trained broker/tax skills via ESI

#### Contract Flipping
- Scan public item_exchange and auction contracts in any region
- Values items at current Jita sell prices
- Shows profit margin — no ESI auth required for basic use

#### Market Seeding
- Plan what to buy at a trade hub and haul to a target station (nullsec, lowsec, etc.)
- ISK/m³ ranking; toggle buy-order vs sell-order pricing
- Freight cost factored in automatically

#### Market Snipes
- Find sell orders listed well below normal market price (fat-finger listings)
- Configurable threshold (% below estimated value)
- Quick link to in-game market for fast purchase

#### Market LP Profit
- Fetches all toons' LP balances and their associated NPC corporation LP stores via ESI
- Calculates net ISK/LP for each offer against live Jita prices
- Factors in manufacturing: if an offer gives a BPC, build profit is calculated using the toon's skills
- Sortable by ISK/LP, profit per item, or required input cost

---

### Skills

#### Skill Farming
- Neural remap planner with queue optimisation
- SP extraction schedule — when to extract, how many Large Skill Injectors you get
- SP thresholds and warning alerts
- Current PLEX price fetched live for extraction profitability

#### Skills
- Full skill queue per character with days-remaining countdown
- Large Skill Injector cost-to-finish calculator
- **Skill Plans** tab — curated plans per activity (Industry, Trade, PvP, etc.) with comparison against each character's trained skills; shows what's missing

---

### Structure Manager *(requires Station Manager, Fuel Technician, Starbase Fuel Technician, or Director role on at least one linked character)*

#### Moons
- All owned moons fetched from ESI with system, constellation, region
- Ore composition breakdown per moon
- Live Jita price fetch for each ore type with total estimated value

#### Extractions
- Moon extraction timers for all characters with access
- Chunk arrival times, belt expiry, days remaining
- Sortable by extraction time

#### Structure Manager (Fuel)
- Fuel status for all structures across all corp characters
- Days of fuel remaining, sorted by urgency (critical → ok)
- Highlights structures running low before they go offline

---

### More / Tools

#### Reprocessing
- Reprocessing yield calculator with skills applied
- Ore and mineral tables with Jita buy prices
- Mineral sourcing — which ore gives the best yield for a target mineral

#### Jump Planner
- Find valid cyno destination systems within jump range of a capital ship
- Cyno chain planner — multi-hop route from origin to destination for capitals
- Uses Fuzzwork universe data; filters by security status

#### Route Checker
- Stargate route from any system to any destination
- Per-hop danger rating: combines ESI system kills and Intel chat log data
- Reads live from EVE client chat logs; highlights recently reported hostile systems
- zKillboard integration for recent kills per system

#### Intel Report
- Parse content from EVE chat logs or manual paste
- Extracts: timestamp, channel, reporter, system, pilot name, ship type
- Supports multiple intel channels simultaneously
- Configurable EVE logs directory

#### Fittings
- Ship fitting browser and explorer
- Left-column browser: ship → fitting
- CPU/PG usage progress bars per fitting
- Per-module stats and slot assignment (high/mid/low/rig)
- Zone tint colours by ship class
- Skill plan comparison for a fit

#### Freight Planner
- Paste an item list, get total m³ and minimum trip count for freighters/jump freighters
- ESI lookup for ship cargo capacity and character's Hull Upgrades skill
- Supports multiple ship types for comparison

#### Courier Calculator
- Hauling contract helper — paste items and pick a route
- Outputs: collateral estimate, recommended reward, volume breakdown

#### Profit Tracker
- Log income by category: mining, selling, reactions, PI, industry, other
- ISK over time graph with configurable date range
- ISK goal system with progress bars
- Per-category breakdown

#### PLEXing
- Plan how much ISK you need to PLEX your accounts
- Supports multiple subscription periods (monthly, quarterly, bi-annually, annually, 2-year)
- Live PLEX sell/buy price fetched from Jita market data
- Shows total PLEX needed and ISK cost across all toons

#### Market Data
- Simple read-only market browser per hub or region
- Sort by best sell price, sell volume, or buy volume
- Uses cached type data; fetch runs in background

#### Notifications
- Central alert feed — all warnings, fuel alerts, extraction reminders, and info messages
- Category icons and timestamps
- Mark-as-read per item or bulk

---

### Settings

- **Account Manager** — Add and manage multiple EVE accounts via SSO; assign primary character; view/revoke ESI tokens
- **Sync** — `Sync All` button to refresh ESI data (skills, wallet, assets, jobs, PI, mining, notifications) across all characters; per-category manual refresh
- **SDE** — Download and update the EVE Static Data Export (item types, blueprints, materials, groups, categories)
- **Universe Map** — Download Fuzzwork stargate data used by Jump Planner and Route Checker
- **Hubs & Locations** — Add custom trade hubs (player structures or non-standard stations) with station ID and region ID
- **Blacklist / Whitelist** — Per-item lists for Station and Regional trading filters
- **Theme & Appearance** — Dark/light theme, font size, accent colour
- **Overlay** — Configurable hotkey (Ctrl/Alt/Shift + F9–F12) to toggle the app window when tabbing in/out of EVE
- **Logs & Diagnostics** — View log file and crash report paths, open logs folder, opt-in auto crash reporting (see below)
- **Background Refresh** — Auto-sync interval and startup behaviour

---

## First-time Setup

1. **Launch the app** — The Settings page opens automatically on first run.
2. **Add an EVE account** — Click *Add account*, complete the EVE SSO login in your browser, and grant the requested ESI scopes.
3. **Sync All** — Click the *Sync All* button in Settings to pull skills, wallet, assets, industry jobs, PI, and mining data for all characters.
4. **Download SDE** — In Settings → SDE, click *Download SDE* to fetch blueprint and item data. Required for manufacturing and market features.
5. **Download Universe Map** — In Settings → Universe Map, click *Download* to enable Jump Planner and Route Checker.

---

## Data & Configuration

All persistent data lives in the `data/` directory:

| File / Folder | Contents |
|---|---|
| `data/config.json` | All user settings and config keys |
| `data/evemanager.log` | Rolling application log (5 MB × 5 backups) |
| `data/crash_reports/` | Crash report text files (`crash_YYYYMMDD_HHMMSS.txt`) |
| `data/sde/` | Downloaded SDE YAML files |
| `data/universe/` | Fuzzwork universe stargate data |
| `data/public_contracts/` | Cached public contract data per region |
| `data/type_icons/` | Cached item type icons |
| `data/dotlan_svg/` | Cached Dotlan region SVG maps |

All ESI tokens, OAuth credentials, and config keys are stored only in this local `data/` folder — nothing is sent to any external server except EVE's own ESI API and (optionally, with your consent) the crash reporter described below.

---

## Crash Reporting

EVEAIO includes an **opt-in** automatic crash reporter.

### What it does

When enabled, if the app crashes the crash report file is automatically sent to the developer's private Discord forum channel. Each user gets their own dedicated thread (titled with your main toon's name) so reports stay organised and follow-up messages go to the same thread.

### What is sent

- The exception traceback (the error text)
- App version and OS/Python version
- Context label (which hook caught it)

### What is **never** sent

- Wallet balances or ISK figures
- ESI access tokens or API keys
- Item prices, trade history, or any personal data

### How to enable

Settings → Logs & Diagnostics → ☑ **Auto-send crash reports to developer**

You can also click **Send latest crash report** at any time to manually send the most recent file, useful if you spotted a bug but the app didn't crash outright.

### Thread persistence

Your Discord thread ID is stored locally in `data/config.json`. If you reinstall fresh and lose the config, a new thread will be created in the forum — this is expected and harmless.
