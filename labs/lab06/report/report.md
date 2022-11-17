---
## Front matter
title: "Лабораторная работа 6"
subtitle: "Основы работы с
Midnight Commander (mc). Структура
программы на языке ассемблера NASM.
Системные вызовы в ОС GNU Linux"
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
Освоение процедуры компиляции и сборки программ, написанных на ассем-
блере NASM


# Выполнение лабораторной работы

1)С помощью команды 'mc' запускаю Midnight Commander, после чего перехожу в каталог ~/work/arch-pc (рис. [-@fig:001])

![запуск окна Midnight Commander](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab06/report/Снимок экрана от 2022-11-17 10-49-49.png){ #fig:001 width=90% }


2) Пользуясь строкой ввода и командой touch создаю файл lab6-1.asm в папке lab06, созданной мной клавишей f7  (рис.[-@fig:002]

![созданный файл](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab06/report/Снимок экрана от 2022-11-17 10-49-59.png){ #fig:002 width=90% }

3) С помощью клавиши f4 редактирую созданный файл, вводя в него текст из листинга 6.1 (рис. [-@fig:003])

![редактирование файла](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab06/report/Снимок экрана от 2022-11-17 10-57-22.png){ #fig:003 }

4) Убеждаюсь, что файл содержит текст программы с помощью клавиши f3  (рис. [-@fig:004])

![проверка текста программы](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/arch-pc/lab05/Снимок экрана от 2022-11-10 11-28-04.png){ #fig:004 width=90% }

5) Транслирую текст программы lab6-1.asm в объектный файл. Выполняю компоновку объектного файла и запускаю получившийся исполняемый файл (рис. [-@fig:005])
![компоновка программного файла и его запуск](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab06/report/Снимок экрана от 2022-11-17 11-05-51.png){ #fig:005 width=90% }

6) передаю объектный файл на обработку компоновщику с помощью команды d -m elf_i386 hello.o -o hello,на предыдущем скриншоте видно, что исполняемый файл был создан; после чего выполняю команду 'ld -m elf_i386 obj.o -o main' (рис. [-@fig:006]) 
 
![обработка файлов компоновщиком LD](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/arch-pc/lab05/Снимок экрана от 2022-11-10 11-34-46.png){ #fig:006 width=90% }

7) копирую файл in_out.asm в каталог с файлом lab6-1.asm с помощью функциональной клавиши f5 (рис. [-@fig:007])

![копирование файла в другой каталог](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab06/report/Снимок экрана от 2022-11-17 11-12-51.png){ #fig:007 width=90% }

8) с помощью клавиши f6 создаю копию файла lab6-1.asm с именем lab6-2.asm (рис. [-@fig:008])

![создание копии файла](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab06/report/Снимок экрана от 2022-11-17 11-15-30.png){ #fig:008 width=90% }

9) Исправляю текст программы в файле lab6-2.asm с использование подпрограмм из внешнего файла in_out.asm (используя подпрограммы sprintLF, sread и quit) в соответствии с листингом 6.2. После этого создаю исполняемый файл и выполняю работу. (рис. [-@fig:009])

![корректировка текста программы](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab06/report/Снимок экрана от 2022-11-17 12-40-15.png){ #fig:009 width=90% }

10) В файле lab6-2.asm заменяю подпрограмму sprintLF на sprint. Создаю исполняемый файл и проверяю его работу. (рис. [-@fig:010])

![замена подпрограммы sprintLF на sprint](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab06/report/Снимок экрана от 2022-11-17 12-42-48.png){ #fig:010 width=90% }

![запуск программного файла](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab06/report/Снимок экрана от 2022-11-17 12-47-34.png){ #fig:011 width=90% }

Задание для самостоятельной работы:

1) Исправляю текст программы с использованием подпрограмм из внешнего файла in_out.asm, так чтобы она работала по следующему алгоритму:
• вывести приглашение типа “Введите строку:”;
• ввести строку с клавиатуры;
• вывести введённую строку на экран. 
 (рис. [-@fig:012])
 
![корректировка текста программы с импользованием подпрограмм](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab06/report/Снимок экрана от 2022-11-17 13-44-55.png){ #fig:012 width=90% }

2) создаю исполняемый файл и проверяю его работу (рис. [-@fig:013])

![создание исполняемого файла](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab06/report/Снимок экрана от 2022-11-17 13-44-55.png){ #fig:013 width=90% }

3)Делаю тоже самое с файлом lab6-1, но без использования подпрограмм из внешнего файла in_out.asm


# Выводы

В ходе выполнения данной лабораторной работы я приобрел практические навыки работы в Midnight Commander,а также я освоил инструкцию языка ассемблера mov и int.
