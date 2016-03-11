# kodi.edemtv.playlist
Подготовленный плейлист на основе данных edem.tv для подключения к PVR IPTV Simple Client.
В том числе исключает армянские телеканалы из списка.

### Использование готового плейлиста
1. Установить [PVR IPTV Simple Client][iptvsimple]
2. Установки EPG:
   * Расположение: Удаленный путь (интернет);
   * Ссылка на XMLTV: [http://georgemikl.ucoz.ru/load/0-0-0-4-20][xmltv];
3. Скачать и разархивировать содержание проекта
4. В файле compiled_edem_pl.m3u заменить строку "{{your_token}}" на ваш ключ доступа на [edem.tv][edemtvkey]. Далее -- сохранить файл.
5. IPTV Simple Client Основные настройки:
   * Расположение: Локальный путь;
   * Путь к M3U: выбрать compiled_edem_pl.m3u
6. В настройках *Kodi - ТВ - Меню/OSD - Папка со значками каналов* выбиррать "picons", включить "Искать недостающие значки".
7. Для каналов с отсутствующими логотипами (например "Viasat Nature\History HD") вручную установить значки.
8. Перезагрузить Kodi

### Формирование нового плейлиста
Проект содержит скрипт converter, позволяющий правильно форматировать и подготовить плейлист для Kodi из скачанного на edem.tv плейлиста.

1. В личном кабинете edem.tv скачать плейлист с интересующего сервера, под именем "edem_pl.m3u8" сохранить в папке "converter"
2. Скачать и разархивировать файл "xmltv.xml" с актуальной телепрограммой в папку "converter".
3. Выполнить
    ```sh
    $ php converter.php
    ```
4. Скрипт переименовывает каналы для соответствия их телепрограмме и пиктограммам. Некоторые каналы могут не пристутствовать в телепрограмме или не иметь пиктограмм, о чем будет сообщено в выводе скрипта.
5. Настроить Kodi в соответствии с разделом "Использование готового плейлиста"

### Пиктограммы телеканалов
[Отсюда][picons]


[iptvsimple]: <http://kodi.wiki/view/Add-on:IPTV_Simple_Client>
[xmltv]: <http://georgemikl.ucoz.ru/load/0-0-0-4-20>
[edemtvkey]: <https://edem.tv/account>
[picons]: <http://logo.fight-show.ru/logos/>
