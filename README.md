
<!-- 🌌 1. HERO — волна + печатающийся текст внутри -->
<div align="center" style="position: relative; width: 100%; min-height: 280px; overflow: hidden;">
  <!-- Волна (фон) -->
  <div style="position: absolute; top: 0; left: 0; width: 100%; z-index: 0;">
    <img src="https://capsule-render.vercel.app/api?type=waving&height=80&color=gradient&customColorList=12,18,24,27,30&text=%20&fontSize=50&fontAlignY=35&desc=&animation=fadeIn" width="100%" style="display: block;" />
  </div>
  <!-- Печатающийся текст поверх волны -->
  <div style="position: relative; z-index: 1; display: flex; justify-content: center; align-items: center; height: 280px;">
    <a href="https://git.io/typing-svg">
      <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=32&duration=4000&pause=1000&color=FF007F&center=true&vCenter=true&width=800&height=100&lines=%24+whoami+%3E+f4ga;Backend+%7C+Systems+Programming;Go+%7C+Python+%7C+LSM+%7C+MVCC" alt="Typing SVG" />
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

## 👩‍💻 About me (facts)

- Backend developer — Go daily, Python when it fits
- Write systems from scratch: storage engines, microservices, CLI tools
- Read production database sources (BadgerDB, BoltDB, PebbleDB) to learn real-world design
- Always finish projects: fully functional, tested, documented
- Write unit tests, integration tests, benchmarks. CI must stay green.
- Use Linux, Docker, Prometheus, GitHub Actions every day

---

<!-- 🛰️ 5. TECH STACK — голубые бейджи, языки без SQL -->
## 🛰️ Tech Stack

### Languages

