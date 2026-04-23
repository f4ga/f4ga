


<div align="center">
  <a href="https://git.io/typing-svg">
    <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=28&duration=3500&pause=800&color=FFB347&center=true&vCenter=true&width=600&height=70&lines=🪨+ScoriaDB;Embeddable+Key‑Value+Store;Fast+%7C+Reliable+%7C+LSM‑based" alt="Typing SVG" />
  </a>
  <br/>
  <i>Встраиваемая, быстрая и надёжная key‑value база данных на Go</i>
  <br/><br/>
  <a href="https://github.com/your-org/scoriadb" target="_blank"><img src="https://img.shields.io/badge/⭐_GitHub-12100E?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" /></a>
  <a href="#🚀-быстрый-запуск" target="_blank"><img src="https://img.shields.io/badge/🚀_Быстрый_старт-2CA5E0?style=for-the-badge&logo=readthedocs&logoColor=white" alt="Quick Start" /></a>
  <a href="#📖-что-это" target="_blank"><img src="https://img.shields.io/badge/📖_Документация-FFB347?style=for-the-badge&logo=go&logoColor=white" alt="Docs" /></a>
</div>

<img src="https://capsule-render.vercel.app/api?type=waving&height=120&color=gradient&customColorList=12,18,24,27,30&section=header&text=&fontSize=0" width="100%" />

## 📖 Что это?

**ScoriaDB** — это встраиваемая база данных «ключ‑значение», написанная на чистом Go.  
Она хранит данные в памяти и на диске, умеет быстро читать и записывать даже очень большие значения, не теряет данные при сбоях и готова к использованию прямо внутри вашего приложения.

Название происходит от слова **scoria** (вулканический шлак) — лёгкий, прочный камень. Мы строим хранилище таким же: лёгким, надёжным и красивым внутри.

<img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&height=3&section=header&text=&fontSize=0" width="100%" />

## 🧠 Как это работает (простыми словами)

1. **Запись**: вы вызываете `Put("user:1", "Alice")`. Данные сначала попадают в журнал (WAL) на диск, а потом в быструю структуру в памяти — MemTable.
2. **Чтение**: вы вызываете `Get("user:1")`. Мы сначала ищем в памяти, а если там нет — поднимаем данные с диска, но только нужный кусочек, не читая всё подряд.
3. **Сброс на диск**: когда память заполняется, мы аккуратно переносим данные в файлы SSTable — отсортированные и сжатые.
4. **Уборка**: старые версии ключей и мусор автоматически удаляются, чтобы база не разрасталась бесконечно.
5. **Большие значения**: если значение очень длинное, мы храним его отдельно в специальном «журнале значений» и показываем напрямую из памяти, не копируя.

<img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&height=3&section=header&text=&fontSize=0" width="100%" />

## 🚀 Быстрый запуск

### Сборка из исходников

```bash
git clone https://github.com/your-org/scoriadb.git
cd scoriadb
go build ./...
```

### Запуск сервера

```bash
go run cmd/server/main.go
```

Сервер слушает gRPC на порту **50051** и HTTP/Web UI на порту **8080**.

### Установка CLI

```bash
go run cmd/cli/main.go --help
```

### Docker

```bash
docker-compose up -d
```

Web UI откроется по адресу http://localhost:8080.

<img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&height=3&section=header&text=&fontSize=0" width="100%" />

## 💡 Как пользоваться в своём коде

```go
import (
    "fmt"
    "github.com/your-org/scoriadb/pkg/scoria"
)

func main() {
    // Открываем базу в папке /tmp/mydb
    db, err := scoria.Open(scoria.DefaultOptions("/tmp/mydb"))
    if err != nil {
        panic(err)
    }
    defer db.Close()

    // Кладём значение
    if err := db.Put([]byte("привет"), []byte("мир")); err != nil {
        panic(err)
    }

    // Читаем значение
    val, err := db.Get([]byte("привет"))
    if err != nil {
        panic(err)
    }
    fmt.Println(string(val)) // "мир"
}
```

<img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&height=3&section=header&text=&fontSize=0" width="100%" />

## 🧩 Основные возможности (MVP)

