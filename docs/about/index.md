# Введение в Redis

Узнайте о проекте Redis с открытым исходным кодом

---

Redis - это __хранилище структур данных__ в памяти с открытым исходным кодом (под лицензией BSD), используемое в качестве базы данных, кеша, брокера сообщений и механизма потоковой передачи. Redis предоставляет [структуры данных](/docs/data-types/) такие как
[строки(strings)](/docs/data-types/strings/), [хеши(hashes)](/docs/data-types/hashes/), [списки(lists)](/docs/data-types/lists/), [множества(sets)](/docs/data-types/sets/), [отсортированные множества(sorted sets)](/docs/data-types/sorted-sets/) с запросами диапазона, [битовые карты(bitmaps)](/docs/data-types/bitmaps/), [гиперлоглоги(hyperloglogs)](/docs/data-types/hyperloglogs/), [геопространственные индексы(geospatial indexes)](/docs/data-types/geospatial/) и [потоки(streams)](/docs/data-types/streams/). Redis имеет встроенную [репликацию](/topics/replication), [Lua-скрипты](/commands/eval), [LRU вытеснение](/docs/reference/eviction/), [транзакции](/topics/transactions) и другие уровни [хранения данных на диске](/topics/persistence), а также обеспечивает высокую доступность с помощью [Redis Sentinel](/topics/sentinel) и автоматического секционирования с помощью [Redis Cluster](/topics/cluster-tutorial).

Вы можете выполнять __атомарные операции__
над этими типами, например, [добавление к строке](/commands/append);
[инкрементирование значения в хеше](/commands/hincrby); [добавление элемента в
список](/commands/lpush); [вычисление пересечения множества](/commands/sinter),
[объединения](/commands/sunion) и [разности](/commands/sdiff);
или [получение члена с наивысшим рейтингом в отсортированном множестве](/commands/zrange).

Для достижения максимальной производительности Redis работает с
**набором данных в памяти**. В зависимости от вашего варианта использования Redis может сохранять ваши данные либо путем
периодического [сброса набора данных на диск](/topics/persistence#snapshotting)
либо путем [добавления каждой команды в журнал на диске](/topics/persistence#append-only-file). Вы также можете отключить сохраняемость, если вам просто нужен многофункциональный сетевой кэш в памяти.

Redis поддерживает [асинхронную репликацию](/topics/replication), с быстрой неблокирующей синхронизацией и автоматическим повторным подключением с частичной повторной синхронизацией при разделении сети.

Redis также включает в себя:

* [Транзакции](/topics/transactions)
* [Pub/Sub](/topics/pubsub)
* [Lua-скрипты](/commands/eval)
* [Ключи с ограниченным сроком жизни](/commands/expire)
* [LRU вытеснение ключей](/docs/reference/eviction)
* [Автоматический переход на другой ресурс(аварийное переключение)](/topics/sentinel)

Вы можете использовать Redis из [большинства языков программирования](/clients).

Redis написан на **ANSI C** и работает в большинстве систем POSIX, таких как Linux,
\*BSD, и Mac OS X, без внешних зависимостей. Linux и OS X — это две операционные системы, в которых Redis разрабатывается и тестируется больше всего, и мы **рекомендуем использовать Linux для развертывания**. Redis может работать в системах, производных от Solaris, таких как SmartOS, но поддержка *все что мы можем предложить*.
Официальной поддержки сборок Windows нет.
