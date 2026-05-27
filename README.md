<!-- 🌌 1. HERO — волна + печатающийся текст внутри -->
<div align="center" style="position: relative; width: 100%; min-height: 280px; overflow: hidden;">
  <div style="position: absolute; top: 0; left: 0; width: 100%; z-index: 0;">
    <img src="https://capsule-render.vercel.app/api?type=waving&height=80&color=gradient&customColorList=12,18,24,27,30&text=%20&fontSize=50&fontAlignY=35&desc=&animation=fadeIn" width="100%" style="display: block;" />
  </div>
  <div style="position: relative; z-index: 1; display: flex; justify-content: center; align-items: center; height: 280px;">
    <a href="https://git.io/typing-svg">
      <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=32&duration=4000&pause=1000&color=FF007F&center=true&vCenter=true&width=800&height=100&lines=%24+whoami+%3E+f4ga;Backend+%7C+Systems+Programming;Go+%7C+Python+%7C+LSM+%7C+Raft" alt="Typing SVG" />
    </a>
  </div>
</div>

<!-- 🎯 2. CONTACT -->
<div align="center">
  <a href="https://github.com/f4ga?tab=repositories"><img src="https://img.shields.io/badge/📁_Repos-12100E?style=for-the-badge&logo=github&logoColor=white" /></a>
  <a href="https://habr.com/ru/users/norzy/"><img src="https://img.shields.io/badge/Habr-5F9DBA?style=for-the-badge&labelColor=5F9DBA&color=5F9DBA" /></a>
  <a href="https://t.me/ebssy"><img src="https://img.shields.io/badge/💬_Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white" /></a>
  <a href="mailto:e04579138@gmail.com"><img src="https://img.shields.io/badge/📧_Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" /></a>
  <a href="https://github.com/f4ga"><img src="https://img.shields.io/badge/⭐_Follow-FF007F?style=for-the-badge&logo=github&logoColor=white" /></a>
</div>

---

## 👩‍💻 About me

I build systems from scratch — storage engines, consensus protocols, CLI tools.  
I don't wrap existing solutions; I read production code (BadgerDB, PebbleDB, BoltDB) and then write my own.

**What I've built and what I learned:**

- **ScoriaDB** – an LSM‑based key‑value store in pure Go. MVCC, ACID transactions, Column Families, WAL with Group Commit. Reads at **6.6M ops/s** (150 ns), writes at **1.43M ops/s** with full fsync. Crash recovery in milliseconds (Pebble: 9s, BadgerDB: 12s).  
  *This taught me: durability is not optional, fsync is expensive but you can amortize it, and Go can be as fast as C++ when you stop adding layers.*

- **ZeroRaft** – Raft consensus on raw syscalls. No `net` package. `socket()`, `bind()`, `listen()`, `epoll`, non‑blocking I/O, single‑threaded event loop. Three‑node cluster in Docker, PCAP export for Wireshark, `/chaos` endpoint for packet loss injection.  
  *This taught me: epoll, the Linux networking stack, and how distributed consensus actually works under the hood.*

- **Scorix** – a log analyzer built on top of ScoriaDB. Filters millions of log lines by time, level, JSON fields. Live tail, percentiles, gRPC server mode. Single binary, no dependencies.  
  *This taught me: building practical tools on top of my own storage engine, and that dogfooding catches bugs fast.*

- **10+ other projects** – backends, Telegram bots, CLI utilities. All have READMEs, tests, and benchmarks. Not just "prototypes" – finished, documented, ready to use.

**What I'm looking for:**

A paid internship or a Junior/Junior+ position (35 hours/week, remote). I dive deep quickly, write maintainable code, test it, document it, and explain complex things simply. No cgo, no black boxes.

---

## 🛠️ Tech stack

### Languages
- **Go** – daily driver (concurrency, syscalls, profiling, benchmarks)
- **Python** – FastAPI, aiogram, Celery, RAG pipelines

### Storage & infrastructure
- **LSM engines** – MemTable, SSTable, Leveled compaction, WAL, Value Log, MVCC
- **Raft** – from scratch on syscalls
- **PostgreSQL** – pgvector, tsvector, complex queries, migrations
- **Redis** – caching, pub/sub, task queues
- **Docker / Compose** – multi‑container setups
- **Linux** – epoll, sockets, filesystems, signals

### APIs & protocols
- **gRPC** – Protobuf, streaming, interceptors
- **REST** – Gin, FastAPI
- **WebSocket** – real‑time notifications
- **CLI** – Cobra, interactive shells

### Engineering culture
- **Unit tests + integration + stress** – 100% coverage for critical paths
- **Benchmarks** – CI fails on >5% regression
- **Race detector** – mandatory for all concurrent code
- **Profiling** – pprof, flamegraphs
- **Documentation** – every project has README + examples (Python, Java, C++)

---

## 📊 GitHub Stats

