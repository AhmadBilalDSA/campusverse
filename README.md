<div align="center">


![CampusVerse](assets/hero.jpg)

![Records](https://img.shields.io/badge/records-293_522-1a2744)
![Full Text](https://img.shields.io/badge/full_text-43_522-2f855a)
![Passages](https://img.shields.io/badge/passages-1_094_881-744210)
![Internet](https://img.shields.io/badge/internet-not_required-c53030)

### The library that never needs the internet.

**CampusVerse is an offline academic discovery engine for Pakistani universities.**
Students and faculty search, read, and cite books and statutes over the campus network.
No internet connection. No cloud accounts. No per-seat licenses.

</div>

---

## What is CampusVerse?

CampusVerse is an offline-first digital library system built for universities in Pakistan. It runs entirely on a local campus server: a Next.js web application backed by a Meilisearch search index, serving content over the campus LAN.

> **293,522** catalog records · **1,094,881** full-text passages · **43,522** readable documents

| Capability | Detail |
|---|---|
| Full-text search | Across 293,522 catalog records |
| Instant reading | 43,522 full-text documents |
| Citations | APA, MLA, and Chicago export |
| Personal library | Shelves, reading history, bookmarks |
| Languages | English and Urdu (right-to-left) |

---

## The Problem

Campus internet in Pakistan is unreliable. Evening congestion, load shedding, and bandwidth caps cut students off from online libraries exactly when they need them most. Commercial academic databases charge per-seat fees in dollars, pricing out most public universities.

> CampusVerse removes the internet from the critical path. The entire collection lives on a server inside the campus building. If the campus network is up, the library is up.

---

## How It Works

Three components, one server:

```
  Students (phones, laptops)
         |
    Campus WiFi / LAN
         |
  ┌──────────────────────┐
  │    CAMPUS SERVER     │
  │                      │
  │  Next.js Web App     │  Port 3000 · Bilingual EN/UR
  │  Meilisearch         │  293,522 records · typo-tolerant
  │  Library Storage     │  43,522 original book files
  └──────────────────────┘
         |
    Internet: NOT REQUIRED
```

![CampusVerse Architecture](assets/architecture.svg)

Deployment is one machine on the campus LAN. A firewall rule opens port 3000 to the local network. Students connect over WiFi using a QR code or URL. Nothing leaves the building.

---

## The Collection

Real numbers, verified against the live search index.

| Source | Documents | Access |
|---|---|---|
| Project Gutenberg | 43,514 books | Full text |
| OpenStax | 5 textbooks | Full text |
| Pakistani statutes | 3 (Companies Act 2017, Partnership Act 1932, Contract Act 1872) | Full text |
| Catalog records | 250,000 | Citation index |

### Copyright Compliance

Pakistan Copyright Ordinance 1962, Section 18: literary works enter the public domain 50 years after the author's death. CampusVerse serves full text only for works verified public domain in Pakistan (author died in 1975 or earlier) or explicitly open-licensed (OpenStax textbooks, statutes). All other records are citation-only index entries.

---

## For Universities

<div align="center">

### Free 30-Day Pilot

We install on your server, load the collection, and train your library staff.

### After the Pilot: PKR 350,000 / campus / year

One flat fee. Unlimited students. Unlimited faculty. Unlimited searches.

**Contact: Ahmad Bilal** · [github.com/AhmadBilalDSA](https://github.com/AhmadBilalDSA) · kierninja@gmail.com

</div>

---

## Technical Overview

| Layer | Technology |
|---|---|
| Frontend | Next.js 15, React, TypeScript |
| Languages | Bilingual English/Urdu with RTL layout |
| Search | Meilisearch (faceted, typo-tolerant) |
| Reader | Paginated text + PDF, table of contents, original file download |
| Auth | Session-based login, rate-limited APIs |
| Assets | Zero CDN dependencies; everything self-hosted |
| Telemetry | Privacy-preserving; hour-bucketed counts only; no IPs, no user IDs |
| Stack | TypeScript, Python (ingestion), PowerShell (operations), SQLite |

<details>
<summary><b>System requirements</b></summary>

- One Windows or Linux machine on the campus LAN
- 8 GB RAM minimum (16 GB recommended for indexing)
- 50 GB free disk space for the search index and library
- Campus WiFi or wired LAN

</details>

---

<div align="center">

*Built by Ahmad Bilal · Independent research for Pakistani higher education*

</div>
