# UAP-Ledger
*A plug-and-play open-science platform for tamper-proof UFO / UAP research*

[![Use this template](https://img.shields.io/badge/Use_this_template-blue?logo=github)](https://github.com/spwotton/uap-ledger/generate)
[![Run on Replit](https://repl.it/badge/github/spwotton/uap-ledger)](https://replit.com/github/YOUR-USER/uap-ledger)
![CI](https://github.com/YOUR-USER/uap-ledger/actions/workflows/zk-proof-check.yml/badge.svg)

---

## What is it?
UAP-Ledger bundles everything you need to run an auditable research workflow for anomalous-phenomena data.

| Feature | Details |
|---------|---------|
| Transparent peer review | 75 % super-majority, published vote splits, minority memos, scheduled & fast-track reviews |
| Cryptographic integrity | SHA-256 hash per report, optional IPFS / Arweave anchoring |
| Automated operations   | Daily pg_dump→S3, Slack uptime pings, Dependabot & Trivy scans |
| Shadow ZK voting       | Noir + Barretenberg circuit proves “one reviewer, one vote” without revealing the vote |
| One-command stack      | `docker compose up -d` launches FastAPI, Postgres, Redis, Caddy (TLS), Prometheus, Grafana |

---

## Quick start

    # clone & boot locally
    git clone https://github.com/YOUR-USER/uap-ledger.git
    cd uap-ledger
    docker compose up -d          # API, DB, Grafana, etc.

    # browse
    http://localhost/docs         # Swagger UI
    http://localhost/grafana      # metrics (admin / changeme)

If you cannot run Docker, click **Code → Codespaces** or the **“Run on Replit”** badge above to open a ready-to-use cloud workspace.

---

## Repository overview

| Folder | Contents |
|--------|----------|
| `core/zk_vote/`        | Noir circuit `vote.nr` + CI proof for anonymous voting |
| `ledger-api/`          | FastAPI backend, JWT auth, Prometheus metrics, Caddy TLS |
| `handbook/`            | Governance rules and report templates (Markdown & LaTeX) |
| `tests/`               | `zk_voting_mock.py` – local proof demonstration |
| `.github/workflows/`   | CI pipelines (lint → tests → ZK proof → Docker push) |

---

## Road-map

| Phase | Goal | Status |
|-------|------|--------|
| 1 | Shadow ZK voting (this repository) | ✔ done |
| 2 | Merkle membership proof & on-chain nullifier anchoring | ⏳ |
| 3 | Telemetry ingest endpoint & SvelteKit front-end        | ⏳ |
| 4 | Incentive tokens & quadratic funding for replications  | ⏳ |

---

## License
Code: **MIT** • Documentation: **CC-BY 4.0**

> “Extraordinary claims demand extraordinary evidence.  
>  Let’s record that evidence—cryptographically and in the open.”