<div align="center">
  <img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=f4ga&layout=compact&langs_count=8&theme=radical&hide_border=true&bg_color=0d1117&title_color=FF007F&text_color=c9d1d9" />
  <br />
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=f4ga&theme=radical&hide_border=true&background=0d1117&stroke=FF007F&ring=FF007F&fire=FF007F&currStreakLabel=FF007F" alt="streak stats" />
  <img width="100%" src="https://github-readme-activity-graph.vercel.app/graph?username=f4ga&theme=tokyo-night&hide_border=true&area=true&color=4cbded&line=4cbded&point=ffffff" />
</div>

---

## 📁 Projects

<div style="border: 1px solid #4cbded; border-radius: 12px; padding: 12px; margin: 16px 0; background-color: #0d1117;">
<strong>🪨 ScoriaDB</strong><br/>
Embedded LSM key‑value store in pure Go.<br/>
MVCC, ACID transactions, Column Families, WAL with Group Commit, gRPC + REST + CLI.<br/>
<br/>
<strong>Numbers (sync mode, full fsync):</strong><br/>
• Read: <strong>6.6M ops/s</strong> (150 ns) – faster than any networked DB<br/>
• Write (16B): <strong>888k ops/s</strong> → Group Commit: <strong>1.43M ops/s</strong> (+60%)<br/>
• Write (4KB): <strong>215k ops/s</strong> (840 MB/s) → Group Commit: <strong>867 MB/s</strong> (NVMe limit)<br/>
• WAL with Group Commit: <strong>10.5M ops/s</strong> (94.9 ns/op) – 4.8× faster than sync<br/>
• Crash recovery: <strong>milliseconds</strong> (Pebble: 9s, BadgerDB: 12s)<br/>
• BadgerDB on same hardware: <strong>142 MB/s</strong> → ScoriaDB is 6× faster<br/>
<br/>
<strong>Stack:</strong> Go, LSM, MVCC, WAL, Value Log (WiscKey), gRPC, REST, CLI, Docker, GitHub Actions<br/>
<strong>Links:</strong> <a href="https://github.com/f4ga/ScoriaDB">GitHub</a> · <a href="https://scoriadb.github.io">Docs</a> · <a href="https://habr.com/ru/articles/1032208/">Habr article</a>
</div>

<div style="border: 1px solid #4cbded; border-radius: 12px; padding: 12px; margin: 16px 0; background-color: #0d1117;">
<strong>🔁 ZeroRaft</strong><br/>
Raft consensus implementation from scratch – no `net` package, only raw syscalls.<br/>
Non‑blocking epoll server, single‑threaded event loop. Leader election, log replication, cluster of 3 nodes in Docker.<br/>
PCAP export for Wireshark, `/chaos` endpoint for packet loss simulation.<br/>
<br/>
<strong>Stack:</strong> Go, syscalls (`socket`, `bind`, `listen`, `epoll`), Docker<br/>
<strong>Link:</strong> <a href="https://github.com/f4ga/ZeroRaft">GitHub</a>
</div>

<div style="border: 1px solid #4cbded; border-radius: 12px; padding: 12px; margin: 16px 0; background-color: #0d1117;">
<strong>📊 Scorix</strong><br/>
Log analyzer built on ScoriaDB. Filters millions of log lines by time, level, JSON fields. Live tail, percentiles, gRPC server mode.<br/>
Single binary, no external dependencies.<br/>
<br/>
<strong>Stack:</strong> Go, ScoriaDB, gRPC<br/>
<strong>Link:</strong> <a href="https://github.com/f4ga/Scorix">GitHub</a>
</div>

<div style="border: 1px solid #4cbded; border-radius: 12px; padding: 12px; margin: 16px 0; background-color: #0d1117;">
<strong>📦 CaseKeeper</strong><br/>
Telegram bot for team case management.<br/>
Go, PostgreSQL (tsvector), Redis, FSM, roles, audit, CSV export.
</div>

<div style="border: 1px solid #4cbded; border-radius: 12px; padding: 12px; margin: 16px 0; background-color: #0d1117;">
<strong>🖥️ AVDI‑shell</strong><br/>
Distributed infrastructure diagnostics.<br/>
Agent‑server over gRPC + WebSocket, task orchestration, real‑time metrics, live logs.
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

<div style="border: 1px solid #4cbded; border-radius: 12px; padding: 12px; margin: 16px 0; background-color: #0d1117;">
<strong>💰 Expense Tracker</strong><br/>
Personal finance web app.<br/>
Python, FastAPI, PostgreSQL, JWT, rate limiting, Pytest >85%.
</div>

<div style="border: 1px solid #4cbded; border-radius: 12px; padding: 12px; margin: 16px 0; background-color: #0d1117;">
<strong>❓ Quizzbattle</strong><br/>
Backend for AI‑generated quizzes.<br/>
Python, FastAPI, 500+ RPS, fallback/retry, WebSocket real‑time.
</div>

---

## 📫 Where to find me

- **Telegram:** [@ebssy](https://t.me/ebssy)
- **Email:** [e04579138@gmail.com](mailto:e04579138@gmail.com)
- **GitHub:** [github.com/f4ga](https://github.com/f4ga)
- **Habr:** [norzy](https://habr.com/ru/users/norzy/)

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
