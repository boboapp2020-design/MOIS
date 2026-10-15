# M.O.I.S — Monitoring Operational Intelligence System

Mitr Lao Sugar · FAF1. This repository hosts the dashboard page for GitHub Pages: https://boboapp2020-design.github.io/MOIS/

| File | What it is |
|---|---|
| `index.html` | the whole dashboard (single file, built from the project's `prototype/src` by `build.py`) |
| `demo.json` | a snapshot recorded from the simulator (last season's real data, replayed), used when no server is connected |

## Three ways the page gets its data
1. **Demo (default on GitHub Pages)** — reads `demo.json`; times move to "now"; a badge bottom-left says *โหมดเดโม*. Saving, stop causes and the AI assistant are disabled.
2. **Connected to the plant's collector** — open once with `?api=https://<collector-address>&token=<API_TOKEN>`; the browser remembers it (badge: *เชื่อมต่อ …*). `?api=off` forgets it.
3. **Served by the collector itself** — open the collector's address directly; same page, live data.

The collector (Python, runs inside the company network, reads PI every minute, the daily reports, the cane report and manual entries,
holds the AI key) is not in this repository. Deployment steps and the parity check (`tools/parity_check.py` — compares a server's
answers with the simulator's for every request the pages make) are in the project's `docs/deploy.md`.
