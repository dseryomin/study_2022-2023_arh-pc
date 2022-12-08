---
## Front matter
title: "Лабораторная работа 9"
subtitle: "Программирование цикла. Обработка аргументов командной строки."
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
lot: true # List of tables
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
Приобретение навыков написания программ с использованием циклов и обработкой аргументов командной строки

# Выполнение лабораторной работы

1)Создаю каталог для лабораторной работы No 9, перехожу в него и создаю файл lab9-1.asm (рис. [-@fig:001]).

![Создание каталога и файла](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab09/report/Снимок экрана от 2022-12-01 13-59-32.png){ #fig:001 width=90% }

2) Ввожу в файл lab9-1.asm текст программы из листинга 9.1., Создаю исполняемый файл и проверяю его работу (рис. [-@fig:002]).

![проверка работы программы из листинга](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab09/report/Снимок экрана от 2022-12-01 14-15-22.png){ #fig:002 width=90% }

3)  Изменяю текст программы, добавив изменение значения регистра ecx в цикле (рис. [-@fig:003]).

![проверка работы измененной программы](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab09/report/Снимок экрана от 2022-12-01 14-17-03.png){ #fig:003 width=90% }

4) Вношу изменения в текст программы, добавив команды push и pop для сохранения значения счетчика цикла loop (рис. [-@fig:004]).

![Создание файла](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab09/report/Снимок экрана от 2022-12-01 14-17-51.png){ #fig:004 width=90% }

5) Создаю файл lab9-2.asm в каталоге ~/work/arch-pc/lab09 и ввожу в него текст программы из листинга 9.2,cоздаю исполняемый файл и запускаю его, указав аргументы (рис. [-@fig:005]).

![проверка работы программы из листинга 9.2](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab09/report/Снимок экрана от 2022-12-01 14-43-56.png){ #fig:005 width=90% }


6) Создаю файл lab9-3.asm в каталоге ~/work/arch-pc/lab09 и ввожу в него текст программы из листинга 9.3., создаю исполняемый файл и запускаю его, указав аргументы (рис. [-@fig:006]).

![результат работы программы из листинга 9.3](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab09/report/Снимок экрана от 2022-12-01 14-47-34.png){ #fig:006 width=90% }

7) Изменяю текст программы из листинга 9.3 для вычисления произведения аргументов командной строки (рис. [-@fig:007]).

![результат работы программы для вычисления произведения аргументов](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab09/report/Снимок экрана от 2022-12-08 11-39-20.png){ #fig:007 width=90% }

Самостоятельная работы:
 
Напишем программу, которая находит сумму значений функции для разных переменных. Значения x передаются как аргументы. У меня второй вариант. Создаём исполняемый файл и проверяем его работу на 2 переменных (рис. [-@fig:008]).

![результат работы программы для вычисления функции](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab09/report/Снимок экрана от 2022-12-08 13-45-35.png){ #fig:008 width=90% }




# Выводы

В ходе выполнения данной лабораторной работы я приобрёл навыки написания программ с использованием циклов и обработкой аргументов командной строки.
