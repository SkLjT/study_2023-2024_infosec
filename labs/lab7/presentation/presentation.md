---
## Front matter
lang: ru-RU
title: Лабораторная работа №7
subtitle: "Элементы криптографии. Однократное гаммирование"
author:
  - Голощапова Ирина Борисовна
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 21 октября 2023

## i18n babel
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

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'
---

# Информация

## Докладчик

:::::::::::::: {.columns align=center}
::: {.column width="70%"}

  * Голощапова Ирина Борисовна
  * студентка уч. группы НФИбд-01-20
  * Российский университет дружбы народов
  * [1032201666@pfur.ru](mailto:1032201666@pfur.ru)
  * <https://github.com/ibgoloshchapowa>

:::
::: {.column width="30%"}



:::
::::::::::::::

# Вводная часть


## Объект и предмет исследования

- Дистрибутив Rocky
- Дискреционное разграничение доступа
- Элементы криптографии
- Однократное гаммирование


## Цели и задачи

Освоить на практике применение режима однократного гаммирования


## Теоретическое введение

Предложенная Г. С. Вернамом так называемая «схема однократного использования (гаммирования)» является простой, но надёжной схемой шифрования данных.
Гаммирование представляет собой наложение (снятие) на открытые (зашифрованные) данные последовательности элементов других данных, полученной с помощью некоторого криптографического алгоритма, для получения зашифрованных (открытых) данных. Иными словами, наложение
гаммы — это сложение её элементов с элементами открытого (закрытого)
текста по некоторому фиксированному модулю, значение которого представляет собой известную часть алгоритма шифрования.

# Выполнение работы

## Условие задачи

Нужно подобрать ключ, чтобы получить сообщение «С Новым Годом,
друзья!». Требуется разработать приложение, позволяющее шифровать и
дешифровать данные в режиме однократного гаммирования. Приложение
должно:

1. Определить вид шифротекста при известном ключе и известном открытом тексте.

2. Определить ключ, с помощью которого шифротекст может быть преобразован в некоторый фрагмент текста, представляющий собой один из
возможных вариантов прочтения открытого текста.


## Программный код

1. Определить вид шифротекста при известном ключе и известном открытом тексте

![функция №1](image/1.png){#fig:01 width=60%}

## Программный код

Вывод функции №1:

![Работа функции №1](image/2.png){#fig:02 width=50%}

## Программный код

2. Определить ключ, с помощью которого шифротекст может быть преобразован в некоторый фрагмент текста, представляющий собой один из возможных вариантов прочтения открытого текста

![функция №2](image/3.png){#fig:03 width=60%}


## Программный код

Вывод функции №2:

![Работа функции №2](image/4.png){#fig:04 width=50%}

## Программный код

3. Сравнение ключей 

![Сравнение ключей](image/5.png){#fig:05 width=50%}



## Вывод


В ходе лабораторной работы мне удалось освоить на практике применение режима однократного гаммирования



