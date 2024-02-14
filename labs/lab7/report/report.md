---
# Front matter
lang: ru-RU
title: "Отчёт по лабораторной работе №7"
subtitle: "Элементы криптографии. Однократное гаммирование"
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

## Цель

Освоить на практике применение режима однократного гаммирования

# Теоретическое введение


Предложенная Г. С. Вернамом так называемая «схема однократного использования (гаммирования)» является простой, но надёжной схемой шифрования данных.
Гаммирование представляет собой наложение (снятие) на открытые (зашифрованные) данные последовательности элементов других данных, полученной с помощью некоторого криптографического алгоритма, для получения зашифрованных (открытых) данных. Иными словами, наложение
гаммы — это сложение её элементов с элементами открытого (закрытого)
текста по некоторому фиксированному модулю, значение которого представляет собой известную часть алгоритма шифрования.


# Выполнение лабораторной работы


1. Создала программу на языке Python, которая позволяет шифровать и
дешифровать данные в режиме однократного гаммирования.

В программе реализован следующий функционал:
1. Определить вид шифротекста при известном ключе и известном открытом тексте (рис. @fig:01)

![Определить вид шифротекста при известном ключе и известном открытом тексте](image/1.png){#fig:01 width=50%}


Для проверки работы функции передадим входную строку и получим данный текст в 16-ой СС, сгенерированный ключ в 16-ой СС, зашифрованный текст (рис. @fig:02)


![Работа функции 1](image/2.png){#fig:02 width=50%}


2. Определить ключ, с помощью которого шифротекст может быть преобразован в некоторый фрагмент текста, представляющий собой один из возможных вариантов прочтения открытого текста (рис. @fig:03)


![Определение ключа](image/3.png){#fig:03 width=50%}


Вывод программы (рис. @fig:04):

![Работа функции 2](image/4.png){#fig:04 width=50%}


3. Сравнение ключей (рис. @fig:05):

![Сравнение ключей](image/5.png){#fig:05 width=50%}




# Выводы

В ходе лабораторной работы мне удалось освоить на практике применение режима однократного гаммирования





# Библиография
1. [Git - система контроля версий](https://github.com/)

2. [Rocky Linux](https://rockylinux.org/)

3. [Элементы криптографии](https://studopedia.su/10_105527_elementi-kriptografii.html)

4. [Однократное гаммирование](https://bugtraq.ru/library/books/crypto/chapter7/)
