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

* klonowanie repozytorium (lokalna kopia; `git clone`) 
* stage'owanie zmian (`git add`/`git reset`)
* commitowanie lokalnych zmian (`git commit`)
* publikowanie lokalnych zmian (`git push`)
* zaciąganie zdalnych zmian (`git fetch`)
* integrowanie lokalnych zmian (`git merge`)
* integrowanie zdalnych zmian (`git pull`)
* gałęzie/branche (`git branch`++)
* historia repozytorium (`git log`)
* zmiany w poszczególnych commitach (`git diff`)

### Formaty tekstowe

* [Plain text](https://en.wikipedia.org/wiki/Plain_text)
* [Markdown](https://www.markdowntutorial.com/)
* [XML](http://www.tei-c.org/support/learn/teach-yourself-tei/)
* [LaTeX](https://www.latex-tutorial.com/tutorials/)
* (honorable mention) HTML
* (honorable mention) [Wikitext](https://en.wikipedia.org/wiki/Help:Wikitext)

Powiedzmy wprost: świat się na tym nie kończy.

### Na warsztaty

#### Narzędzia

* [Konto GitHub](https://github.com/join)
* [Atom](https://atom.io/)
* [pandoc](https://pandoc.org)
* Najbardziej pożyteczny skrót klawiszowy w atomie: `Ctrl+Shift+P` (`Toggle Command Palette`) - możemy
tam wyszukiwać łatwo polecenia dostępne w Atomie. Wpisujemy w wyszukiwarkę i klikamy na wyszukane polecenie.

#### Konfiguracja Gita

* Włączamy Atom i tworzymy nowy plik (`File->New File`)
* Wypełniamy jego zawartość jako:
```
[user]
    name = <NAME>
    email = <EMAIL>
```
Zamiast `<NAME>` Wpisujemy swoje imię + nazwisko, pseudonim lub cokolwiek innego. Będą nim podpisane
nasze commity widoczne na GitHubie. W polu `<EMAIL>` dobrze jest wpisać nasz email, który podaliśmy
przy rejestracji na GitHubie (wtedy nasze commity będą skojarzone z naszym kontem), ale nie ma takiego
obowiązku.

* W Atomie wybieramy `File->Save as...` i zapisujemy plik jako `.gitconfig` w swoim katalogu domowym
(Windows: `C:\Users\nazwa-uzytkownika\.gitconfig`, Linux: `/home/nazwa-uzytkownika/.gitconfig`,
MacOs `/Users/nazwa-uzytkownika/.gitconfig`). **Uwaga:** nazwa pliku jest "magiczna"
(plik musi się nazywać dokładnie tak, z nazwą zaczynającą się od kropki).

#### Klonowanie repozytorium

* Na stronie internetowej naszego repozytorium GitHubowego klikamy zielony guzik `Clone or download`, 
wybieramy `Use HTTPS` i kopiujemy podany tam adres
* W Atomie klonujemy nasze repozytorium -- w `Command Palette` (zob. wyżej) wybieramy `GitHub: Clone`,
w `Clone from` podajemy adres skopiowany w powyższym punkcie. **Uwaga**: Atom może rzucić błędem. Jeśli
mimo wszystko pojawił się po lewej stronie katalog, który próbowaliśmy klonować, ignorujemy błąd.

#### Prosta edycja

* Tworzymy nowy plik, dla ustalenia uwagi `a_file.md`: Klikamy prawym przyciskiem myszy na sklonowany
folder w drzewku po lewej stronie, wybieramy `New File`, podajemy nazwę pliku.
* Piszemy/przeklejamy i formatujemy rzeczy w pliku. Minimalną ściągę z popularnych kodów formatowania
MarkDowna można znaleźć np. tutaj: <https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet>
* Zapisujemy plik (`File-Save`, `Ctrl+S`)
* Jeśli po prawej stronie okna Atoma nie mamy menu `Gita`, w prawym dolnym rogu okna klikamy na napis Git
* Na liście `Unstaged changes` powinniśmy widzieć nasz plik. Klikając na niego raz możemy obejrzeć `diff`
(czyli zmiany względem poprzedniej wersji - w naszym przypadku wszystko w pliku jest nowe).
* Klikamy dwukrotnie, aby przenieść plik z `Unstaged changes` do `Staged changes`.
* W okienku `Commit message` wpisujemy "sensowny" opis naszych zmian (tradycja mówi, że w naszej sytuacji
opis "First commit" nie jest taki zły...) i klikamy `Commit`
* W dolnym pasku, po prawej stronie, powinien znaleźć się napis `Push 1` (oznaczający, że mamy jeden
niewypushowany commit). Kliknijmy na niego.
* Jeśli wszystko zrobiliśmy dobrze, Na stronie internetowej (GitHubowej) naszego repozytorium powinien
pojawić się nasz plik. Kiedy na niego klikniemy, GitHub powinien wyświetlić go w wersji ładnie sformatowanej
(przycisk `Raw` pozwala zobaczyć plik w takiej postaci, w jakiej go tworzyliśmy).

#### Kolejne kroki

* Pożyteczne pluginy do atoma: `autocomplete-bibtex`, `pandoc-convert`
* Na stronie <https://www.zotero.org/styles> można znaleźć plik z pożądanycm przez nas formatowaniem cytowań,
który podamy pandocowi 
* Na stronie <https://pandoc.org/demos.html> można znaleźć przykładowe polecenia do robienia różnych rzeczy
w pandocu; polecenia wołamy w wierszu poleceń (Linux/MacOs: terminal, Windows: `Start->cmd`).
* Przykładowe polecenie (uwaga, trzeba je przeczytać, zrozumieć i dostosować nazwy plików), które 
z pliku `a_file.md` i bibliografii `my_bib.bib` (format `bibtex`, łatwy do wygenerowania np. z Zotero)
 wygeneruje plik `a_file.md.pdf`: `pandoc --filter=pandoc-citeproc --smart --listings --number-sections 
--bibliography my_bib.bib --standalone a_file.md -o a_file.md.pdf`
* [GitHub Pages](https://pages.github.com/) pozwala autogenerować strony takie jak ta na podstawie zawartości
repozytorium GitHubowego.

### Pożyteczne linki

* [A Plain Text Workflow for Academic Writing with Atom](http://u.arizona.edu/~selisker/post/workflow/)
* [Sustainable Authorship in Plain Text using Pandoc and Markdown](https://programminghistorian.org/en/lessons/sustainable-authorship-in-plain-text-using-pandoc-and-markdown)
* [Using Atom for academic writing](https://discuss.atom.io/t/using-atom-for-academic-writing/19222)

Ostatnia zmiana: {{ site.time | date: '%Y-%m-%d %H:%M:%S' }} UTC

Autor: Piotr Kasprzyk <p.kasprzyk@uw.edu.pl>
