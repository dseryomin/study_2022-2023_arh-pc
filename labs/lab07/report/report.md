---
## Front matter
title: "Лабораторная работа 7"
subtitle: "Арифметические операции в NASM"
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
Освоение арифметических инструкций языка ассемблера NASM.


# Выполнение лабораторной работы

1) Создаю каталог для программ лабораторной работы No 7, перехожу в него и создаю файл lab7-1.asm: (рис. [-@fig:001])

![создание файла](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab07/report/Снимок экрана от 2022-11-24 10-57-57.png){ #fig:001 width=90% }


2) Ввожу в файл lab7-1.asm текст программы из листинга 7.1, создаю исполняемый файл и заупскаю его  (рис.[-@fig:002]

![результат создания файла](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab07/report/Снимок экрана от 2022-11-24 11-04-31.png){ #fig:002 width=90% }

3) Далее изменяю текст программы и вместо символов записываю в регистры числа.Видим,что символ не отображается на экране. (рис. [-@fig:003])

![редактирование файла](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab07/report/Снимок экрана от 2022-11-24 12-10-59.png){ #fig:003 }

4) Создаю файл lab7-2.asm в каталоге ~/work/arch-pc/lab07 и ввожу в него текст программы из листинга 7.2  (рис. [-@fig:004])

![результат работы текста программы из листинга 7.2](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab07/report/Снимок экрана от 2022-11-24 11-28-29.png){ #fig:004 width=90% }

5) Аналогично предыдущему примеру изменяю символы на числа. Заменяю строки
mov eax,'6'
mov ebx,'4'
   на строки
mov eax,6
mov ebx,4 (рис. [-@fig:005])
![результат изменения текста программы](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab07/report/Снимок экрана от 2022-11-24 12-13-09.png){ #fig:005 width=90% }

6) Заменяю функцию iprintLF на iprint. Создаю исполняемый файл и запускаю его.  (рис. [-@fig:006]) 
 
![резудьтат смены функции iprintLF на iprint ](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab07/report/Снимок экрана от 2022-11-24 12-13-50.png){ #fig:006 width=90% }

7) Создаю файл lab7-3.asm в каталоге ~/work/arch-pc/lab07:touch ~/work/arch-pc/lab07/lab7-3.asm, внимательно изучаю текст программы из листинга 7.3 и ввожу в lab7-3.asm.Запускаю файл. (рис. [-@fig:007])

![результат работы программы из листинга 7.3](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab07/report/Снимок экрана от 2022-11-24 12-18-16.png){ #fig:007 width=90% }

8) Изменяю текст программы для вычисления выражения f(x)= (4 ∗ 6 + 2)/5. Создаю исполняемый файл и проверяю его работу. (рис. [-@fig:008])

![результат работы программы для вычисления заданной ф-ции](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab07/report/Снимок экрана от 2022-11-24 12-20-23.png){ #fig:008 width=90% }

9) Создаю файл variant.asm в каталоге ~/work/arch-pc/lab07:touch ~/work/arch-pc/lab07/variant.asm. Внимательно изучаю текст программы из листинга 7.4 и ввожу в файл
variant.asm. Аналитически проверяю корректност вычислений. (рис. [-@fig:009])

![результат работы программы для вычисления номера варианта по номеру студ.билета](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab07/report/Снимок экрана от 2022-11-24 12-29-01.png){ #fig:009 width=90% }

Ответы: 1)строки mov eax,rem call sprint
2) mov ecx,x: записывает адресы выводимого сообщения в EAX
mov edx,80: записывает дину вводимого сообщения в EBX
call sread выполняет вызов программы ввода сообщения
3) для преобразования символа в число
4) xor edx,edx mov ebx,20 div ebx inc edx
5) в регистр EBX
6) для увеличения значения edx на единицу
7)mov eax,edx call iprintLF

Задания для самостоятельной работы:


10)Необходимо написать программу для вычисления функции из 2ого варианта.
Напишем программу и проверим кореектность, подставив x=1 и x=6 (рис. [-@fig:010])

![результат работы программы для нахождения ф-ции](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab07/report/Снимок экрана от 2022-11-24 14-40-34.png){ #fig:010 width=90% }



# Выводы

В ходе выполнения данной лабораторной работы я освоил арифметические инструкции языка ассемблера NASM.
