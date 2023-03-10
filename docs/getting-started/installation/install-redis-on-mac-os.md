# Установка Redis в macOS

Используйте Homebrew для установки и запуска Redis в macOS

---

В этом руководстве показано, как установить Redis в macOS с помощью Homebrew. Homebrew — это самый простой способ установить Redis в macOS. Если вы предпочитаете собирать Redis из исходных файлов в macOS, см. раздел [Установка Redis из исходного кода](install-redis-from-source.md).

## Предварительные требования

Во-первых, убедитесь, что у вас установлен Homebrew. Из терминала запустите:

``` bash
$ brew --version
```

Если эта команда не удалась, вам нужно будет [следовать инструкциям по установке Homebrew](https://brew.sh/).

## Установка

Из терминала запустите:

``` bash
brew install redis
```

Эта команда установит Redis в вашу систему.

## Запуск и остановка Redis на переднем плане

Чтобы протестировать установку Redis, вы можете выаолнить команду `redis-server` из командной строки:

``` bash
redis-server
```

В случае успеха вы увидите журналы запуска Redis и Redis будет работать на переднем плане.

Чтобы остановить Redis, введите `Ctrl-C`.

### Запуск и остановка Redis с помощью launchd

В качестве альтернативы запуску Redis на переднем плане вы также можете использовать `launchd` для запуска процесса в фоновом режиме:

``` bash
brew services start redis
```

Эта команда запускает Redis и перезапускает его при входе в систему. Вы можете проверить состояние Redis под управлением `launchd`, выполнив следующее:

``` bash
brew services info redis
```

Если служба запущена, вы увидите следующий вывод:

``` bash
redis (homebrew.mxcl.redis)
Running: ✔
Loaded: ✔
User: miranda
PID: 67975
```

Чтобы остановить службу, выполните:

``` bash
brew services stop redis
```

## Подключение к Redis

После запуска Redis вы можете протестировать его, запустив `redis-cli`:

``` bash
redis-cli
```

Это откроет Redis REPL. Попробуйте выполнить несколько команд:

``` bash
127.0.0.1:6379> lpush demos redis-macOS-demo
OK
127.0.0.1:6379> rpop demos
"redis-macOS-demo"
```

## Следующие шаги

Если у вас есть работающий экземпляр Redis, вы можете:

* Попробуйте учебник Redis CLI
* Подключиться с помощью одного из клиентов Redis
