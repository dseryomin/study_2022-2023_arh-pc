---
## Front matter
title: "Лабораторная работа 5"
subtitle: "Создание и процесс обработки программ на языке ассемблера NASM"
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


# Теоретическое введение

Язык ассемблера — это машинно-ориентированный язык низкого уровня,который больше любых
других языков приближен к архитектуре ЭВМ и её аппаратным возможностям,
что позволяет получить к ним более полный доступ, нежели в языках высокого
уровня, таких как C/C++, Perl, Python.
NASM — это открытый проект ассемблера, версии которого доступны под
различные операционные системы и который позволяет получать объектные
файлы для этих систем

# Выполнение лабораторной работы

1)Создаю каталог для работы с программами на языке ассемблера NASM (рис. [-@fig:001])

![создание каталога](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/arch-pc/lab05/Снимок экрана от 2022-11-10 10-50-01.png){ #fig:001 width=90% }


2) Перехожу в созданный каталог (рис.[-@fig:002]

![результат команды 'cd'](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/arch-pc/lab05/Снимок экрана от 2022-11-10 10-50-08.png){ #fig:002 width=90% }

3) Создаю текстовый файл с именем hello.asm с помощью команды 'touch',после чего в текстовом редакторе gedit ввожу текст и компилирую его командой 'nasm -f elf hello.asm' (рис. [-@fig:003])

![результат работы команды для компиляции](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/arch-pc/lab05/Снимок экрана от 2022-11-10 11-27-16.png){ #fig:003 }

4) Проверяю, что файл был создан с помощью команды 'ls'  (рис. [-@fig:004])

![проверка создания файла](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/arch-pc/lab05/Снимок экрана от 2022-11-10 11-28-04.png){ #fig:004 width=90% }

5) с помощью команды 'nasm -o obj.o -f elf -g -l list.lst hello.asm' компилирую исходный файл hello.asm в obj.o, после чего проверяю корректность выполненного действия с помощью команды ls (рис. [-@fig:005])
![Проверка корректности компиляции файла](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/arch-pc/lab05/Снимок экрана от 2022-11-10 11-29-55.png){ #fig:005 width=90% }

6) передаю объектный файл на обработку компоновщику с помощью команды d -m elf_i386 hello.o -o hello,на предыдущем скриншоте видно, что исполняемый файл был создан; после чего выполняю команду 'ld -m elf_i386 obj.o -o main' (рис. [-@fig:006]) 
 
![обработка файлов компоновщиком LD](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/arch-pc/lab05/Снимок экрана от 2022-11-10 11-34-46.png){ #fig:006 width=90% }

7) запускаю созданный исполняемый файл командой './hello' (рис. [-@fig:007])

![ запуск созданного исполняемого файла](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/arch-pc/lab05/Снимок экрана от 2022-11-10 11-37-25.png){ #fig:007 width=90% }


# Выводы

В ходе данной лабораторной работы я освоил процедуры компиляции и сборки программ, написанных на ассемблере NASM.
