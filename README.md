
<!-- 🌌 1. HERO — волна + печатающийся текст внутри -->
<div align="center" style="position: relative; width: 100%; min-height: 280px; overflow: hidden;">
  <!-- Волна (фон) -->
  <div style="position: absolute; top: 0; left: 0; width: 100%; z-index: 0;">
    <img src="https://capsule-render.vercel.app/api?type=waving&height=80&color=gradient&customColorList=12,18,24,27,30&text=%20&fontSize=50&fontAlignY=35&desc=&animation=fadeIn" width="100%" style="display: block;" />
  </div>
  <!-- Печатающийся текст поверх волны -->
  <div style="position: relative; z-index: 1; display: flex; justify-content: center; align-items: center; height: 280px;">
    <a href="https://git.io/typing-svg">
      <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=32&duration=4000&pause=1000&color=FF007F&center=true&vCenter=true&width=800&height=100&lines=%24+whoami+%3E+f4ga;Backend+%7C+Systems+Programming;Go+%7C+Python" alt="Typing SVG" />
    </a>
  </div>
</div>

<!-- 🎯 2. CONTACT -->
<div align="center">
  <a href="https://github.com/f4ga?tab=repositories"><img src="https://img.shields.io/badge/📁_Repos-12100E?style=for-the-badge&logo=github&logoColor=white" /></a>
  <a href="https://t.me/ebssy"><img src="https://img.shields.io/badge/💬_Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white" /></a>
  <a href="mailto:e04579138@gmail.com"><img src="https://img.shields.io/badge/📧_Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" /></a>
  <a href="https://github.com/f4ga"><img src="https://img.shields.io/badge/⭐_Follow-FF007F?style=for-the-badge&logo=github&logoColor=white" /></a>
</div>

---

## 👩‍💻 A bit about me 

- I’m a developer who loves to build things from scratch – even when it hurts.
- Go is my daily tool; Python helps when the task doesn't need raw speed.
- Storage engines, CLI tools, microservices – if it touches the system, I'm interested.
- I read production code (BadgerDB, BoltDB, PebbleDB) to understand real trade‑offs.
- I finish what I start: working, tested, documented.
- Unit tests, integration tests, benchmarks – CI must stay green.
- Linux, Docker, Prometheus, GitHub Actions are my everyday environment.

---

## 🪨 My main project: ScoriaDB

