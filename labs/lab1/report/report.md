---
# Front matter
lang: ru-RU
title: "Отчёт по лабораторной работе №1"
subtitle: "Установка и конфигурация операционной системы на виртуальную машину. Управление версиями"
author: "Голощапова Ирина Борисовна"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
polyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: lualatex
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цели и задачи лабораторной работы

## Цель работы

Приобретение практических навыков
установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов.

## Задачи работы

- Установить операционную систему на виртуальную машину
- Изучить идеологию и применение средств контроля версий.
- Освоить умения по работе с git.





# Выполнение лабораторной работы


## Установка дистрибутива Rocky

1. Открыла у себя на компьютере установленную заранее VirtualBox и создала новую виртуальную машину Rocky (рис. @fig:01):


![Имя и операционная система вм](image/1.png){#fig:01 width=50%}


![Виртуальный жесткий диск](image/2.png){#fig:02 width=50%}


![Итоговая конфигурация для вм](image/3.png){#fig:03 width=50%}


2. Зашла в настройки созданной новой виртуальной машины и добавила заранее установленный оптический диск (рис. @fig:04):

![Добавление оптического диска](image/4.png){#fig:04 width=50%}


3. Запустила созданную виртуальную машину и применила следующие настройки (рис. @fig:05):


![Установка языка](image/5.png){#fig:05 width=50%}

![Выбор программ](image/6.png){#fig:06 width=50%}


![Подключение сети и добавление имени узла](image/7.png){#fig:07 width=50%}


![Создание пароля root](image/8.png){#fig:08 width=50%}


4. Перезупустила систему для корректной установки.

5. Указала свое полное имя и имя пользователя (рис. @fig:09):

![Имя пользователя](image/9.png){#fig:09 width=50%}


6. Подключила образ диска дополнений гостевой ОС (рис. @fig:10):

![Образ диска дополнений гостевой ОС](image/10.png){#fig:10 width=50%}


![Загрузка образа диска дополнений гостевой ОС](image/11.png){#fig:11 width=50%}



7. Проверила на корректность имя хоста (рис. @fig:12):

![Имя хоста](image/12.png){#fig:12 width=50%}


8. При помощи команды **dmesg | grep -i "то, что ищем"** получила следующие сведения: 

- версия ядра (рис. @fig:13):


![Версия ядра](image/13.png){#fig:13 width=50%}


- частота процессора (рис. @fig:14):

![частота процессора](image/14.png){#fig:14 width=50%}

- модель процессора (рис. @fig:15):

![модель процессора](image/15.png){#fig:15 width=50%}

- объем доступной оперативной памяти (рис. @fig:16):

![объем доступной оперативной памяти](image/16.png){#fig:16 width=50%}

- тип обнаруженного гипервизора (рис. @fig:17):

![тип обнаруженного гипервизора](image/17.png){#fig:17 width=50%}

- тип файловой системы корневого раздела (рис. @fig:18):


![тип файловой системы корневого раздела](image/18.png){#fig:18 width=50%}

- последовательность монтирования файловых систем (рис. @fig:19):

![последовательность монтирования файловых систем](image/19.png){#fig:19 width=50%}








## Настройка git

1. Задала имя и email владельца репозитория (рис. @fig:20):


![Задание имени и email владельца репозитория](image/20.png){#fig:20 width=50%}

2. Настроила utf-8 в выводе сообщений git (рис. @fig:21):

![Настройка utf-8](image/21.png){#fig:21 width=50%}

3. Настроила верификацию и подписание коммитов git. Задала имя начальной ветки (будем называть её master) (рис. @fig:22):

![Задание начальной ветки](image/22.png){#fig:22 width=50%}


4. Параметр autocrlf, Параметр safecrlf (рис. @fig:23):

![Параметр autocrlf, Параметр safecrlf](image/23.png){#fig:23 width=50%}

## Создание ключей

5. Добавление ssh ключей (рис. @fig:24):

![Добавление ssh ключей](image/24.png){#fig:24 width=50%}


![Добавление ssh ключей (2)](image/25.png){#fig:25 width=50%}



6. Добавление gpg ключей (рис. @fig:26):

![Добавление gpg ключей](image/26.png){#fig:26 width=50%}


![Добавление gpg ключей (2)](image/27.png){#fig:27 width=50%}




## Настройка автоматических подписей коммитов git

7. Настроила автоматические подписи (рис. @fig:28):

![Настройка автоматических подписей коммитов git](image/28.png){#fig:28 width=50%}



## Настройка gh

8. Прошла авторизацию  (рис. @fig:29): 


![Авторизация на гит](image/29.png){#fig:29 width=50%}


![Авторизация на гит](image/30.png){#fig:30 width=50%}



## Создание репозитория курса

7. Создала репозиторий согласно шаблону  (рис. @fig:31): 


![Создание репозитория](image/31.png){#fig:31 width=50%}

![Создание репозитория (2)](image/32.png){#fig:32 width=50%}





## Настройка каталога курса

8. Перешла в каталог курса, удалила ненужные файлы, создала необходимые каталоги и отправила файлы на сервер  (рис. @fig:33): 

![Настройка каталога курса](image/33.png){#fig:33 width=50%}


# Выводы

В ходе лабораторной работы нам удалось:

- Установить операционную систему на виртуальную машину.

- Изучить идеологию и применение средств контроля версий.

- Освоить умения по работе с git.




# Ответы на вопросы

1. Какую информацию содержит учётная запись пользователя?

Учётная запись пользователя - это запись, которая содержит сведения, необходимые для 
идентификации пользователя при подключении к системе, а также информацию для 
авторизации и учёта. Это имя пользователя и пароль

2. . Укажите команды терминала и приведите примеры:

– для получения справки по команде: «имя программы --help»

– для просмотра содержимого каталога: «ls -l»

– для определения объёма каталога: «du имя_папки»

– для создания / удаления каталогов / файлов: создание - «mkdir», удаление - «rm» 

или для рекурсивного удаления – «rm -r»

– для задания определённых прав на файл / каталог: изменение расширения 
доступа - «chmod разрешение имя_файла»; смена владельца – «chown
новый_владелец имя_файла»

– для просмотра истории команд: «history»


3. Что такое файловая система? Приведите примеры с краткой характеристикой. 

Фа́йловая систе́ма (англ. file system) — порядок, определяющий способ организации, хранения и именования данных на носителях информации в компьютерах, а также в другом электронном оборудовании: цифровых фотоаппаратах, мобильных 
телефонах и т. п.

- Для носителей с произвольным доступом (например, жёсткий 
диск): FAT32, HPFS, ext2 и др. Поскольку доступ к дискам в несколько раз медленнее, чем доступ к оперативной памяти, для прироста производительности во многих файловых системах применяется асинхронная запись изменений на диск. 
Для этого применяется либо журналирование, например, 
в ext3, ReiserFS, JFS, NTFS, XFS, либо механизм soft updates и др. Журналирование 
широко распространено в Linux, применяется в NTFS. Soft updates — в BSD 
системах.
- Для носителей с последовательным доступом (например, магнитные ленты): QIC и 
др.
- Для оптических носителей — CD и DVD: ISO9660, HFS, UDF и др.
- Виртуальные файловые системы: AEFS и др.
- Сетевые файловые системы: NFS, CIFS, SSHFS, GmailFS и др.
- Для флэш-памяти: YAFFS, ExtremeFFS, exFAT


4. Как посмотреть, какие файловые системы подмонтированы в ОС?

**$ findmnt --mtab**



# Библиография
1. [Git - система контроля версий](https://github.com/)

2. [Rocky Linux](https://rockylinux.org/)
