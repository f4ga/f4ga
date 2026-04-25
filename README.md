<!-- 🌌 1. HERO -->
<div align="center">
  <a href="https://git.io/typing-svg">
    <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=32&duration=4000&pause=1000&color=FF007F&center=true&vCenter=true&width=800&height=100&lines=%24+whoami+%3E+f4ga;Backend+%7C+Systems+Programming;Go+%7C+Python+%7C+LSM+%7C+MVCC;Embedded+KV+database+from+scratch" alt="Typing SVG" />
  </a>
  <img src="https://capsule-render.vercel.app/api?type=waving&height=180&color=gradient&customColorList=12,18,24,27,30&text=%20&fontSize=50&fontAlignY=35&desc=&animation=fadeIn" width="100%" />
</div>

<!-- 🎯 2. CONTACT -->
<div align="center">
  <a href="https://github.com/f4ga?tab=repositories"><img src="https://img.shields.io/badge/📁_Repos-12100E?style=for-the-badge&logo=github&logoColor=white" /></a>
  <a href="https://t.me/ebssy"><img src="https://img.shields.io/badge/💬_Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white" /></a>
  <a href="mailto:e04579138@gmail.com"><img src="https://img.shields.io/badge/📧_Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" /></a>
  <a href="https://github.com/f4ga"><img src="https://img.shields.io/badge/⭐_Follow-FF007F?style=for-the-badge&logo=github&logoColor=white" /></a>
</div>

<!-- 🧠 3. ABOUT -->
<h3 align="center">
  <img src="https://media.giphy.com/media/hvRJCLFzcasrR4ia7z/giphy.gif" width="25px"> 
  LSM · MVCC · ACID · gRPC
</h3>
<p align="center">
  <i>«Build your own database. It teaches you more than a hundred CRUD apps.»</i>
</p>

<!-- 🛸 4. STACK -->
<h3 align="center">🛸 Core stack</h3>
<div align="center">
  <img src="https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white" />
  <img src="https://img.shields.io/badge/gRPC-2CA5E0?style=for-the-badge&logo=google&logoColor=white" />
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white" />
  <img src="https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white" />
  <img src="https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white" />
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" />
  <img src="https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white" />
  <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white" />
</div>

<br />

<!-- 🚀 5. MAIN PROJECT (SCORIADB - MVP) -->
<h2 align="center">⚡ Key project</h2>

<div align="center">
  <h3>🪨 ScoriaDB — embedded transactional KV store in Go</h3>
  <p><b>LSM · MVCC · ACID · gRPC · Web UI</b></p>
  <a href="https://github.com/f4ga/ScoriaDB"><img src="https://img.shields.io/badge/📦_github.com/f4ga/ScoriaDB-FF007F?style=for-the-badge&logo=github" /></a>
</div>

<br />

**What I built from scratch (MVP, fully working):**

| Component | Implementation |
|-----------|----------------|
| **LSM Engine** | MemTable (B‑tree), SSTable with Bloom + range filter, Leveled compaction |
| **Value Log** | WiscKey + mmap → zero‑copy reads for large values (>64 bytes) |
| **WAL + MANIFEST** | Write‑ahead log (CRC32) + manifest with fsync, crash recovery |
| **MVCC** | Snapshot isolation, inverted timestamps, tombstone support |
| **Transactions** | WriteBatch (atomic) + interactive optimistic transactions, explicit `ErrConflict` |
| **Write Stall Controller** | 3‑level backpressure (Soft / Hard / MemTable stall), Prometheus metrics |
| **Column Families** | Isolated LSM instances + atomic cross‑CF writes |
| **gRPC API** | Unary + server‑streaming Scan, reflection |
| **REST + WebSocket** | HTTP gateway, live key updates |
| **CLI** | Cobra‑based: get/set/del/scan/txn + interactive REPL |
| **Web UI** | React + TypeScript + Tailwind (embedded via `embed.FS`) |
| **Observability** | `/metrics` (Prometheus), `/health`, `/ready` |
| **DevOps** | Docker Compose, GitHub Actions (lint, test, license‑check) |
| **Licensing** | Apache 2.0 (full text + headers + CI check) |

🔗 **Full code + design docs:** [github.com/f4ga/ScoriaDB](https://github.com/f4ga/ScoriaDB)

---

<!-- 📁 6. OTHER PROJECTS -->
<h2 align="center">📁 Other projects</h2>

<table align="center">
  <tr><td width="500">
    <b>🤖 CaseKeeper</b><br />
    Telegram bot: team case management, Russian full‑text search (tsvector), roles, audit.<br />
    <i>Go · PostgreSQL · Redis · FSM</i><br />
    <a href="https://github.com/f4ga/CaseKeeper"><img src="https://img.shields.io/badge/repo-FF007F?style=flat-square&logo=github" /></a>
   </tr>
  <tr><td width="500">
    <b>🖥️ AVDI‑shell</b><br />
    Distributed infrastructure diagnostic: agent + central server, real‑time logs via WebSocket.<br />
    <i>Go · gRPC · PostgreSQL · Redis</i><br />
    <a href="https://github.com/42x-SAU/AVDI-shell"><img src="https://img.shields.io/badge/repo-FF007F?style=flat-square&logo=github" /></a>
   </tr>
  <tr><td width="500">
    <b>🔍 Hybrid RAG</b><br />
    Hybrid search (semantic + lexical) with ruBERT, E5, pgvector.<br />
    <i>Python · FastAPI · PostgreSQL · Transformers</i><br />
    <a href="https://github.com/f4ga/Hybrid-rag-service"><img src="https://img.shields.io/badge/repo-FF007F?style=flat-square&logo=github" /></a>
   </tr>
  <tr><td width="500">
    <b>🎮 SSH Arena</b><br />
    Multiplayer real‑time RTS over SSH, ANSI graphics, 20ms game loop.<br />
    <i>Go · SSH · SQLite</i><br />
    <a href="https://github.com/f4ga/SSH-rts-online-game"><img src="https://img.shields.io/badge/repo-FF007F?style=flat-square&logo=github" /></a>
   </tr>
</table>

<!-- 🧬 7. HIDDEN MATRIX (optional) -->
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

<!-- 👁️ 8. VISITOR COUNTER -->
<div align="center">
  <a href="https://visitor-badge.laobi.icu/badge?page_id=f4ga.f4ga">
    <img src="https://visitor-badge.laobi.icu/badge?page_id=f4ga.f4ga&left_color=black&right_color=FF007F&left_text=Profile%20Views" />
  </a>
</div>
