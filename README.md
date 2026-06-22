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

🟣 **ScoriaDB** — LSM‑based key‑value store in pure Go.  
MVCC, ACID transactions, Column Families, Zero‑copy Value Log, WAL with Group Commit.  
Reads at **7.1M ops/s** (140 ns), writes at **1.51M ops/s** with Group Commit (662 ns).  
4KB value reads at **1.25M ops/s** — zero‑copy from mmap, 5 allocs/op (was 8).  
WAL sync writes at **2.29M ops/s** (436 ns), Group Commit at **12.4M ops/s** (80.8 ns).  
Crash recovery in <1 second (Pebble: 9s, BadgerDB: 12s).  

🔵 **ZeroRaft** — Raft consensus on raw syscalls.  
No `net` package. `socket()`, `bind()`, `listen()`, `epoll`, non‑blocking I/O, single‑threaded event loop.  
Three‑node cluster in Docker, leader election in 150–300 ms, PCAP export for Wireshark, `/chaos` endpoint for packet loss injection.  
*This taught me: epoll, the Linux networking stack, and how distributed consensus actually works under the hood.*

🟢 **Scorix** — log analyzer built on top of ScoriaDB.  
Filters millions of log lines by time, level, JSON fields. Live tail, percentiles, gRPC server mode.  
Single binary, no dependencies.  
*This taught me: building practical tools on top of my own storage engine, and that dogfooding catches bugs fast.*

📝 **Articles:**  
- [How I added Group Commit to my LSM database in Go](https://habr.com/p/1043820/)  
- [How I wrote an LSM engine with MVCC and Value Log in pure Go](https://habr.com/p/1032208/)  
- [How I made VLog zero‑copy and got +487% faster reads](https://habr.com/p/—link—) *(coming soon)*

---

## 🛠️ Tech stack

### Languages
- **Go** – daily driver (concurrency, syscalls, profiling, benchmarks)
- **Python** – FastAPI, aiogram, Celery, RAG pipelines

### Storage & infrastructure
- **LSM engines** – MemTable, SSTable, Leveled compaction, WAL, Value Log, MVCC, Zero‑copy VLog
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
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=f4ga&theme=radical&hide_border=true&background=0d1117&stroke=FF007F&ring=FF007F&fire=FF007F&currStreakLabel=FF007F" alt="streak stats" />
  <br/>
  <img width="100%" src="https://github-readme-activity-graph.vercel.app/graph?username=f4ga&theme=tokyo-night&hide_border=true&area=true&color=4cbded&line=4cbded&point=ffffff" />
</div>

## 📫 Where to find me

- **Telegram:** [@ebssy](https://t.me/ebssy)
- **Habr:** [norzy](https://habr.com/ru/users/norzy/)
- **Email:** e04579138@gmail.com

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
