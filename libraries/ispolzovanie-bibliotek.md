# Использование библиотек

Использование библиотек автоматизировано, если вы пользуетесь компилятором valac. Специфичные для Vala файлы в библиотеке называются пакетом. Вы указываете компилятору, в каких пакетах ваша программа нуждается:

`$ valac --pkg gee-1.0 test.vala`

Эта команда значит, что ваша программа может использовать все, что определено в файле gee-1.0.vapi, и так же все, что определено в пакетах, от которых зависит gee-1.0. Эти зависимости перечисляются в gee-1.0.deps, если таковые имеются. В этом примере valac будет создавать бинарный код, поэтому для осуществления линковки библиотек он будет использовать информацию из pkg-config. Вот почему в названиях Vala пакетов используются названия файлов pkg-config.

Пакеты обычно используются пространствами имен, но технически они не связаны. Это значит, что даже если вы собираете приложение с зависимостями, вы все равно должны использовать using в каждом файле или использовать полное название для всех символов.

Возможно так же обращение к локальной библиотеке \(которая не установлена\) как к пакету. Например, сама Vala использует внутреннюю версию Gee. Когда собирается valac создается VAPI файл этой внутренней библиотеки и непосредственно используется так:

`$ valac --vapidir ../gee --pkg gee ...`

За более детальной информацией о генерации такой библиотеки обратитесь к следующему разделу или примеру.

