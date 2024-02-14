---
## Front matter
title: "Лабораторная работа 1"
subtitle: "Установка и конфигурация операционной системы на виртуальную машину"
author: "Лушин Артём Андреевич"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: false
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Приобретение практических навыков установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов. 

# Задание

Здесь приводится описание задания в соответствии с рекомендациями
методического пособия и выданным вариантом.

# Теоретическое введение


Лабораторная работа подразумевает установку на виртуальную машину
VirtualBox (https://www.virtualbox.org/) операционной системы Linux
(дистрибутив Rocky (https://rockylinux.org/)).

Выполнение работы возможно как в дисплейном классе факультета
физико-математических и естественных наук РУДН, так и дома. Описание
выполнения работы приведено для дисплейного класса со следующими характеристиками:

– Intel Core i3-550 3.2 GHz, 4 GB оперативной памяти, 20 GB свободного
места на жёстком диске;

– ОС Linux Gentoo (http://www.gentoo.ru/);

– VirtualBox верс. 6.1 или старше;

– каталог с образами ОС для работающих в ди

# Выполнение лабораторной работы

1) Я создал новую виртуальную машину с именем "4sem" и установил тип Linux (сделал фотографию раньше, чем поставил тип"

![Имя машины и тип ОС](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab1/report/image/1.jpg){#fig:001 width=70%}

2) Далее я выделил 11086МБ основной памяти и 10 процессоров. 

![Выделение основной памяти и процессоров](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab1/report/image/2.jpg){#fig:002 width=70%}

3) Создал новый виртуальный жёсткий диск и выделил на него 110 Гигабайт. В новой версии VirtualBox нет возможности указать тип диска и он ставится автоматически.

![Создание виртуального жёсткого диска](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab1/report/image/3.jpg){#fig:003 width=70%}

4) Запустил виртуальную машину и поставил в качестве языка интерфейса - Английский (United States) 

![Установка языка интерфейся](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab1/report/image/4.jpg){#fig:004 width=70%}

5) В окне выбора программ поставил базовое оборудование - Server with GUI, а в разделе Development Tools.

![Окно Настройки установки программ](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab1/report/image/5.jpg){#fig:005 width=70%}

6) В следующем окне отключить функцию KDUMP, убрав галочку. 

![Отключение KDUMР](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab1/report/image/6.jpg){#fig:006 width=70%}

7) В разделе сети установил сеть и задал имя узла "aalushin.localdomin" (скриншот сделан до переименования)

![Сеть и имя узла](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab1/report/image/7.jpg){#fig:007 width=70%}

8) Установил москвоское время. Регион - Европа, город - Москва. 

![Установка времени](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab1/report/image/8.jpg){#fig:008 width=70%}

9) В качестве раскладки клавиатуры поставил английскую, а затем русскую. То есть при входе автоматически включается английская раскладка, при необходимости переключается на русскую. 

![Раскладка клавиатуры](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab1/report/image/9.jpg){#fig:009 width=70%}

10) После всех действия установил пароль для root-пользователя. 

![Пароль для root](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab1/report/image/10.jpg){#fig:010 width=70%}

11) Создал пользователя. Имя пользователя такое же, как в дисплейных классах. Добавил пользователю возможность администратора. 

![Создание пользователя](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab1/report/image/11.jpg){#fig:011 width=70%}

12) После установки и ввода всех данных начинаю загрузку образа.

![Установка образа](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab1/report/image/12.jpg){#fig:012 width=70%}

# Домашнее задание

1) С помощью команды "dmesg" нашел информацию о версии ядра Linux

![Версия ядра Linux](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab1/report/image/13.png){#fig:013 width=70%}

2) С помощью команды "dmesg" нашел информацию о частоте процессора

![Частота процессора](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab1/report/image/14.jpg){#fig:014 width=70%}

3) С помощью команды "dmesg" нашел информацию о моделе процессора

![Модель процессора](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab1/report/image/15.jpg){#fig:015 width=70%}

4) С помощью команды "dmesg" нашел информацию об объёме доступной оперативной памяти. Максимальная оперативная память равно 131072 килобайта.

![Объём оперативной памяти](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab1/report/image/16.jpg){#fig:016 width=70%}

5) С помощью команды "dmesg" определил тип обнаруженного тепловизора

![Обнаруженный тепловизор](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab1/report/image/17.jpg){#fig:017 width=70%}

6) С помощью команды "dmesg" определил тип файловой системы корневого раздела. Так же аналогично можно узнать тип файловых систем с помощью команды "df -T" и под словом "Type" написан тип. В моём случае это - xfs.

![Тип файловых систем](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab1/report/image/19.jpg){#fig:019 width=70%}

![Тип файловых систем с помощью df](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab1/report/image/20.jpg){#fig:020 width=70%}

7) С помощью команды "dmesg" определил последовательность монтирования файловых систем.

![Последовательность монтирования файловых систем](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab1/report/image/18.jpg){#fig:018 width=70%}

![](){#fig:01 width=70%}

# Выводы

Я приобрёл практические навыки установки операционной системы на виртуальную машину. Настроил минимально необходимые для дальнейшей работы сервисы

# Контрольные вопросы

1) Какую информацию содержит учётная запись пользователя? 

Учётная запись пользователя - это запись, которая содержит сведения, необходимые для идентификации пользователя при подключении к системе, а также информацию для авторизации и учёта. Это имя пользователя и пароль

2) Укажите команды терминала и приведите пример 

- для получения справки по команде: имя программы --help. dmesg --help

- для перемещения по файловой системе: cd путь. cd work

- для просмотра содержимого каталога: ls - l. ls work

- для определения объёма каталога du имя_папки. du work

- для создания / удаления каталогов / файлов: создание каталога - mkdir, удаление файла или каталога - rm -r, создание файла - touch

- для создания определённых прав на файл/каталог: chmod разрешение имя_файла. chown новый_владелец - для смены владельца

- для просмотра историй команд: history

3) Что такое файловая система? Приведите пример с краткой характеристикой. 

Фа́йловая систе́ма (англ. file system) — порядок, определяющий способ организации, хранения и именования данных на носителях информации в компьютерах, а также в другом электронном оборудовании: цифровых фотоаппаратах, мобильных телефонах и т. п.

• Для носителей с произвольным доступом (например, жёсткий диск): FAT32, HPFS, ext2 и др. Поскольку доступ к дискам в несколько раз медленнее, чем доступ к оперативной памяти, для прироста производительности во многих файловых системах применяется асинхронная запись изменений на диск. Для этого применяется либо журналирование, например, в ext3, ReiserFS, JFS, NTFS, XFS, либо механизм soft updates и др. Журналирование широко распространено в Linux, применяется в NTFS. Soft updates — в BSD системах.

• Для носителей с последовательным доступом (например, магнитные ленты): QIC и др.

• Для оптических носителей — CD и DVD: ISO9660, HFS, UDF и др.

• Виртуальные файловые системы: AEFS и др.

• Сетевые файловые системы: NFS, CIFS, SSHFS, GmailFS и др.

• Для флэш-памяти: YAFFS, ExtremeFFS, exFAT

4) Как посмотреть, какие файловые системы подмонтированы в ОС?

$ findmnt –mtab

5) Как удалить зависший процесс?

команды: kill, pgrep, pkill, killall