**An embeddable LSM‑based key‑value store written in pure Go**  
(and yes, it's way more complex than I expected)

[github.com/f4ga/ScoriaDB](https://github.com/f4ga/ScoriaDB)

I built ScoriaDB to really understand how LSM engines, MVCC, and transactions work.  
It can be used as a library (`import`) or as a standalone server (gRPC, REST, CLI).

**What already works (and is tested):**

- LSM engine with MemTable (B‑tree), SSTable, Leveled compaction, Bloom filter, block compression (Snappy/Zstd)
- MVCC with Snapshot Isolation – readers never block writers
- ACID transactions: interactive `Begin/Commit/Rollback`, atomic WriteBatch, conflict detection
- WiscKey‑style Value Log – large values (>64 bytes) offloaded to a separate file, mmap reads (with copying for safety, true zero‑copy planned)
- Column Families – independent LSM trees, shared WAL for atomic cross‑CF writes
- WAL + Manifest with `fsync` – crash recovery works; after `kill -9` no acknowledged writes are lost
- Embedded Go API, gRPC (streaming Scan, transactions), REST, WebSocket notifications
- CLI (`scoria`) with `get/set/del/scan/txn`, interactive REPL, and admin commands (users, roles, password)
- JWT authentication (bcrypt, roles: `admin`, `readwrite`, `readonly`)
- Docker Compose – one command to run server + CLI integration tests
- CI/CD: GitHub Actions (lint, race detector, license checks)

**What's still rough (or coming soon):**

- Web UI (React) – not ready yet (v0.1.1)
- Manual GC only – automatic incremental GC is planned (v0.3.0)
- B‑tree with a global mutex – lock‑free skip list will come in v0.3.0
- No true zero‑copy yet – current implementation copies from mmap to avoid SIGSEGV
- Group Commit, TTL, binary Manifest – v0.2.0
- Distributed mode (Raft, sharding) – far future, maybe v1.0.0

**Why I built it** – to learn, to have something real in my portfolio, and because I wanted to know if I could. Turns out, I can. It's not production‑ready, but it's honest work.

**Quick start**
```bash
git clone https://github.com/f4ga/scoriadb.git && cd scoriadb
docker compose -f deployments/docker-compose.yml up --build
```

The project is in **v0.1.0** – core components are implemented and pass stress tests.  
Use it for pet projects or learning; for production, wait for v1.0.0 or pin a release tag.

---

<!-- 🛰️ 5. TECH STACK — голубые бейджи, языки без SQL -->
## 🛰️ Tech Stack

### Languages

![Go](https://img.shields.io/badge/Go-1A1A1A?style=flat-square&logo=go&logoColor=40a0ff)
![Python](https://img.shields.io/badge/Python-1A1A1A?style=flat-square&logo=python&logoColor=40a0ff)

### Storage & Infrastructure

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-1A1A1A?style=flat-square&logo=postgresql&logoColor=40a0ff)
![Redis](https://img.shields.io/badge/Redis-1A1A1A?style=flat-square&logo=redis&logoColor=40a0ff)
![Prometheus](https://img.shields.io/badge/Prometheus-1A1A1A?style=flat-square&logo=prometheus&logoColor=40a0ff)
![Docker](https://img.shields.io/badge/Docker-1A1A1A?style=flat-square&logo=docker&logoColor=40a0ff)
![Linux](https://img.shields.io/badge/Linux-1A1A1A?style=flat-square&logo=linux&logoColor=40a0ff)
![GitHub%20Actions](https://img.shields.io/badge/GitHub_Actions-1A1A1A?style=flat-square&logo=github-actions&logoColor=40a0ff)

### Areas of Interest

![Backend](https://img.shields.io/badge/Backend-0A1A2F?style=flat-square&logoColor=white)
![Systems Programming](https://img.shields.io/badge/Systems-0A1A2F?style=flat-square&logoColor=white)

---

<!-- 📊 6. GITHUB STATS — телеметрия -->
## 📊 GitHub Stats

<div align="center">
  <img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=f4ga&layout=compact&langs_count=8&theme=radical&hide_border=true&bg_color=0d1117&title_color=FF007F&text_color=c9d1d9" />
  <br />
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=f4ga&theme=radical&hide_border=true&background=0d1117&stroke=FF007F&ring=FF007F&fire=FF007F&currStreakLabel=FF007F" alt="streak stats" />
  <!-- Activity graph в голубых тонах -->
  <img width="100%" src="https://github-readme-activity-graph.vercel.app/graph?username=f4ga&theme=tokyo-night&hide_border=true&area=true&color=40a0ff&line=40a0ff&point=ffffff" />
</div>

## 📁 Other projects

<div style="border: 1px solid #4cbded; border-radius: 12px; padding: 12px; margin: 16px 0; background-color: #0d1117;">
<strong>📦 CaseKeeper</strong><br/>
Telegram bot for team case management.<br/>
Go, PostgreSQL (tsvector), Redis, FSM.<br/>
Roles, audit, Russian full‑text search, CSV export.
</div>

<div style="border: 1px solid #4cbded; border-radius: 12px; padding: 12px; margin: 16px 0; background-color: #0d1117;">
<strong>🖥️ AVDI‑shell</strong><br/>
Distributed infrastructure diagnostics.<br/>
Agent‑server over gRPC + WebSocket, task orchestration, real‑time metrics, live logs.<br/>
PostgreSQL, Redis, CLI client.
</div>

<div style="border: 1px solid #4cbded; border-radius: 12px; padding: 12px; margin: 16px 0; background-color: #0d1117;">
<strong>📄 Hybrid RAG</strong><br/>
Hybrid search (semantic + lexical).<br/>
Python, FastAPI, pgvector, ruBERT, E5, BM25, chunking, reranking.
</div>

<div style="border: 1px solid #4cbded; border-radius: 12px; padding: 12px; margin: 16px 0; background-color: #0d1117;">
<strong>🎮 SSH Arena</strong><br/>
Multiplayer real‑time strategy over SSH.<br/>
Go, SSH server, SQLite, ANSI graphics, 20ms game loop.
</div>


<div style="border: 1px solid #40a0ff; border-radius: 12px; padding: 12px; margin: 16px 0; background-color: #0d1117;">
<strong>💰 Expense Tracker</strong><br/>
Personal finance web app.<br/>
Python, FastAPI, PostgreSQL, JWT, rate limiting, Pytest >85%.
</div>

<div style="border: 1px solid #4cbded; border-radius: 12px; padding: 12px; margin: 16px 0; background-color: #0d1117;">
<strong>❓ Quizzbattle</strong><br/>
Backend for AI‑generated quizzes.<br/>
Python, FastAPI, 500+ RPS, fallback/retry, WebSocket real‑time.
</div>

## 📫 Where to find me

- Telegram: [@ebssy](https://t.me/ebssy)
- Email: e04579138@gmail.com
- GitHub: [github.com/f4ga](https://github.com/f4ga)

---

<!-- 🧬 ASCII-ART (спойлер) -->
<details>
  <summary><b>🕹️ $> DISPLAY MATRIX</b></summary>
  <br />
  <div align="center">
    <pre style="font-family: monospace; color: #c9d1d9; background: none; border: none; display: inline-block; text-align: left;">
░▒▓█▓▒░      ░▒▓█▓▒░░▒▓█▓▒░░▒▓███████▓▒░▒▓████████▓▒░       ░▒▓██████▓▒░░▒▓███████▓▒░ ░▒▓██████▓▒░░▒▓█▓▒░░▒▓█▓▒░             ░▒▓███████▓▒░▒▓████████▓▒░▒▓█▓▒░░▒▓█▓▒░░▒▓█▓▒░ 
░▒▓█▓▒░      ░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░      ░▒▓█▓▒░             ░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░             ░▒▓█▓▒░░▒▓█▓▒░ ░▒▓█▓▒░   ░▒▓█▓▒░░▒▓█▓▒░░▒▓█▓▒░ 
░▒▓█▓▒░      ░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░      ░▒▓█▓▒░             ░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░      ░▒▓█▓▒░░▒▓█▓▒░             ░▒▓█▓▒░░▒▓█▓▒░ ░▒▓█▓▒░   ░▒▓█▓▒░░▒▓█▓▒░░▒▓█▓▒░ 
░▒▓█▓▒░      ░▒▓█▓▒░░▒▓█▓▒░░▒▓██████▓▒░░▒▓██████▓▒░        ░▒▓████████▓▒░▒▓███████▓▒░░▒▓█▓▒░      ░▒▓████████▓▒░             ░▒▓███████▓▒░  ░▒▓█▓▒░   ░▒▓█▓▒░░▒▓█▓▒░░▒▓█▓▒░ 
░▒▓█▓▒░      ░▒▓█▓▒░░▒▓█▓▒░      ░▒▓█▓▒░▒▓█▓▒░             ░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░      ░▒▓█▓▒░░▒▓█▓▒░▒▓██▓▒░      ░▒▓█▓▒░░▒▓█▓▒░ ░▒▓█▓▒░   ░▒▓█▓▒░░▒▓█▓▒░░▒▓█▓▒░ 
░▒▓█▓▒░      ░▒▓█▓▒░░▒▓█▓▒░      ░▒▓█▓▒░▒▓█▓▒░             ░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░▒▓██▓▒░      ░▒▓█▓▒░░▒▓█▓▒░ ░▒▓█▓▒░   ░▒▓█▓▒░░▒▓█▓▒░░▒▓█▓▒░ 
░▒▓█▓▒░       ░▒▓██████▓▒░░▒▓███████▓▒░░▒▓████████▓▒░      ░▒▓█▓▒░░▒▓█▓▒░▒▓█▓▒░░▒▓█▓▒░░▒▓██████▓▒░░▒▓█▓▒░░▒▓█▓▒░░▒▓█▓▒░      ░▒▓███████▓▒░  ░▒▓█▓▒░    ░▒▓█████████████▓▒░  
    </pre>
  </div>
</details>

<br />
