<img height="67" width="192" src="https://raw.githubusercontent.com/artem-malko/artwork/master/tars/logo.png">
=============

Сборщик html-верстки, основанный на <a href="http://gulpjs.com/" target="_blank">gulp.js</a>. Облегчает и ускоряет процесс html-верстки любой сложности. Подойдет как командам, так и отдельному разработчику.

TARS — сборщик-фреймворк, включающий в себя набор gulp-тасков, предоставляющий возможность легкого расширения (создания новых тасков) и модифицирования уже существующих.

Основные фичи
-------------

Ниже перечислены только часть особенностей, на самом деле их гораздо больше)

* Jade или Handlebars на выбор в качестве html-шаблонизатора.
* Использование json для передачи данных в шаблоны (опционально, но очень крутая штука, которая позволит избавиться от копипаста).
* SCSS, LESS или Stylus в качестве препроцессора для css. Также в комплекте идет небольшой набор миксинов.
* Никаких внешних библиотек и плагинов (кроме html5shiv). И да, это фича, так как вы вольны сами выбирать, какие библиотеки использовать.
* Watching за изменениями файлов (создания и удаления). В текущей версии gulp вотчер имеет <a href="https://github.com/gulpjs/gulp/issues/651" target="_blank">много проблем</a>. Поэтому был написан свой модуль для этого. С 4 версией gulp будем использовать встроенный, так как планируется, что он избавится от всех недостатков.
* Расшаривание верстки с вашего компьютера во внешний веб, опционально.
* Можно легко добавлять новые таски. Есть примеры того, как создать и использовать новый таск внутри TARS.
* Умная работа с изображениями. В первую очередь с вектором (svg).
* Несколько режимов сборки (обычная, с минифицированными файлами, с хешем в названии css- и js-файлов для выкладки в продакшн).
* Создание архива с готовой сборкой.

Установка
----------

Необходимо установить `nodeJS` версии выше или равной 0.8
Далее необходимо установить gulp глобально. (Возможно потребуются права суперюзера или администратора)

```shell
    npm i -g gulp
```

Затем устанавливаем зависимости.

```shell
    npm i or npm install
```

Если не все зависимости были установлены, то последнюю оперцию нужно повторить.

После установки всех зависимостей необходимо открыть projectConfig и настроить проект под себя. В конфиге вы можете выбрать шаблонизатор, css-препроцессор, использование уведомлений, имена папок для различной статики и т.д.
После настройки проекта, выполняем следующую команду:    

```shell
    gulp init
```

Данная команда создаст базовую файловую структуру, подтянет таски для выбранных вами шаблонизатора и css-препроцессора.

Все готово, можно колбасить :)

Основные команды
----------------

`gulp init` — Инициализирует проект с заданными опциями в projectConfig.

`gulp re-init` — Переинициализирует проект с заданными опциями в projectConfig. Предлагается использовать данную команду, если вы инициализировали проект с неверными опциями. При переинициализации все папки и файлы удаляются, поэтому не рекомендуется выполнять эту команду, если вы уже начали выполнение работы.

`gulp` или `gulp build` — делает сборку проекта. Подключаются не минимизированные файлы. Тип сборки зависит от переданных ключей вместе с этой командой. Доступные ключи:

* `--min` – в html подключаются минимизированные файлы.
* `--release` – в html подключаются минимизированные файлы, в названии которых есть hash. Данный режим полезен, если вы напрямую выкладываете верстку на сервер. 

`gulp dev` — инициализация сборщика в режиме разработки. Создается dev-версия проекта, без всех минификаций. Также запускает вотчеры за файлами проекта. Доступные ключи:

* `--lr` – инициализация livereload, если он включен в конфиге проекта.
* `--tunnel` – инициализация проекта с расшаривание верстки во внешний веб.

Ссылка будет указана в консоли.

`gulp build-dev` — генерация dev-версии проекта без вотчеров.

Ключи, доступные при любом режиме сборки:
* `--ie9` – включить в сборку стили для ie9.
* `--ie8` – включить в сборку стили для ie8.

`gulp update` – обновление всех зависимостей сборщика до последних стабильных. Может потребоваться какое-то время на выполнение данной команды. Желательно выполнять раз в неделю.

Документация
------------
* <a href="https://github.com/artem-malko/tars/blob/master/docs/file-structure.md">Файловая структура</a>
* Работа с тасками
* Опции
* Html
* Css
* Js
* Images
* <a href="https://github.com/artem-malko/tars/blob/master/docs/scenarios.md">Сценарии использования</a>
* FAQ

Последние изменения
-------------------
* Тут пока пусто...
