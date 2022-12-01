---
## Front matter
title: "Лабораторная работа 8"
subtitle: "Команды безусловного и условного переходов в Nasm. Программирование ветвлений."
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
Изучение команд условного и безусловного переходов. Приобретение навыков написания программ с использованием переходов. Знакомство с назначе-нием и структурой файла листинга


# Выполнение лабораторной работы

1) Создаю каталог для программ лабораторной работы No 8, перехожу в него и создаю файл lab8-1.asm (рис. [-@fig:001])

![создание файла](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab08/report/Снимок экрана от 2022-11-29 15-33-00.png){ #fig:001 width=90% }


2) Ввожу в файл lab8-1.asm текст программы из листинга 8.1, создаю исполняемый файл и запускаю его  (рис.[-@fig:002]

![результат создания файла](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab08/report/Снимок экрана от 2022-11-29 15-43-23.png){ #fig:002 width=90% }

3) Изменяю программу таким образом, чтобы она выводила сначала ‘Сообщение No 2’, потом ‘Сообщение No 1’ и завершала работу (рис. [-@fig:003])

![редактирование файла](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab08/report/Снимок экрана от 2022-11-29 15-47-14.png){ #fig:003 }

4) Изменяю текст программы добавив или изменив инструкции jmp, чтобы вывод сообщений был в другом порядке:3,2,1  (рис. [-@fig:004])

![редактирование файла](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab08/report/Снимок экрана от 2022-11-29 15-51-05.png){ #fig:004 width=90% }

5) Создаю файл lab8-2.asm в каталоге ~/work/arch-pc/lab08. Изучаю текст программы из листинга 8.3 и ввожу в lab8-2.asm. Создаю исполняемый файл и проверяю его работу для разных значений B. (рис. [-@fig:005])
![проверка работы программы](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab08/report/Снимок экрана от 2022-11-29 16-00-13.png){ #fig:005 width=90% }

6) Создаю файл листинга для программы из файла lab8-2.asm командой 'nasm -f elf -l lab8-2.lst lab8-2.asm' открываю файл листинга lab8-2.lst с помощью любого текстового редактора, например mcedit 
Содержимое трех строк:

7) Открываю файл с программой lab8-2.asm и в любой инструкции с двумя операндами удаляю один операнд. Выполняю трансляцию с получением файла листинга, после чего вижу, что файл листинга также выдает ошибку (рис. [-@fig:007])

![ошибка в файле листинга](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab08/report/Снимок экрана от 2022-11-29 17-31-43.png){ #fig:007 width=90% }

Самостоятельная работа: 

1)Напишем программу нахождения наименьшей из 3 целочисленных переменных a,b и c. Значения переменных выберем из табл. 8.5 в соответствии с вариантом, полученным при выполнении лабораторной работы No 7.
Создадим исполняемый файл и проверим его работу.В 7 лабораторной работе у меня был 2ой вариант. (рис. [-@fig:008])

![результат работы программы нахождения наименьшей переменной](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab08/report/Снимок экрана от 2022-11-29 17-47-55.png){ #fig:008 width=90% }

2)Напишу программу, которая для введенных с клавиатуры значений x и a вычисляет значение заданной функции и выводит результат вычислений. Создам исполняемый файл и проверю его работу для значений x и a из таблицы 8.6 (рис. [-@fig:009])

![результат работы программы для вычисления заданной функции](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab08/report/Снимок экрана от 2022-11-29 18-23-37.png){ #fig:009 width=90% }


# Выводы

В ходе выполнения данной лабораторной работы я изучил команды условного и безусловного переходов. Приобрел навыки написания программ с использованием переходов. Познакомился с назначением и структурой файла листинга.
