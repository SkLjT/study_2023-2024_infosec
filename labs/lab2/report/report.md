---
## Front matter
title: "Лабораторная работа 2"
subtitle: "Дискреционное разграничение прав в Linux. Основные атрибуты"
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

Получение практических навыков работы в консоли с атрибутами файлов, закрепление теоретических основ дискреционного разграничения доступа в современных системах с открытым кодом на базе ОС Linuх


# Выполнение лабораторной работы

1) Перешёл в учётную запись с правами администратора и создал нового пользователя "guest"

![Создание нового пользователя](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab2/report/image/1.jpg){#fig:001 width=70%}

2) Установил пароль на нового пользователя. 

![Установка пароля](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab2/report/image/2.jpg){#fig:002 width=70%}

3) Перешёл в нового пользователя и с помощью команды "PWD" узнал, где я нахожусь. Потом перешёл в домашнюю директорию с помощью команды "cd".

![Домашняя директория](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab2/report/image/3.jpg){#fig:003 width=70%}

4) С помощью команды "whoami" уточнил имя пользователя 

![Имя пользователя](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab2/report/image/4.jpg){#fig:004 width=70%}

5) Уточнил имя пользователя, группу и группу, куда входит пользователь. Сравнил данные, имя пользователя везде одинаковое.

![Команда id](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab2/report/image/5.jpg){#fig:005 width=70%}

6) С помощью команды "cat /etc/passwd" нашёл своего пользователя. Затем ввёл команду "cat /etc/passwd | grep guest", чтобы получить именно строку с моим именем.

![Поиск с помощью сat](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab2/report/image/6.jpg){#fig:006 width=70%}

![Поиск с уточнением](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab2/report/image/7.jpg){#fig:007 width=70%}

7) С помощью команды "ls -l /home/" определил директории, которые находится с папке home. На каждой из директорий установлены все права для владельца директории. 

![Определение директорий](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab2/report/image/8.jpg){#fig:008 width=70%}

8) Я проверил какие расширенные атрибуты установлены в поддерикториях с помощью команды "lsattr /home". Прочитать атрибуты для директории, которая относится к пользователю "aalushin" я не смог, но атрибуты директории "guest" у меня вывелись. 

![Определение расширенных атрибутов](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab2/report/image/9.jpg){#fig:009 width=70%}

9) Я перешел в домашнюю директорию и создал папку "dir1". С помощью команды "ls -l" и "lsattr" определил, какие права и расширения атрибутов стоят для папки. Папка имеет практически все права, но нет атрибутов.

![Анализ новой папки](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab2/report/image/11.jpg){#fig:010 width=70%}

10) С помощью команды "chmod 000 dir1" я снял все права с папки.

![Снятие прав](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab2/report/image/12.jpg){#fig:011 width=70%}

11) Я попытался создать файл внутри директории, но мне выдало ошибку. ИЗ-за того, что я забрал все права, включая права на создание файлов, я не могу создать файл внутри этой папки. Так же я забрал и права на просмотр, то есть я не могу посмотреть содержимое папки. 

![Проверка прав](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab2/report/image/13.jpg){#fig:012 width=70%}

12) Я заполнил таблицу "Установленные права и разрешенные действия". Все ответы определил опытным путём, то есть проверил. В данной таблици я рассмотрел всего 64 возможных варианта. На самом деле их больше, но в задании необходимо рассмотреть всего 64 варианта. В таблице зелёным + отмечено то, что возможно делать, при выдаче определённых прав на папку и файл. А красным - отмечено то, что нельзя сделать при определённых правах.

![Составление первой таблицы](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab2/report/image/14.jpg){#fig:013 width=70%}

13) Основываясь на первой таблице, я заполнил вторую таблицу "Минимальные права для совершения операции". То есть для выполнения каждого действия я вписал минимальные права, которые необходимы для директории и файла. В таблице "ООО" означает, как 000, то есть права со всеми нулями. 

![Составление второй таблицы](/home/aalushin/work/study/study_2023-2024_infosec/labs/lab2/report/image/15.jpg){#fig:014 width=70%}

# Выводы

Я получил практические навыки работы в консоли с атрибутами файлов. Так же закрепил теоретическую основу дискреционного разграничения доступа в современных системах с открытым кодом на базе ОС Linux


:::
