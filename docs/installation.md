# Laravel 9 · Установка

- [Встречайте Laravel](#meet-laravel)
    - [Почему именно Laravel?](#why-laravel)
- [Ваш первый проект на Laravel](#your-first-laravel-project)
    - [Начало работы в macOS](#getting-started-on-macos)
    - [Начало работы в Windows](#getting-started-on-windows)
    - [Начало работы в Linux](#getting-started-on-linux)
    - [Выбор служб Sail](#choosing-your-sail-services)
    - [Установка через Composer](#installation-via-composer)
- [Начальная конфигурация](#initial-configuration)
    - [Конфигурация на основе окружения](#environment-based-configuration)
    - [Конфигурация каталога](#directory-configuration)
- [Следующие шаги](#next-steps)
    - [Laravel как клиент-серверный фреймворк](#laravel-the-fullstack-framework)
    - [Laravel в качестве сервера API](#laravel-the-api-backend)

<a name="meet-laravel"></a>
## Встречайте Laravel

Laravel – фреймворк веб-приложения с выразительным, элегантным синтаксисом. Веб-фреймворк предлагает структуру и отправную точку для создания вашего приложения, позволяя вам сосредоточиться на создании чего-то удивительного, но пока мы не будем вдаваться в детали.

Laravel стремится обеспечить потрясающий опыт разработчика, предоставляя при этом мощный функционал: тщательное внедрение зависимостей, выразительный уровень абстракции базы данных, очереди и запланированные задачи, модульное и интеграционное тестирование и многое другое.

Независимо от того, новичок ли вы в PHP, веб-фреймворках или имеете многолетний опыт, Laravel – это фреймворк, который может расти вместе с вами. Мы поможем вам сделать первые шаги в качестве веб-разработчика или подскажем, как вы поднимите свой опыт на новый уровень. Нам не терпится увидеть, что вы построите.

<a name="why-laravel"></a>
### Почему именно Laravel?

При создании веб-приложения вам доступны различные инструменты и фреймворки. Однако мы считаем, что Laravel – лучший выбор для создания современных полнофункциональных веб-приложений.

#### Прогрессивный фреймворк

Нам нравится называть Laravel «прогрессивным» фреймворком. Под этим мы подразумеваем, что Laravel растет вместе с вами. Если вы только делаете первые шаги в веб-разработке, обширная библиотека документации, руководств и [видеоуроков](https://laracasts.com) Laravel поможет вам изучить основы, не перегружая себя.

Если вы старший разработчик, Laravel предлагает вам надежные инструменты для [внедрения зависимостей](container.md), [модульного тестирования](testing.md), [создания очередей](queues.md), [событий в реальном времени](broadcasting.md) и многое другое. Laravel оптимизирован для создания профессиональных веб-приложений и готов обрабатывать корпоративные рабочие нагрузки.

#### Масштабируемый фреймворк

Laravel невероятно масштабируем. Благодаря удобному для масштабирования характеру PHP и встроенной поддержке быстрых распределенных систем кеширования, таких как Redis, горизонтальное масштабирование с Laravel очень просто. Фактически, приложения Laravel легко масштабируются для обработки сотен миллионов запросов в месяц.

Требуется экстремальное масштабирование? Такие платформы, как [Laravel Vapor](https://vapor.laravel.com), позволяют запускать приложение Laravel в практически неограниченном масштабе с использованием новейшей бессерверной технологии AWS.

#### Фреймворк сообщества

Laravel объединяет лучшие пакеты в экосистеме PHP, чтобы предложить наиболее надежный и удобный для разработчиков фреймворк. Кроме того, тысячи талантливых разработчиков со всего мира [внесли свой вклад в фреймворк](https://github.com/laravel/framework). Кто знает, возможно, вы даже станете соучастником Laravel.

<a name="your-first-laravel-project"></a>
## Ваш первый проект на Laravel

Мы хотим, чтобы начать работу с Laravel было как можно проще. Существует множество вариантов разработки и запуска проекта Laravel на вашем собственном компьютере. Хотя вы, возможно, захотите изучить эти варианты позже, но Laravel предлагает [Sail](sail.md) – встроенное решение для запуска вашего проекта Laravel с помощью [Docker](https://www.docker.com).

Docker – это инструмент для запуска приложений и служб в небольших, легких «контейнерах», которые не мешают установленному на вашем локальном компьютере программному обеспечению или его конфигурации. Это означает, что вам не нужно беспокоиться о конфигурировании или настройке сложных инструментов разработки, таких как веб-серверы и базы данных на вашем персональном компьютере. Для начала вам нужно всего лишь установить [Docker Desktop](https://www.docker.com/products/docker-desktop).

Laravel Sail – это легкий интерфейс командной строки для взаимодействия с конфигурацией Docker по умолчанию в Laravel. Sail обеспечивает отличную отправную точку для создания приложения Laravel с использованием PHP, MySQL и Redis без предварительного опыта работы с Docker.

> {tip} Уже знакомы с Docker? Не волнуйтесь! Все в Sail можно перенастроить с помощью файла `docker-compose.yml`, входящего в Laravel.

<a name="getting-started-on-macos"></a>
### Начало работы в macOS

Если вы разрабатываете на Mac и [Docker Desktop](https://www.docker.com/products/docker-desktop) уже установлен, то вы можете использовать простую команду терминала для создания нового проекта Laravel. Например, чтобы создать новое приложение Laravel в каталоге с именем `example-app`, вы можете запустить следующую команду в своем терминале:

```shell
curl -s https://laravel.build/example-app | bash
```

Конечно, вы можете изменить `example-app` в этом URL на что угодно – просто убедитесь, что имя приложения содержит только буквенно-цифровые символы, дефисы и символы подчеркивания. Каталог приложения Laravel будет создан в каталоге, из которого вы выполняете команду.

После создания проекта вы можете перейти в каталог приложения и запустить Laravel Sail. Laravel Sail предлагает простой интерфейс командной строки для взаимодействия с конфигурацией Docker по умолчанию в Laravel:

```shell
cd example-app

./vendor/bin/sail up
```

При первом запуске команды `up` Sail на вашем компьютере будут созданы контейнеры приложений Sail. Это может занять несколько минут. **Не волнуйтесь, последующие попытки запустить Sail будут намного быстрее**.

После запуска контейнеров приложения Docker, вы можете получить доступ к приложению в своем веб-браузере по адресу: http://localhost.

> {tip} Чтобы продолжить изучение Laravel Sail, просмотрите его [полную документацию](sail.md).

<a name="getting-started-on-windows"></a>
### Начало работы в Windows

Прежде чем мы создадим новое приложение Laravel на вашем компьютере с Windows, обязательно установите [Docker Desktop](https://www.docker.com/products/docker-desktop). Затем вы должны убедиться, что подсистема Windows для Linux 2 (WSL2) установлена и включена. WSL позволяет запускать двоичные исполняемые файлы Linux прямо в Windows 10. Информацию о том, как установить и включить WSL2, можно найти в [документации Среда разработки](https://docs.microsoft.com/ru-ru/windows/wsl/install-win10).

> {tip} После установки и включения WSL2 вы должны убедиться, что Docker Desktop [настроен на использование серверной части WSL2](https://docs.docker.com/docker-for-windows/wsl/).

Теперь вы готовы создать свой первый проект Laravel. Запустите [Терминал Windows](https://www.microsoft.com/ru-ru/p/windows-terminal/9n0dx20hk701?rtc=1&activetab=pivot:overviewtab) и начните новый сеанс терминала для вашей операционной системы WSL2 Linux. Затем вы можете использовать простую команду терминала для создания нового проекта Laravel. Например, чтобы создать новое приложение Laravel в каталоге с именем `example-app`, вы можете запустить следующую команду в своем терминале:

```shell
curl -s https://laravel.build/example-app | bash
```

Конечно, вы можете изменить `example-app` в этом URL на что угодно – просто убедитесь, что имя приложения содержит только буквенно-цифровые символы, дефисы и символы подчеркивания. Каталог приложения Laravel будет создан в каталоге, из которого вы выполняете команду.

После создания проекта вы можете перейти в каталог приложения и запустить Laravel Sail. Laravel Sail предлагает простой интерфейс командной строки для взаимодействия с конфигурацией Docker по умолчанию в Laravel:

```shell
cd example-app

./vendor/bin/sail up
```

При первом запуске команды `up` Sail на вашем компьютере будут созданы контейнеры приложений Sail. Это может занять несколько минут. **Не волнуйтесь, последующие попытки запустить Sail будут намного быстрее**.

После запуска контейнеров приложения Docker, вы можете получить доступ к приложению в своем веб-браузере по адресу: http://localhost.

> {tip} Чтобы продолжить изучение Laravel Sail, просмотрите его [полную документацию](sail.md).

#### Разработка в подсистеме WSL2

Конечно, вам нужно будет иметь возможность изменять файлы приложения Laravel, которые были созданы в вашей установке WSL2. Для этого мы рекомендуем использовать редактор Microsoft [Visual Studio Code](https://code.visualstudio.com) и его собственное расширение [Remote Development](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack).

После установки этих инструментов вы можете открыть любой проект Laravel, выполнив из корневого каталога вашего приложения команду `code .` с помощью Терминала Windows.

<a name="getting-started-on-linux"></a>
### Начало работы в Linux

Если вы разрабатываете в Linux и [Docker Compose](https://docs.docker.com/compose/install/) уже установлен, то вы можете использовать простую команду терминала для создания нового проекта Laravel. Например, чтобы создать новое приложение Laravel в каталоге с именем `example-app`, вы можете запустить следующую команду в своем терминале:

```shell
curl -s https://laravel.build/example-app | bash
```

Конечно, вы можете изменить `example-app` в этом URL на что угодно – просто убедитесь, что имя приложения содержит только буквенно-цифровые символы, дефисы и символы подчеркивания. Каталог приложения Laravel будет создан в каталоге, из которого вы выполняете команду.

После создания проекта вы можете перейти в каталог приложения и запустить Laravel Sail. Laravel Sail предлагает простой интерфейс командной строки для взаимодействия с конфигурацией Docker по умолчанию в Laravel:

```shell
cd example-app

./vendor/bin/sail up
```

При первом запуске команды `up` Sail на вашем компьютере будут созданы контейнеры приложений Sail. Это может занять несколько минут. **Не волнуйтесь, последующие попытки запустить Sail будут намного быстрее**.

После запуска контейнеров приложения Docker, вы можете получить доступ к приложению в своем веб-браузере по адресу: http://localhost.

> {tip} Чтобы продолжить изучение Laravel Sail, просмотрите его [полную документацию](sail.md).

<a name="choosing-your-sail-services"></a>
### Выбор служб Sail

При создании нового приложения Laravel через Sail вы можете использовать строковую переменную запроса `with`, чтобы выбрать, какие службы должны быть настроены в файле `docker-compose.yml` вашего нового приложения. Доступны следующие службы `mysql`, `pgsql`, `mariadb`, `redis`, `memcached`, `meilisearch`, `minio`,`selenium` и `mailhog`:

```shell
curl -s "https://laravel.build/example-app?with=mysql,redis" | bash
```

Если вы не укажете желаемые службы, то будет сконфигурирован стек по умолчанию из `mysql`, `redis`, `meilisearch`, `mailhog` и `selenium`.

Вы можете указать Sail установить [Devcontainer](sail.md#using-devcontainers) по умолчанию, добавив параметр `devcontainer` к URL-адресу:

```shell
curl -s "https://laravel.build/example-app?with=mysql,redis&devcontainer" | bash
```

<a name="installation-via-composer"></a>
### Установка через Composer

Если на вашем компьютере уже установлены PHP и Composer, то вы можете создать новый проект Laravel напрямую с помощью Composer. После того, как приложение было создано, вы можете запустить локальный сервер разработки Laravel с помощью команды `serve` Artisan CLI:

```shell
composer create-project laravel/laravel example-app

cd example-app

php artisan serve
```

<a name="the-laravel-installer"></a>
#### Установщик Laravel

В качестве альтернативы, вы можете использовать установщик Laravel, включив его в глобальную зависимость Composer:

```shell
composer global require laravel/installer

laravel new example-app

cd example-app

php artisan serve
```

Чтобы исполняемый файл `laravel` мог быть обнаружен вашей системой, удостоверьтесь в правильном расположении каталога `bin` менеджера пакетов Composer, задаваемый системной переменной `$PATH`. Расположение каталога зависит от вашей операционной системы, но типичными могут быть:

<!-- <div class="content-list" markdown="1"> -->

- macOS: `$HOME/.composer/vendor/bin`
- Windows: `%USERPROFILE%\AppData\Roaming\Composer\vendor\bin`
- GNU / Linux Distributions: `$HOME/.config/composer/vendor/bin` или `$HOME/.composer/vendor/bin`

<!-- </div> -->

Для удобства установщик Laravel также может создать репозиторий Git для вашего нового проекта. Чтобы указать, что вы хотите создать репозиторий Git, передайте флаг `--git` при создании нового проекта:

```shell
laravel new example-app --git
```

Эта команда инициализирует новый репозиторий Git для вашего проекта и автоматически зафиксирует базовый каркас Laravel. Флаг `--git` предполагает, что вы правильно установили и настроили Git. Можно также использовать параметр `--branch`, чтобы задать имя ответвления:

```shell
laravel new example-app --git --branch="main"
```

Вместо использования флага `--git` вы можете использовать параметр `--github`, чтобы создать репозиторий Git и, соответствующий ему, частный репозиторий на GitHub:

```shell
laravel new example-app --github
```

Созданный репозиторий будет доступен по адресу `https://github.com/<your-account>/example-app`. Параметр `--github` предполагает, что вы правильно установили [GitHub CLI](https://cli.github.com) и прошли аутентификацию с помощью интерфейса командной строки. Кроме того, у вас должен быть установлен и правильно настроен [git](https://git-scm.com/). При необходимости вы можете передать [дополнительные параметры и флаги](https://cli.github.com/manual/gh_repo_create), поддерживаемые GitHub CLI:

```shell
laravel new example-app --github="--public"
```

Можно использовать параметр `--organization` для создания репозитория под определенной организацией GitHub:

```shell
laravel new example-app --github="--public" --organization="laravel"
```

<a name="initial-configuration"></a>
## Начальная конфигурация

Все файлы конфигурации для фреймворка Laravel хранятся в каталоге `config`. Каждый параметр имеет комментарии, поэтому не стесняйтесь просматривать файлы и знакомиться с доступными вам вариантами.

Laravel практически не требует дополнительной настройки из коробки. Вы можете начать разработку! Однако вы можете просмотреть файл `config/app.php` и его комментарии. Он содержит несколько параметров, таких как часовой пояс и локаль, которые вы можете изменить в соответствии с вашим приложением.

<a name="environment-based-configuration"></a>
### Конфигурация на основе окружения

Поскольку многие значения параметров конфигурации Laravel могут различаться в зависимости от того, работает ли ваше приложение на локальном компьютере или на эксплуатационном веб-сервере, многие важные значения конфигурации определяются с помощью файла `.env`, существующий в корне вашего приложения.

Ваш файл `.env` не должен быть привязан к системе контроля версий вашего приложения, поскольку каждому разработчику / серверу, использующему ваше приложение, может потребоваться другая конфигурация окружения. Более того, это будет угрозой безопасности в случае, если злоумышленник получит доступ к вашему репозиторию системы управления версиями, поскольку любые конфиденциальные учетные данные будут раскрыты.

> {tip} Для получения дополнительной информации о конфигурации на основе файла `.env` и окружения ознакомьтесь с полной [документацией по конфигурации](configuration.md#environment-configuration).

<a name="directory-configuration"></a>
### Конфигурация каталога

Laravel всегда должен обслуживаться из корня «веб-каталога», настроенного для вашего веб-сервера. Вы не должны пытаться обслуживать приложение Laravel из поддиректории относительно «веб-каталога». Такая попытка может открыть доступ к конфиденциальным файлам, существующим в вашем приложении.

<a name="next-steps"></a>
## Следующие шаги

Теперь, когда вы создали свой проект Laravel, вам может быть интересно, чему научиться дальше. Во-первых, мы настоятельно рекомендуем ознакомиться с тем, как работает Laravel, прочитав следующие разделы документации:

<!-- <div class="content-list" markdown="1"> -->

- [Жизненный цикл запроса](lifecycle.md)
- [Конфигурирование](configuration.md)
- [Структура каталогов](structure.md)
- [Контейнер служб](container.md)
- [Фасады](facades.md)

<!-- </div> -->

То, как вы хотите использовать Laravel, также будет определять следующие шаги на вашем пути. Существует множество способов использования Laravel, и мы рассмотрим два основных варианта использования фреймворка ниже.

<a name="laravel-the-fullstack-framework"></a>
### Laravel как клиент-серверный фреймворк

Laravel может служить клиент-серверным фреймворком. Под «клиент-серверным фреймворком» мы подразумеваем, что вы собираетесь использовать Laravel для маршрутизации запросов к вашему приложению и отрисовки интерфейса через [шаблоны Blade](blade.md) или с использованием гибридной технологии одностраничного приложения, такой как [Inertia.js](https://inertiajs.com). Это наиболее распространенный способ использования фреймворка Laravel.

Если вы планируете использовать Laravel именно таким образом, вы можете ознакомиться с нашей документацией по [маршрутизации](routing.md), [представлениям](views.md) или [Eloquent ORM](eloquent.md). Кроме того, вам может быть интересно узнать о таких пакетах сообщества, как [Livewire](https://laravel-livewire.com) и [Inertia.js](https://inertiajs.com). Эти пакеты позволяют использовать Laravel в качестве фреймворка полного стека, при этом пользуясь многими преимуществами UI, предоставляемыми одностраничными JavaScript-приложениями.

Если вы используете Laravel в качестве фреймворка полного стека, мы также настоятельно рекомендуем вам научиться компилировать CSS и JavaScript вашего приложения с помощью [Laravel Mix](mix.md).

> {tip} Если вы хотите получить преимущество перед созданием своего приложения, ознакомьтесь с одним из наших официальных [стартовых комплектов приложений](starter-kits.md).

<a name="laravel-the-api-backend"></a>
### Laravel в качестве сервера API

Laravel также может служить серверной частью API для одностраничного JavaScript-приложения или мобильного приложения. Например, вы можете использовать Laravel в качестве серверной части API для своего [Next.js](https://nextjs.org) приложения. В этом контексте вы можете использовать Laravel для обеспечения [аутентификации](sanctum.md) и хранения / получения данных для вашего приложения, а также пользуясь преимуществами мощных служб Laravel, таких как очереди, электронная почта, уведомления и многое другое.

Если вы планируете использовать Laravel именно так, то вы можете ознакомиться с нашей документацией по [маршрутизации](routing.md), пакету [Laravel Sanctum](sanctum.md) и [Eloquent ORM](eloquent.md).

> {tip} Вы хотите создать бэкэнд на Laravel и интерфейс на Next.js? Laravel Breeze предлагает [стек API](starter-kits.md#breeze-and-next), а также [реализацию внешнего интерфейса Next.js](https://github.com/laravel/breeze-next ), чтобы вы могли начать работу за считанные минуты.