<table align="center">
  <tr><td width="50%" valign="top">
    <h3>✅ LSM‑дерево</h3>
    <p>Быстрая запись и чтение, компактное хранение на диске.</p>
    </td>
   <td width="50%" valign="top">
    <h3>✅ Bloom‑фильтры</h3>
    <p>Молниеносная проверка «а есть ли ключ?» без лишних дисковых операций.</p>
    </td>
  </tr>
  <tr><td width="50%" valign="top">
    <h3>✅ Журнал (WAL)</h3>
    <p>Никаких потерь при внезапном сбое — все операции сначала логируются.</p>
    </td>
   <td width="50%" valign="top">
    <h3>✅ Разделение значений</h3>
    <p>Большие данные не тормозят основное дерево — хранятся отдельно (Value Log).</p>
    </td>
  </tr>
  <tr><td width="50%" valign="top">
    <h3>🔜 MVCC</h3>
    <p>Версионность и чтение «на определённый момент» (в работе).</p>
    </td>
   <td width="50%" valign="top">
    <h3>🔜 Транзакции</h3>
    <p>Групповые операции с гарантией согласованности (в работе).</p>
    </td>
  </tr>
  <tr><td width="50%" valign="top">
    <h3>🔜 gRPC API</h3>
    <p>Доступ из любого языка.</p>
    </td>
   <td width="50%" valign="top">
    <h3>🔜 Веб‑интерфейс</h3>
    <p>Просмотр данных через браузер.</p>
    </td>
  </table>
</table>

<img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&height=3&section=header&text=&fontSize=0" width="100%" />

## 🛠️ Технологии

| Компонент | Инструмент |
|-----------|------------|
| Язык | Go 1.23+ |
| Дерево в памяти | google/btree |
| SSTable | Собственный формат (блоки, сжатие ключей) |
| Фильтр Блума | github.com/bits-and-blooms/bloom |
| WAL | Файл с контрольной суммой CRC32 |
| Value Log | Отображаемый в память файл (mmap) |
| gRPC | google.golang.org/grpc |
| CLI | cobra |
| Web UI | React + Vite + Tailwind |

<img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&height=3&section=header&text=&fontSize=0" width="100%" />

## 📁 Структура проекта

```
scoriadb/
├── cmd/
│   ├── server/          # запуск сервера
│   └── cli/             # консольный клиент
├── internal/
│   ├── engine/          # ядро LSM‑движка
│   ├── engine/sstable/  # чтение/запись SSTable
│   ├── mvcc/            # многоверсионность (в разработке)
│   ├── txn/             # транзакции (в разработке)
│   ├── api/grpc/        # gRPC сервис
│   ├── auth/            # пользователи и права
│   └── metrics/         # метрики Prometheus
├── pkg/scoria/          # публичный API для встраивания
├── proto/               # protobuf описания
├── web/                 # React приложение
├── test/                # интеграционные тесты
└── deployments/         # Docker, docker-compose
```

<img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&height=3&section=header&text=&fontSize=0" width="100%" />

## 🧪 Разработка

```bash
# все юнит‑тесты
go test ./... -v

# бенчмарки
go test ./internal/engine -bench=. -benchmem

# проверка гонок
go test ./... -race
```

<img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&height=3&section=header&text=&fontSize=0" width="100%" />

## 🗺️ Что дальше

- [x] Ядро LSM
- [x] SSTable и фильтры Блума
- [ ] MVCC и транзакции (следующий этап)
- [ ] Распределённый режим (Raft, шардирование)
- [ ] Веб‑интерфейс и CLI‑ассистент
- [ ] Kubernetes оператор
<br />

<div align="center">
  <a href="https://visitor-badge.laobi.icu/badge?page_id=scoriadb.scoriadb">
    <img src="https://visitor-badge.laobi.icu/badge?page_id=scoriadb.scoriadb&left_color=black&right_color=FFB347&left_text=Profile%20Views" />
  </a>
</div>

<img src="https://capsule-render.vercel.app/api?type=waving&height=100&color=gradient&customColorList=12,18,24,27,30&section=footer&text=&fontSize=0" width="100%" />
