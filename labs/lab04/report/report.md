---
## Front matter
title: "Лабораторная работа 4"
subtitle: "Язык разметки Markdown"
author: "Ерёмин Даниил"

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
lot: false # List of tables
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
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Целью работы является освоение процедуры оформления отчетов с помощью
легковесного языка разметки Markdown.

# Задание

Здесь приводится описание задания в соответствии с рекомендациями
методического пособия и выданным вариантом.

# Теоретическое введение

Язык разметки Markdown является "легковесным", при чем данный термин обязательно подлежит заключению в кавычки

# Выполнение лабораторной работы

1) С помощью терминала перехожу в каталог курса, сформированный при выполнении лабораторной работы 3,после чего обновляю локальный репозиторий, скачав изменения из удаленного репозитория (рис. [-@fig:001])

![Результат работы команды `git pull`](image/Снимок экрана от 2022-10-27 11-12-53.png){ #fig:001 width=90% }


2) Перехожу в каталог с отчетом по лабораторной работе 4 и провожу компиляцию шаблона с использованием Makefile (рис.[-@fig:002]

![Компиляция шаблона с использованием Makefile](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab04/report/image/Снимок экрана от 2022-10-27 11-26-28.png){ #fig:002 width=90% }

3) Проверяю корректность полученных файлов (рис. [-@fig:003])

![Результат работы команды 'make'](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab04/report/image/Снимок экрана от 2022-10-27 11-29-17.png){ #fig:003 }

4) Удаляю полученные файлы с помощью Makefile (рис. [-@fig:004])

![Удаление файлов с помощью Makefile](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab04/report/image/Снимок экрана от 2022-10-27 11-32-16.png){ #fig:004 width=90% }

5)Проверяю, что файлы были удалены, после чего приступаю к оформлению отчета в gedit (рис. [-@fig:005])
![Проверка отсутствия удаленных файлов](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab04/report/image/Снимок экрана от 2022-10-27 11-31-33.png){ #fig:005 width=90% }

# Выводы

В ходе лабораторной работы я освоил процедуры оформления отчетов с помощью легковесного языка разметки Markdown.

