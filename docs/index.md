---  
title: Git, GitHub i publikowanie naukowe z zachowaniem kontroli wersji  
author: Piotr Kasprzyk  
date: 2018-12-19  
---  

# Git, GitHub i publikowanie naukowe z zachowaniem kontroli wersji
## Notatki i linki

### Zasoby na później (niech się ściągają, ja będę gadał)

1. <https://atom.io/>
2. <https://pandoc.org/installing.html>

### Git

> System kontroli wersji śledzi wszystkie zmiany dokonywane na pliku
> (lub plikach) i umożliwia przywołanie dowolnej wcześniejszej wersji.
> (...). Pozwala on przywrócić plik(i) do wcześniejszej wersji, odtworzyć
> stan całego projektu, porównać wprowadzone zmiany, dowiedzieć się kto jako
> ostatnio zmodyfikował część projektu powodującą problemy, kto i kiedy
> wprowadził daną modyfikację. Oprócz tego używanie VCS oznacza, że nawet
> jeśli popełnisz błąd lub stracisz część danych, naprawa i odzyskanie ich
> powinno być łatwe. Co więcej, wszystko to można uzyskać całkiem niewielkim
> kosztem.  ([Pro Git](https://git-scm.com/book/pl/v2/Pierwsze-kroki-Wprowadzenie-do-kontroli-wersji))

Git jest rozproszonym systemem kontroli wersji (Distributed Version Control System),
co oznacza, że kopie projektu objętego kontrolą VCS (określanego mianem "repozytorium")
mogą być przechowywane w kilku miejscach jednocześnie, a narzędzia wbudowane
w Gita umożliwiają wygodne synchronizowanie danych w tych lokalizacjach.


### Wikipedia jako przykład kontroli wersji w działaniu

<https://en.wikipedia.org/wiki/List_of_treasure_hunters>


### GitHub

Zwykle pracując z Gitem chcemy mieć lokalne repozytorium u siebie
na komputerze (tam wprowadzamy zmiany), ale także zdalne repozytorium na jakimś
serwerze - w nim dane są:
* dostępne dla ew. naszych innych komputerów
* dostępne dla naszych współpracowników
* zabezpieczone przez zaginięciem/zepsuciem naszego komputera zawierającego
  lokalne repozytorium

GitHub to organizacja, która umożliwia utrzymywanie zdalnych repozytoriów
Gita (i umila to wieloma towarzyszącymi narzędziami). Można również powiedzieć,
że GitHub to hosting dla repozytoriów Gitowych.

### Podstawowe koncepcje w Git

* stage'owanie zmian (`git add`/`git reset`)
* commitowanie lokalnych zmian (`git commit`)
* publikowanie lokalnych zmian (`git push`)
* zaciąganie zdalnych zmian (`git fetch`)
* integrowanie lokalnych zmian (`git merge`)
* integrowanie zdalnych zmian (`git pull`)
* gałęzie/branche (`git branch`++)

### Formaty tekstowe

* [Plain text](https://en.wikipedia.org/wiki/Plain_text)
* [Markdown](https://www.markdowntutorial.com/)
* [XML](http://www.tei-c.org/support/learn/teach-yourself-tei/)
* [LaTeX](https://www.latex-tutorial.com/tutorials/)
* (honorable mention) HTML
* (honorable mention) [Wikitext](https://en.wikipedia.org/wiki/Help:Wikitext)

Powiedzmy wprost: świat się na tym nie kończy.

### Na warsztaty

* [Konto GitHub](https://github.com/join)
* [Atom](https://atom.io/)
* [pandoc](https://pandoc.org)
* Najbardziej pożyteczny skrót klawiszowy w atomie: `Ctrl+Shift+P` (`Toggle Command Palette`)
* Pożyteczne pluginy do atoma: `autocomplete-bibtex`, `pandoc-convert`
* https://www.zotero.org/styles
* https://pandoc.org/demos.html
* `pandoc --filter=pandoc-citeproc --smart --listings --number-sections --bibliography my_bib.bib --standalone a_file.md -o a_file.md.pdf`
* [GitHub Pages](https://pages.github.com/)

### Pożyteczne linki

* [A Plain Text Workflow for Academic Writing with Atom](http://u.arizona.edu/~selisker/post/workflow/)
* [Sustainable Authorship in Plain Text using Pandoc and Markdown](https://programminghistorian.org/en/lessons/sustainable-authorship-in-plain-text-using-pandoc-and-markdown)
* [Using Atom for academic writing](https://discuss.atom.io/t/using-atom-for-academic-writing/19222)

Ostatnia zmiana: {{ site.time | date: '%Y-%m-%d %H:%M:%S' }} UTC
