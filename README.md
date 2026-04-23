
<div align="center">
  <!-- Основной баннер-заголовок -->
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12&height=200&section=header&text=🪨%20ScoriaDB&fontSize=70&fontAlignY=40&animation=fadeIn" alt="Header">


  <!-- Второй уровень с кратким описанием -->
  <img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=1&height=60&section=header&text=🔥%20Встраиваемая%20LSM%20база%20данных%20на%20Go%20|%20Быстрая%20как%20камень%20и%20лёгкая%20как%20пепел&fontSize=20&fontAlignY=50&animation=twinkling" alt="Subtitle">

</div>





---

## 🧠 Как это работает (простыми словами)

1.  **Запись**: вы вызываете `Put("user:1", "Alice")`. Данные сначала попадают в журнал (WAL) на диск, а потом в быструю структуру в памяти — MemTable.
2.  **Чтение**: вы вызываете `Get("user:1")`. Мы сначала ищем в памяти, а если там нет — поднимаем данные с диска, но только нужный кусочек, не читая всё подряд.
3.  **Сброс на диск**: когда память заполняется, мы аккуратно переносим данные в файлы SSTable — отсортированные и сжатые.
4.  **Уборка**: старые версии ключей и мусор автоматически удаляются, чтобы база не разрасталась бесконечно.
5.  **Большие значения**: если значение очень длинное, мы храним его отдельно в специальном «журнале значений» и показываем напрямую из памяти, не копируя.

---

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

---

## 💡 Как пользоваться в своём коде

```go
package main

import (
    "fmt"
    "log"

    "github.com/your-org/scoriadb/pkg/scoria"
)

func main() {
    // Открываем базу в папке /tmp/mydb
    db, err := scoria.Open(scoria.DefaultOptions("/tmp/mydb"))
    if err != nil {
        log.Fatal(err)
    }
    defer db.Close()

    // Кладём значение
    if err := db.Put([]byte("привет"), []byte("мир")); err != nil {
        log.Fatal(err)
    }

    // Читаем значение
    val, err := db.Get([]byte("привет"))
    if err != nil {
        log.Fatal(err)
    }
    fmt.Println(string(val)) // "мир"
}
```

---

## 🧩 Основные возможности (MVP)

- ✅ **LSM‑дерево** — быстрая запись и чтение
- ✅ **Bloom‑фильтры** — молниеносная проверка «а есть ли ключ?»
- ✅ **Журнал (WAL)** — никаких потерь при сбоях
- ✅ **SSTable** — компактное хранение на диске
- ✅ **Разделение значений** — большие данные не тормозят основное дерево
- 🔜 **MVCC** — версионность и чтение «на определённый момент» (в работе)
- 🔜 **Транзакции** — групповые операции с гарантией согласованности (в работе)
- 🔜 **gRPC API** — доступ из любого языка
- 🔜 **Веб‑интерфейс** — просмотр данных через браузер

---

## 🛠️ Технологии

| Компонент | Инструмент |
| :--- | :--- |
| Язык | Go 1.23+ |
| Дерево в памяти | google/btree |
| SSTable | Собственный формат (блоки, сжатие ключей) |
| Фильтр Блума | github.com/bits-and-blooms/bloom |
| WAL | Файл с контрольной суммой CRC32 |
| Value Log | Отображаемый в память файл (mmap) |
| gRPC | google.golang.org/grpc |
| CLI | cobra |
| Web UI | React + Vite + Tailwind |

---

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

---

## 🧪 Разработка

```bash
# все юнит‑тесты
go test ./... -v

# бенчмарки
go test ./internal/engine -bench=. -benchmem

# проверка гонок
go test ./... -race
```

---

## 🗺️ Что дальше

- [x] Ядро LSM
- [x] SSTable и фильтры Блума
- [ ] MVCC и транзакции (следующий этап)
- [ ] Распределённый режим (Raft, шардирование)
- [ ] Веб‑интерфейс и CLI‑ассистент
- [ ] Kubernetes оператор


<div align="center">
  <!-- Финальная волна, подходящая по стилю -->
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12&height=120§ion=footer">

</div>

