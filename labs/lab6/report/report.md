---
## Front matter
title: "Лабораторная работа 6"
subtitle: "Мандатное разграничение прав в Linux "
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
biblatex: true
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

Развить навыки администрирования ОС Linux. Получить первое практическое знакомство с технологией SELinux1. Проверить работу SELinx на практике совместно с веб-сервером Apache.



# Выполнение лабораторной работы

1) Я проверил в каком режиме работает SELinux. Режим - Enforcing, а политика - targeted. 

![Проверка режима и политики](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab6/report/image/1.jpg){#fig:001 width=70%}

2) Проверил статус браузера к веб-серверу, который запущен на компьютере. Статус - active.

![Проверка статуса](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab6/report/image/2.jpg){#fig:006 width=70%}

3) Я определил контекст безопасности веб-сервера Apache. Контекст - httpd_t.

![Определение контекста безопасности](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab6/report/image/3.jpg){#fig:003 width=70%}

4) Посмотрел текущее состояние переключателей SELinux для Apache. Большая часть переключателей выключены.

![Проверка переключателей](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab6/report/image/4.jpg){#fig:004 width=70%}

5) Посмотрел статистику по политике. Пользователей - 8, ролей - 15, а типов - 5135.

![Статистика политики](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab6/report/image/5.jpg){#fig:005 width=70%}

6) Определил тип файлов, которые находятся в директории "/var/www/html". Все файлы созданы и относятся к пользователю root. Владельцем так же является пользователь root.

![Тип файлов html](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab6/report/image/6.jpg){#fig:006 width=70%}

7) От имени суперпользователя создал файл "test.html" в директории "/var/www/html". Вписал туда необходимый текст, чтобы потом проверить его на сайте. А контекст для новых файлов - httpd_sys_content_t.

![Создание файла](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab6/report/image/7.jpg){#fig:007 width=70%}

8) Я ввёл в браузере ссылку "http://127.0.0.1/test.html". Файл успешно отобразился и на сайте показали такой же текст, как и в файле.

![Отображение на сайте](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab6/report/image/8.jpg){#fig:008 width=70%}

9) Я изучил справку "man httpd_selinux". Для httpd определены следующие контексты: httpd_sys_conten_t, httpd_sys_script_exec_t, httpd_sys_script_ro_t, httpd_sys_script_rw_t, httpd_sys_script_ra_t, httpd_unconfined_script_exec_t. Я изменил контекст моего файла на "samba_share_t и провели, чтобы контекст установился.

![Смена контекста](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab6/report/image/9.jpg){#fig:009 width=70%}

10) Я попытался подключиться к файлу на сайте, но выдало ошибку. Связано это с тем, что httpd не имеет доступа к тому контексту, который я установил.

![Проверка нового контекста](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab6/report/image/10.jpg){#fig:010 width=70%}

11) Я убедился, что есть права доступа на чтение, но ошибка появляется из-за того, что сам httpd не может распознать контекст. Так же просмотрел системный лог-файл веб-сервера Apache и увидел, что он отображает ошибки.

![Проверка лог-файла](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab6/report/image/11.jpg){#fig:011 width=70%}

12) В файле "/etc/httpd/conf/httpd.conf" изменил TCP-порт на 81, а не на 80, как рекомендована IANA.

![Изменение порта на 81](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab6/report/image/12.jpg){#fig:012 width=70%}

13) Я перезапустил сервер и проанализировал лог-файл.

![Перезапуск сервера](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab6/report/image/13.jpg){#fig:013 width=70%}

14) Я просмотрел файлы "/var/log/http/error_log", "/var/log/http/access_log" и "/var/log/audit/audit.log". Изменения произошли в audit файле.

![Проверка файлов](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab6/report/image/14.jpg){#fig:014 width=70%}

15) Я выполнил команду для смены портов и затем проверил список портов, чтобы убедиться, что появился 81 порт.

![Смена портов](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab6/report/image/15jpg){#fig:015 width=70%}

16) Я перезапустил веб-сервер и он запустился. Произошло это из-за того, что я добавил порт, которого до этого не было. 

![Перезапуск веб-сервера с добавленным портом](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab6/report/image/16.jpg){#fig:016 width=70%}

17) Я вернул изначальный контекст файлу "text.html" и убедился в этом. 

![Возвращение контекста](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab6/report/image/17.jpg){#fig:017 width=70%}

18) Попробовал зайти на веб-сервер, чтобы убедиться в том, что файл читается. Веб-сервер подключился и вывел текст "test", как и в самом файле. Даже не смотря на то, что я поменял порт, веб-сервер запустился. 

![Проверка веб-сервера с новым портом](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab6/report/image/18.jpg){#fig:018 width=70%}

19) Я исправил в конфигурационном файле 80 порт. Попытался вообще удалить привязку 81 порта, но этого нельзя сделать, так как не разрешает политика. Но тем не менее, теперь в конфигурационном файле стоит 80 порт и в списке портов он есть. 

![Возвращение старого порта](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab6/report/image/19.jpg){#fig:019 width=70%}

20) Чтобы в дальнейшем мне не мешались тестовые файлы, я удалил все файлы, с которым работал в директории "var/www/html".

![Удаление файлов](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab6/report/image/20.jpg){#fig:020 width=70%}



# Выводы

Я развил навыки администрирования ОС Linux. Получил первое практическое знакомство с технологией SELinux. Проверил работу SELinux на практике совместно с веб-сервером Apache.
