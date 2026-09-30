<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:1a1a2e,100:0d1117&height=140&section=header&text=f4ga&fontSize=52&fontColor=ffffff&fontAlignY=45" width="100%" />

### Бэкенд-разработчик · Go · Хранилища данных · Распределённые системы

[![Telegram](https://img.shields.io/badge/telegram-@ebssy-2CA5E0?style=flat-square&logo=telegram&logoColor=white)](https://t.me/ebssy)
[![Habr](https://img.shields.io/badge/habr-norzy-5F9DBA?style=flat-square)](https://habr.com/ru/users/norzy/)
[![Email](https://img.shields.io/badge/email-написать-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:e04579138@gmail.com)

</div>

---

Пишу бэкенд на Go. Изучаю хранилища — LSM-деревья, WAL, MVCC, Raft. Предпочитаю предсказуемость: не «в среднем быстро», а «быстро всегда».

---

### [ScoriaDB](https://github.com/f4ga/ScoriaDB)
*Встраиваемое LSM key-value хранилище на чистом Go*

MVCC, ACID-транзакции, колоночные семейства, zero-copy value log, WAL с group commit.

**Тесты.** Около 500 тестов, включая crash-recovery и прогоны под `-race`. Покрыты горячий путь чтения и записи, восстановление после падения, конкурентный доступ.

**Производительность.**
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

**Навыки**

</div>

| | |
|---|---|
| <img src="https://cdn.simpleicons.org/go/00ADD8" width="16" /> **Языки** | Go — основной, включая конкурентность, syscalls, профилирование и бенчмарки. Python — FastAPI, aiogram, Celery, RAG, Hugging Face |
| <img src="https://cdn.simpleicons.org/postgresql/4169E1" width="16" /> **Хранилища** | Проектирование и реализация LSM-движков: MemTable, SSTable, leveled compaction, WAL, MVCC, value log, zero-copy чтение через mmap |
| <img src="https://cdn.simpleicons.org/etcd/419EDA" width="16" /> **Распределённые системы** | Raft с нуля, Multi-Raft, консенсус, восстановление после сетевых сбоев |
| <img src="https://cdn.simpleicons.org/docker/2496ED" width="16" /> **Инфраструктура** | PostgreSQL (pgvector, tsvector) · Redis · Docker/Compose · Linux: epoll, сокеты, сигналы |
| <img src="https://cdn.simpleicons.org/grpc/244c5a" width="16" /> **API** | gRPC, REST, WebSocket, CLI на Cobra |
| <img src="https://cdn.simpleicons.org/linux/FCC624" width="16" /> **Тестирование и качество** | Unit, integration, crash-тесты · benchmark CI с порогом регрессии · `-race` · pprof |

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
<sub>Telegram <a href="https://t.me/ebssy">@ebssy</a> · Habr <a href="https://habr.com/ru/users/norzy/">norzy</a> · <a href="mailto:e04579138@gmail.com">почта</a></sub>
</div>
