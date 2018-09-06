Структура:

prog
|- prog.tex (сборник)
|
|- problems (данные)
|  |- 2013-12.tex
|  |- 2014-03.tex
|  |- ...
|  |- pictures
|  |- |- 2016-04-E.tex
|  |- |- ...
|
|- solutions (данные)
|  |- 2013-12.tex
|  |- 2014-03.tex
|  |- ...
|
|- results (данные)
|  |- 2013-12.tex
|  |- 2014-03.tex
|  |- ...
|
|- year by year (по годам)
|  |- generate.py (скрипт, генерирующий обертку для каждого года)
|  |- template (шаблоны)
|  |- |- olymp-problems.tex (pdf условия)
|  |- |- olymp-a5-12pt.tex (png условия)
|  |- |- olymp-a5-10pt.tex (png условия)
|  |- |- olymp-solutions.tex (решения)
|  |- |- olymp-results-ind.tex (результаты)
|  |- |- olymp-results-team.tex (результаты)
|  |
|  |- msu.txt (список подстановок в шаблон)
|  |- msu-ind.txt (список подстановок в шаблон)
|  |- msu-team.txt (список подстановок в шаблон)
|  |
|  |- problems 
|  |  |- problems-2020.tex
|  |  |- problems-2020.pdf
|  |  |- problems-2020.png
|  |  |- ...
|  |
|  |- solutions
|  |  |- solutions-2020.tex
|  |  |- solutions-2020.pdf
|  |  |- ...
|  |
|  |- results
|  |  |- results-2020.tex
|  |  |- results-2020.pdf
|  |  |- ...

============================

Добавить олимпиаду:

1) problems/2020-10.tex - условия
   problems/pictures/2020-10-A.tex - картинка
2) solutions/2020-10.tex - решения
3) results/2020-10.tex - результаты
4) yby/2020.txt
	file, date, name, hoster, city
	2018-05, 27 октября 2020, Открытая олимпиада по программированию \\ Осенний тур 2020, Казахстанский филиал МГУ имени М.В.Ломоносова, г.~Астана 
5) cd yby
6) python3 generate.py png 2020.txt template/olymp-problems.tex problems
7) python3 generate.py pdf 2020.txt template/olymp-solutions.tex solutions
8) python3 generate.py pdf 2020.txt template/olymp-results-team.tex results

============================

Добавить в книгу:

1) prog.tex
   добавить строки
\head{Осенний тур 2020}{27 октября 2020}
\input{problems/2020-10}
\result{2020-10}{27 октября 2020}

\head{Осенний тур 2020}{27 октября 2020}
\input{solutions/2020-10}

добавить тематический указатель themes.tex

2) pdflatex prog.tex

============================

Добавить на сайт

0) cd yby
1) python3 generate.py png 2020.txt template/olymp-a5-12pt.tex  ../problems/ ~/http/mymath.info/prog/msu/problems/ msu- -mobile
   python3 generate.py png 2020.txt template/olymp-a5-10pt.tex  ../problems/ ~/http/mymath.info/prog/msu/problems/ msu- -desktop
   python3 generate.py pdf 2020.txt template/olymp-problems.tex  ../problems/ ~/http/mymath.info/prog/msu/problems/ msu- -problems
2) python3 generate.py pdf 2020.txt template/olymp-solutions.tex s  ../solutions/ ~/http/mymath.info/prog/msu/solutions/ msu- -solutions
3) python3 generate.py pdf 2020.txt template/olymp-results-team.tex s  ../results/ ~/http/mymath.info/prog/msu/results/ msu- -results
4) исправить mymath.info/prog/show.php
	if ($olymp == "msu")
		for ($y = 2014; $y <= 2020; $y++)

============================
