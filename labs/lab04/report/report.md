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
```
4.2.1. Базовые сведения о Markdown
Чтобы создать заголовок, используйте знак #, например:
# This is heading 1
## This is heading 2
### This is heading 3
#### This is heading 4
Чтобы задать для текста полужирное начертание, заключите его в двойные
звездочки:
This text is **bold**.
Чтобы задать для текста курсивное начертание, заключите его в одинарные
звездочки:
This text is *italic*.
Чтобы задать для текста полужирное и курсивное начертание, заключите его
в тройные звездочки:
This is text is both ***bold and italic***.
Блоки цитирования создаются с помощью символа >:
> The drought had lasted now for ten million years, and the reign of
the terrible lizards had long since ended. Here on the Equator,
in the continent which would one day be known as Africa, the
battle for existence had reached a new climax of ferocity, and
the victor was not yet in sight. In this barren and desiccated
land, only the small or the swift or the fierce could flourish,
or even hope to survive.
↪
↪
↪
↪
↪
↪
Упорядоченный список можно отформатировать с помощью соответствую-
щих цифр:
1. First instruction
1. Sub-instruction
1. Sub-instruction
1. Second instruction
Чтобы вложить один список в другой, добавьте отступ для элементов дочер-
него списка:
1. First instruction
1. Second instruction
1. Third instruction
Неупорядоченный (маркированный) список можно отформатировать с помо-
щью звездочек или тире:
* List item 1
* List item 2
* List item 3
Чтобы вложить один список в другой, добавьте отступ для элементов дочер-
него списка:
- List item 1
- List item A
- List item B
- List item 2
Синтаксис Markdown для встроенной ссылки состоит из части [link text],
представляющей текст гиперссылки, и части (file-name.md) – URL-адреса или
имени файла, на который дается ссылка:
[link text](file-name.md)
или
[link text](http://example.com/ "Необязательная подсказка")
Markdown поддерживает как встраивание фрагментов кода в предложение,
так и их размещение между предложениями в виде отдельных огражденных
блоков. Огражденные блоки кода — это простой способ выделить синтаксис для
фрагментов кода. Общий формат огражденных блоков кода:
``` language
your code goes in here
```
4.2.2. Оформление формул в Markdown
Внутритекстовые формулы делаются аналогично формулам LaTeX. Например,
Смотри формулу (`[-@eq:eq1]`).
4.2.3. Оформление изображений в Markdown
В Markdown вставить изображение в документ можно с помощью непосред-
ственного указания адреса изображения. Синтаксис данной команды выглядит
следующим образом:
![Подпись к рисунку](/путь/к/изображению.jpg "Необязательная
подсказка"){ #fig:fig1 width=70% }↪
Здесь:
• в квадратных скобках указывается подпись к изображению;
• в круглых скобках указывается URL-адрес или относительный путь изоб-
ражения, а также (необязательно) всплывающую подсказку, заключённую
в двойные или одиночные кавычки.
• в фигурных скобках указывается идентификатор изображения (#fig:fig1)
для ссылки на него по тексту и размер изображения относительно ширины
страницы (width=90%)
Ссылка на изображение (рис. 4.1) может быть оформлена следующим образом
(рис. [-@fig:fig1])
4.2.4. Обработка файлов в формате Markdown
Преобразовать файл README.md можно следующим образом:
pandoc README.md -o README.pdf
или так
pandoc README.md -o README.docx
Для компиляции отчетов по лабораторным работам предлагается использо-
вать следующий Makefile
FILES = $(patsubst %.md, %.docx, $(wildcard *.md))
FILES += $(patsubst %.md, %.pdf, $(wildcard *.md))
LATEX_FORMAT =
FILTER = --filter pandoc-crossref
%.docx: %.md
-pandoc "$<" $(FILTER) -o "$@"
%.pdf: %.md
-pandoc "$<" $(LATEX_FORMAT) $(FILTER) -o "$@"
all: $(FILES)
@echo $(FILES)
clean:
-rm $(FILES) *~
4.3. Техническое обеспечение
При выполнении лабораторной работы на своей технике необходимо устано-
вить следующее ПО:
• TeX Live (https://www.tug.org/texlive/) последней версии.
• Pandoc (https://pandoc.org/) версии v2.18
• Pandoc-crossref (https://github.com/lierdakil/pandoc-crossref/releases)
версии v0.3.13.0
На компьютерах в дисплейных классах факультета физико-математических
и естественных наук РУДН все необходимое ПО установлено.
```

# Выполнение лабораторной работы
1) С помощью терминала перехожу в каталог курса, сформированный при выполнении лабораторной работы 3,после чего обновляю локальный репозиторий, скачав изменения из удаленного репозитория (рис. [-@fig:001])

![рис.1](image/Снимок экрана от 2022-10-27 11-12-53.png){ #fig:001 width=70% }


2) Перехожу в каталог с отчетом по лабораторной работе и 4 и провожу компиляцию шаблона с использованием Makefile (рис.[-@fig:002]

![рис.2](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab04/report/image/Снимок экрана от 2022-10-27 11-26-28.png){ #fig:002 width=70% }

3) Проверяю корректность полученных файлов (рис. [-fig:003])

![рис.3](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab04/report/image/Снимок экрана от 2022-10-27 11-29-17.png){ #fig:003 width=70% }

4) Удаляю полученные файлы с помощью Makefile (рис. [-fig:004])

![рис.4](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab04/report/image/Снимок экрана от 2022-10-27 11-32-16.png){ #fig:004 width=70% }

5)Проверяю, что файлы были удалены, после чего приступаю к оформлению отчета в gedit (рис. [-fig:005])
![рис.5](/afs/.dk.sci.pfu.edu.ru/home/d/s/dseryomin/work/study/2022-2023/Архитектура компьютера/arch-pc/labs/lab04/report/image/Снимок экрана от 2022-10-27 11-31-33.png){ #fig:005 width=70% }

# Выводы

В ходе лабораторной работы я освоил процедуры оформления отчетов с помощью легковесного языка разметки Markdown.

