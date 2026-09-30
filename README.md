<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:1a1a2e,100:0d1117&height=120&section=header&text=f4ga&fontSize=48&fontColor=ffffff&fontAlignY=38&desc=Backend%20%C2%B7%20Go%20%C2%B7%20Storage%20Engines%20%C2%B7%20Distributed%20Systems&descAlignY=58&descSize=14&descColor=8b949e" width="100%" />

<br/>

[![GitHub](https://img.shields.io/badge/github-f4ga-181717?style=flat-square&logo=github)](https://github.com/f4ga)
[![Telegram](https://img.shields.io/badge/telegram-@ebssy-2CA5E0?style=flat-square&logo=telegram&logoColor=white)](https://t.me/ebssy)
[![Habr](https://img.shields.io/badge/habr-norzy-5F9DBA?style=flat-square)](https://habr.com/ru/users/norzy/)
[![Email](https://img.shields.io/badge/email-e04579138@gmail.com-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:e04579138@gmail.com)

</div>

---

Пишу бэкенд на Go. Изучаю хранилища — LSM-деревья, WAL, MVCC, Raft. Предпочитаю предсказуемость: не «в среднем быстро», а «быстро всегда».

---

### [ScoriaDB](https://github.com/f4ga/ScoriaDB)
*Встраиваемое LSM key-value хранилище на чистом Go*

MVCC, ACID-транзакции, колоночные семейства, zero-copy value log, WAL с group commit. 480+ тестов, включая crash-recovery и `-race`.

- 40.6 млн чтений/с на ноутбуке за $400 — без аллокаций в куче, GC не мешает
- Запись с fsync на каждую транзакцию — 375K ops/s, ~187× быстрее RocksDB в строгом режиме
- SSD живёт ~5× дольше за счёт низкого write amplification
- Работает на ARM64

---

### [TephraKV](https://github.com/f4ga/TephraKV)
*Дизайн распределённого KV-хранилища*

Архитектурный документ, по которому уже можно писать код. Цель — не средняя задержка, а предсказуемость в худшем случае (p999).

- Arena на mmap — данные вне кучи, GC не трогает горячий путь
- Lock-free skiplist и epoch-based reclamation
- WAL как Raft-лог — один журнал вместо двух
- Multi-Raft на Dragonboat вместо внешнего etcd
- KV separation по WiscKey — ключи в LSM, значения отдельно

Каждое решение — ADR с честным указанием цены. Статус: v0.1 в разработке.

---

### [ZeroRaft](https://github.com/f4ga/ZeroRaft)
*Raft на голых системных вызовах*

Без пакета `net`: только `socket()`, `bind()`, `epoll`, неблокирующий I/O и однопоточный event loop. Три узла в Docker, выборы лидера за 150–300 мс, экспорт PCAP для Wireshark, `/chaos` для имитации потерь пакетов.

---

### [Scorix](https://github.com/f4ga/Scorix)
*Анализатор логов поверх ScoriaDB*

Фильтрация миллионов строк по времени, уровню и JSON-полям. Live tail, перцентили, gRPC-сервер. Один бинарник, без зависимостей времени выполнения.

---

<div align="center">

**Стек**

</div>

| | |
|---|---|
| <img src="https://cdn.simpleicons.org/go/00ADD8" width="16" /> **Языки** | Go (основной) · Python (FastAPI, aiogram, Celery, RAG, Hugging Face) |
| <img src="https://cdn.simpleicons.org/postgresql/4169E1" width="16" /> **Хранилища** | Внутренности LSM: MemTable, SSTable, leveled compaction, WAL, MVCC, value log |
| <img src="https://cdn.simpleicons.org/etcd/419EDA" width="16" /> **Распределённые системы** | Raft с нуля · Multi-Raft |
| <img src="https://cdn.simpleicons.org/docker/2496ED" width="16" /> **Инфраструктура** | PostgreSQL (pgvector, tsvector) · Redis · Docker/Compose · Linux |
| <img src="https://cdn.simpleicons.org/grpc/244c5a" width="16" /> **API** | gRPC · REST · WebSocket · CLI на Cobra |
| <img src="https://cdn.simpleicons.org/linux/FCC624" width="16" /> **Практика** | Unit, integration, crash-тесты · benchmark CI · `-race` · pprof |

В планах — микроконтроллеры на C.

---

<div align="center">

**GitHub Stats**

<img src="https://github-readme-streak-stats.herokuapp.com/?user=f4ga&theme=radical&hide_border=true&background=0d1117&stroke=FF007F&ring=FF007F&fire=FF007F&currStreakLabel=FF007F" alt="streak stats" />
<br/>
<img width="100%" src="https://github-readme-activity-graph.vercel.app/graph?username=f4ga&theme=tokyo-night&hide_border=true&area=true&color=4cbded&line=4cbded&point=ffffff" />

</div>

---

<div align="center">
<sub>GitHub <a href="https://github.com/f4ga">f4ga</a> · Telegram <a href="https://t.me/ebssy">@ebssy</a> · Habr <a href="https://habr.com/ru/users/norzy/">norzy</a> · <a href="mailto:e04579138@gmail.com">e04579138@gmail.com</a></sub>
</div>