![Go](https://img.shields.io/badge/Go-1A1A1A?style=flat-square&logo=go&logoColor=40a0ff)
![Python](https://img.shields.io/badge/Python-1A1A1A?style=flat-square&logo=python&logoColor=40a0ff)

### Storage & Infrastructure

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-1A1A1A?style=flat-square&logo=postgresql&logoColor=40a0ff)
![Redis](https://img.shields.io/badge/Redis-1A1A1A?style=flat-square&logo=redis&logoColor=40a0ff)
![SQLite](https://img.shields.io/badge/SQLite-1A1A1A?style=flat-square&logo=sqlite&logoColor=40a0ff)
![Docker](https://img.shields.io/badge/Docker-1A1A1A?style=flat-square&logo=docker&logoColor=40a0ff)
![Linux](https://img.shields.io/badge/Linux-1A1A1A?style=flat-square&logo=linux&logoColor=40a0ff)
![GitHub%20Actions](https://img.shields.io/badge/GitHub_Actions-1A1A1A?style=flat-square&logo=github-actions&logoColor=40a0ff)

### Observability & Tools

![Prometheus](https://img.shields.io/badge/Prometheus-1A1A1A?style=flat-square&logo=prometheus&logoColor=40a0ff)
![Flower](https://img.shields.io/badge/Flower-1A1A1A?style=flat-square&logo=celery&logoColor=40a0ff)
![WebSocket](https://img.shields.io/badge/WebSocket-1A1A1A?style=flat-square&logo=websocket&logoColor=40a0ff)

### Areas of Interest

![Storage Systems](https://img.shields.io/badge/Storage_Systems-0A1A2F?style=flat-square&logoColor=white)
![LSM & MVCC](https://img.shields.io/badge/LSM_&_MVCC-0A1A2F?style=flat-square&logoColor=white)
![Backend](https://img.shields.io/badge/Backend-0A1A2F?style=flat-square&logoColor=white)
![Systems Programming](https://img.shields.io/badge/Systems-0A1A2F?style=flat-square&logoColor=white)

---

<!-- 📊 6. GITHUB STATS — телеметрия -->
## 📊 GitHub Stats

<div align="center">
  <img src="https://github-readme-streak-stats.vercel.app/?user=f4ga&theme=radical&hide_border=true&background=0d1117&stroke=FF007F&ring=FF007F&fire=FF007F&currStreakLabel=FF007F" alt="streak stats" />
  <img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=f4ga&layout=compact&langs_count=8&theme=radical&hide_border=true&bg_color=0d1117&title_color=FF007F&text_color=c9d1d9" />
  <br />
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=f4ga&theme=radical&hide_border=true&background=0d1117&stroke=FF007F&ring=FF007F&fire=FF007F&currStreakLabel=FF007F" alt="streak stats" />
  <!-- Activity graph в голубых тонах -->
  <img width="100%" src="https://github-readme-activity-graph.vercel.app/graph?username=f4ga&theme=tokyo-night&hide_border=true&area=true&color=40a0ff&line=40a0ff&point=ffffff" />
</div>

---

## ⚡ Main project

### 🪨 ScoriaDB — embeddable transactional KV store in Go

[github.com/f4ga/ScoriaDB](https://github.com/f4ga/ScoriaDB)

LSM-based database built from scratch. No forks, no wrappers.  
**Embeddable** (pure Go, single `import`) or **standalone server** with gRPC, REST, CLI and Web UI.

**Highlights**
- **~150 ns reads**, **~1 070 ns writes** — MemTable hits ~6.6M ops/s
- **MVCC with Snapshot Isolation** — readers never block writers
- **ACID transactions** — interactive `Begin/Commit/Rollback`, atomic WriteBatch, conflict detection
- **WiscKey Value Log** — values >64B in separate file, mmap zero‑copy reads
- **Column Families** — independent LSM trees, atomic cross‑CF writes
- **WAL + MANIFEST + fsync** — full crash recovery, no acknowledged writes lost
- **Docker Compose** — one command to launch server, CLI and integration tests
- **CI/CD** — GitHub Actions: lint, race detector, license headers

**What's already live**

| Layer | Status |
|---|---|
| Storage engine (LSM, WAL, SSTable, Bloom, compaction, Snappy/Zstd) | ✅ |
| Embedded Go API (`DB`, `CFDB`) | ✅ |
| gRPC API (CRUD, streaming Scan, transactions) | ✅ |
| REST + WebSocket (live key updates) | ✅ |
| CLI (`scoria`): get/set/del/scan/txn + interactive REPL + admin | ✅ |
| JWT auth (bcrypt, roles: admin/readwrite/readonly) | ✅ |
| Web UI (React + TypeScript + Tailwind, `embed.FS`) | 🚧 v0.1.1 |
| Value Log GC, TTL, secondary indexes, sorted sets, JSON | ⏳ v1.0.0 |

**Benchmarks** (Intel i3-1215U, Go 1.23+, Linux amd64)

| Operation | Value size | Time | Throughput |
|---|---|---|---|
| `Get` (MemTable hit) | < 64 B | **~150 ns** | ~6 600 000 ops/s |
| `Put` (small) | < 64 B | **~1 070 ns** | ~935 000 ops/s |
| `Put` (large, Value Log) | 4 KB | **~4 785 ns** | ~209 000 ops/s |
| Public API overhead | — | < 5% | — |

**Quick start**
```bash
git clone https://github.com/f4ga/scoriadb.git && cd scoriadb
docker compose -f deployments/docker-compose.yml up --build
# Server: gRPC :50051, HTTP :8080
```

Project is in **v0.1.0 release cycle** — all core components implemented and tested.  
For evaluation use `main`; for production wait for v1.0.0 or pin a release tag.

---

## 📁 Other projects

**CaseKeeper** — Telegram bot for team case management.  
Go, PostgreSQL (tsvector), Redis, FSM. Roles, audit, Russian full‑text search, export.

**AVDI-shell** — Distributed infrastructure diagnostics.  
Go, gRPC, WebSocket, PostgreSQL, Redis. Agent‑server, real‑time metrics, live logs.

**Hybrid RAG** — Hybrid search (semantic + lexical) over documents.  
Python, FastAPI, pgvector, ruBERT, E5. Chunking, BM25.

**SSH Arena** — Multiplayer real‑time RTS in terminal over SSH.  
Go, SSH, SQLite, ANSI graphics. 20ms game loop, auto‑save.

**Review Bot** — Async Telegram bot that generates reviews via GigaChat.  
Python, aiogram, Celery, Redis, Flower.

**Expense Tracker** — Personal finance web app.  
Python, FastAPI, PostgreSQL, JWT, rate limiting, Pytest.

**Quizzbattle** — Backend for AI‑generated quizzes.  
Python, FastAPI, 500+ RPS, fallback/retry.

---

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

<!-- 👁️ VISITOR COUNTER -->
<div align="center">
  <a href="https://visitor-badge.laobi.icu/badge?page_id=f4ga.f4ga">
    <img src="https://visitor-badge.laobi.icu/badge?page_id=f4ga.f4ga&left_color=black&right_color=FF007F&left_text=Profile%20Views" />
  </a>
</div>
