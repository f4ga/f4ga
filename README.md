<!-- 🌌 1. HERO (фоновая волна + печатающийся текст поверх) -->
<div align="center" style="position: relative; min-height: 280px;">
  <!-- фоновая волна (без текста) -->
  <div style="position: absolute; top: 0; left: 0; width: 100%; z-index: 0;">
    <img src="https://capsule-render.vercel.app/api?type=waving&height=280&color=gradient&customColorList=12,18,24,27,30&text=%20&fontSize=50&fontAlignY=35&desc=&animation=fadeIn" width="100%" />
  </div>
  <!-- печатающийся текст поверх (с отступом, чтобы не сливался с волной) -->
  <div style="position: relative; z-index: 0; padding-top: 80px;">
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

## 🛸 Stack

| Area | Tech |
|------|------|
| **Go** | net/http, gRPC, unsafe, mmap, sync, pprof, testing, benchmarks |
| **Python** | FastAPI, Celery, aiogram, Pytest |
| **Storage** | PostgreSQL (tsvector, pgvector), Redis, SQLite, my own LSM engine |
| **Infra** | Docker, Docker Compose, GitHub Actions, Nginx, Bash |
| **Observability** | Prometheus, Flower, custom /health, /ready, /metrics |

## ⚡ Main project

### 🪨 ScoriaDB — embedded transactional KV store in Go

[github.com/f4ga/ScoriaDB](https://github.com/f4ga/ScoriaDB)

I built an LSM-based database from scratch. No forks, no wrappers.

**Storage engine**
- MemTable (B‑tree) + SSTable with block index, Bloom filter, range filter (min/max key)
- Leveled compaction
- WAL with CRC32, crash recovery
- Value Log (WiscKey + mmap): values >64 bytes → separate file, zero‑copy reads
- MANIFEST: SSTable metadata log with fsync, consistent recovery
- Write Stall Controller: 3‑level backpressure (Soft / Hard / MemTable stall), Prometheus metrics
- VFS abstraction for disk failure testing

**MVCC & transactions**
- Inverted timestamps → Snapshot Isolation
- WriteBatch (atomic batch)
- Interactive transactions: `startTS`, local buffer, conflict check on commit → `ErrConflict`

**Column Families**
- Isolated LSM instances per family
- Atomic writes across families via WriteBatch

**Network & interfaces**
- Embedded API (`pkg/scoria`)
- gRPC (unary + server‑streaming Scan)
- REST gateway
- WebSocket for live key updates
- CLI (Cobra): get/set/del/scan/txn + interactive REPL
- Web UI (React + TypeScript + Tailwind) embedded via `embed.FS`

**DevOps & quality**
- Docker Compose — one command to run everything
- GitHub Actions: lint, test, license‑check
- Prometheus `/metrics`, health checks `/health` and `/ready`
- Unit tests, integration tests, benchmarks
- Apache 2.0 license, headers in every file, CI enforcement

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
