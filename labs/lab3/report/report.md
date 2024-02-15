---
## Front matter
title: "Лабораторная работа 3"
subtitle: "Дискреционное разграничение прав в Linux. Два пользователя"
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

Получение практических навыков работы в консоли с атрибутами файлов для групп пользователей


# Выполнение лабораторной работы

1) Я создал нового пользователя "guest" и создал к нему пароль. Для создания использовал права администратора.

![Создание guest](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab3/report/image/1.jpg){#fig:001 width=70%}

2) Затем я создал и второго пользователя "guest2" и добавил пароль. Для создания так же использовали права администратора.

![Создание guest2](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab3/report/image/2.jpg){#fig:002 width=70%}

3) Добавил пользователя "guest2" в группу "guest".

![Добавление в группу](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab3/report/image/3.jpg){#fig:003 width=70%}

4) Я осуществил вход на первой консоли на аккаунт "guest". А на второй консоли зашел на аккаунт "guest2"

![Вход на guest](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab3/report/image/4.jpg){#fig:004 width=70%}

![Вход на guest2](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab3/report/image/5.jpg){#fig:005 width=70%}

5) Я уточнил на двух аккаунтах имя пользователя, группу, кто входит в группу и к каким группам принадлежит сам пользователь.

![Информация о guest](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab3/report/image/6.jpg){#fig:006 width=70%}

![Информация о guest2](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab3/report/image/7.jpg){#fig:007 width=70%}

6) Я сравнил полученную информацию с содержимым файла /etc/group. Информацию совпала.

![Сравнение ланных](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab3/report/image/8.jpg){#fig:008 width=70%}

7) От имени пользователя "guest2" я выполнил регистрацию в группе "guest".

![Регистрация в группе](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab3/report/image/9.jpg){#fig:009 width=70%}

8) Используя аккаунт "guest" я изменил права директории "/home/guest" разрешив все действия для пользователей группы.

![Изменение прав директории](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab3/report/image/10.jpg){#fig:010 width=70%}

9) С аккаунта "guest" я снял все атрибуты с папки "dir1", которая находится по адресу "/home/guest/dir1"

![Изменение прав папки dir1](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab3/report/image/11.jpg){#fig:011 width=70%}

10) Я заполнил таблицу "Установленные права и разрешения действия для групп". Ответы заполнял, основываясь на личном опыте и проверке файлов. В таблице есть несколько столбцов: создание файла, удаление файла, запись файла, смена директории, просмотр файла в директории, смена атрибутов директории. И строк с определёнными разрешениями для файла и директории. Всего 64 возможных варианта. В таблице красным "-" отмечена ячейка, которая не выполняется при определённых правах. А зеленым "+" отмечены те функции, которые могут выполняться. 

![Таблица 1](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab3/report/image/12.jpg){#fig:012 width=70%}

11) Я заполнил таблицу "Минимальные права для совершения операция от имени пользователей входящих в группу". Для заполнения таблицы использовал данные, которые внёс в таблицу 1. На пересечении определённых столбцов и строк стоят минимальные права, которые необходимы для выполнения данной функции.

![Таблица 2](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab3/report/image/13.jpg){#fig:012 width=70%}


# Выводы

Я получил практические навыки работы в консоли с атрибутами файлов для групп пользователей. 


