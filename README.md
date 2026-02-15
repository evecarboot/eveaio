# EVEManager

**TL;DR** — All-in-one desktop app for EVE Online: industry & blueprints, reactions, moon management, extractions, market prices, fuel monitoring, reprocessing, profit tracking, PI calculator, skill farming, and skill plans. Log in with EVE SSO to sync structures, extractions, skills, and mining ledger; everything else works offline with local data and optional price APIs.

- **Dashboard** — Upcoming extractions, fuel alerts, quick stats.
- **Industry & Blueprints** — Manufacturing/invention profits, SDE data, contract scanning, research/copy views.
- **Reactions** — Reaction profits, materials, copy-to-multibuy.
- **Moons** — Systems/moons from ESI, ore compositions, Jita price fetch.
- **Extractions** — Moon extraction timers (ESI).
- **Market** — Compressed ore Jita prices (Fuzzwork).
- **Fuel** — Structure fuel status, sorted by urgency.
- **Reprocessing** — Yield calculator, ore/mineral tables, mineral sourcing.
- **Profit & Goals** — Log income, track ISK, set goals with progress bars.
- **PI Calculator** — Production chains, colonies, system planner.
- **Skill Farm** — Remap + queue planner, extraction schedule.
- **Skill Plans** — Curated plans per activity, compare to ESI skills.

Data lives in a **data/** folder next to the app (or exe), created automatically on first run. SQLite for user data; cache files for SDE and prices so the app stays fast.
