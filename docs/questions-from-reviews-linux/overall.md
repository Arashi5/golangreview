---
title: Общее
sidebar_position: 1
description: Общие вопросы по Linux
---

## Назовите 10 трехбуквенных команд в Линуксе
1. `pwd` - путь к текущему рабочему каталогу
2. `cat` - вывод содержимого файла в командной строке
3. `tar` - команда для архивирования нескольких файлов
4. `top` - эквивалент диспетчера задач в Windows
5. `man` - подсказки по командам, например: `man tail` покажет инструкцию к команде `tail`.
6. `zip` - команда для сжатия ваших файлов
7. `who` - информация о вошедших пользователях
8. `ssh` - соединение с удаленным сервером по протоколу SSH.
9. `scp` - копирует файлы между удаленным и локальным серверами по протоколу SSH.
10. `sar` - собирает информацию о использовании ресурсов системы, таких как процессор, память, сеть и диски, и сохраняет ее для последующего анализа.

## Как отлистать процессы
Для того, чтобы отобразить список процессов в Linux, вы можете использовать различные команды, такие как ps, top, htop, pidof и другие. Каждая из этих команд имеет свои параметры и опции, которые позволяют фильтровать, сортировать и управлять процессами. Вот несколько примеров:

- `ps` — выводит информацию о выбранных процессах1. Вы можете использовать разные ключи, например, `ps -e` для вывода всех процессов, `ps -u username` для вывода процессов определенного пользователя, `ps -C command` для вывода процессов с определенным именем и т.д.
- `top` — выводит динамически обновляемую информацию о процессах и ресурсах системы. Вы можете нажимать разные клавиши, чтобы изменять режим отображения, например, P для сортировки по использованию ЦП, M для сортировки по использованию памяти, k для убийства процесса по PID и т.д.
- `htop` — улучшенная версия `top`, которая имеет более удобный интерфейс и больше возможностей. Вы можете использовать мышь для выбора и управления процессами, а также нажимать разные клавиши, например, F3 для поиска по процессам, F9 для убийства процесса, F4 для фильтрации по имени и т.д.
- `pidof` — выводит идентификаторы процессов (PID) по имени команды. Например, `pidof sshd` выведет PID всех процессов `sshd`.

## Что такое proc-fs? sys-fs?

proc-fs и sys-fs это две виртуальные файловые системы, которые используются в Linux для предоставления информации о процессах и системных параметрах. Они не хранятся на физическом диске, а генерируются ядром при обращении к ним.

proc-fs обычно монтируется на /proc и содержит каталоги, соответствующие каждому процессу, а также файлы, содержащие общую информацию о системе, такую как версия ядра, загрузка ЦП, память и т.д. proc-fs позволяет получать и изменять различные атрибуты процессов, такие как приоритет, ограничения, сигналы и т.д

sys-fs обычно монтируется на /sys и содержит информацию о доступном оборудовании, драйверах, подсистемах и настройках ядра. sys-fs позволяет управлять некоторыми параметрами ядра, такими как частота ЦП, состояние питания, горячая замена устройств и т.д

Источники: 
- [Habr](https://habr.com/ru/companies/otus/articles/446614/)
- [Wikipedia](https://ru.wikipedia.org/wiki/Procfs)

## Что такое initrd?
Initrd (сокращение от англ. Initial RAM Disk, диск в оперативной памяти для начальной инициализации) — это временная файловая система, которая используется ядром Linux при начальной загрузке. Initrd обычно используется для начальной инициализации перед монтированием «настоящих» файловых систем. Initrd позволяет загружать необходимые модули ядра для работы с дисками, файловыми системами, сетью и другими подсистемами, которые нужны для доступа к корневому разделу.

Initrd может быть создан с помощью различных утилит, таких как mkinitrd, dracut, genkernel и других. Initrd обычно хранится в сжатом виде рядом с ядром и загружается загрузчиком, таким как GRUB, LILO, SYSLINUX и т.д. После загрузки initrd, ядро запускает специальный скрипт, который выполняет необходимые действия для подключения корневого раздела и перехода к нему.

Источники:
- [Wikipedia](https://ru.wikipedia.org/wiki/Initrd)