# Szablon raportu LaTeX (Politechnika Wrocławska, język polski)

Szablon raportów, sprawozdań i dokumentacji projektowej: jednolity wygląd, strona tytułowa PWr, spisy (treści,
rysunków, tabel, listingów, algorytmów), bibliografia BibTeX oraz załączniki. Dokument jest wyłącznie po polsku.

## Szybki start

1. Wgraj archiwum `report-template.zip` na Overleaf (*New Project -> Upload Project*) albo rozpakuj lokalnie.
2. W pliku `config/metadata.tex` wpisz tytuł, przedmiot, autorów, prowadzącego, miejscowość i datę.
3. Zastąp przykładowe rozdziały w `chapters/` własnymi (usuń ramki `\TemplateNote{...}`).
4. Zdjęcia i zrzuty ekranu wrzucaj do `images/` i wstawiaj makrem `\Figure`.
5. Skompiluj `main.tex` (pdfLaTeX + BibTeX).

## Układ projektu

```
main.tex                 szkielet dokumentu (kolejność części, bez treści)
config/
  metadata.tex           JEDYNE miejsce z danymi dokumentu i przełącznikami części opcjonalnych
  theme-pwr.tex          kolory, nazwy uczelni i wydziału, plik logo
preamble/
  packages.tex           pakiety (kolejność istotna)
  polish.tex             wszystkie polskie napisy (Rozdział, Spis rysunków, Algorytm, ...)
  macros.tex             \code, \file, \cmd, \hash, \lead, środowisko qa, twierdzenia, listy
  floats-and-tables.tex  podpisy, makro \Figure, kolumny tabel
  listings.tex           style listingów: terminal (domyślny) i code
  headings.tex           tytuły rozdziałów i sekcji
  pagestyles.tex         nagłówki i stopki
  links.tex              hyperref i metadane PDF (zawsze ostatni)
frontmatter/             strona tytułowa, streszczenie, spis skrótów
chapters/                rozdziały 1_wstep ... 6_podsumowanie
appendices/              załączniki (A_przykladowy.tex)
images/                  zdjęcia i rysunki (placeholder.pdf = zastępczy obraz)
logos/                   logo uczelni
bib/
  references.bib         źródła (BibTeX)
  plabbrv-fixed.bst      polski styl bibliografii
scripts/make-zip.ps1     budowanie archiwum szablonu
```

## Dane dokumentu (`config/metadata.tex`)

| Makro | Znaczenie |
| --- | --- |
| `\DocType`, `\DocTitle` | rodzaj dokumentu (np. Raport) i jego tytuł |
| `\Course`, `\Subject`, `\GroupInfo` | kierunek, przedmiot (także w stopce), grupa zajęciowa |
| `\Authors`, `\Supervisor` | autorzy i prowadzący; kolejne linie rozdzielaj przez `\\` |
| `\PlaceDate` | miejscowość i data wpisywane ręcznie (bez `\today`) |
| `\DocumentHash` | linia ze skrótem na stronie tytułowej; pusta wartość ukrywa linię |
| `\PdfAuthor` | autor w metadanych PDF |

Przełączniki: `\showabstract`, `\showabbreviations`, `\showbibliography`, `\showlistoffigures`,
`\showlistoftables`, `\showlistoflistings`, `\showlistofalgorithms`, `\showappendices`
(każdy z końcówką `true` lub `false`), oraz `\printversiontrue` (odnośniki bez kolorów do druku).

## Najczęstsze czynności

- **Nowy rozdział:** utwórz `chapters/7_nazwa.tex` z `\chapter{Tytuł}\label{ch:nazwa}` i dodaj
  `\input{chapters/7_nazwa}` w `main.tex`.
- **Rysunek:** `\Figure[0.8]{plik.png}{Podpis}{fig:etykieta}`. Brak pliku nie przerywa kompilacji
  - w jego miejscu widać ramkę z nazwą pliku.
- **Tabela:** podpis nad tabelą, `\tablefont`, `booktabs`; kolumny rozciągliwe `Y`/`Z` w `tabularx`,
  stałe `L{..}`/`C{..}`/`R{..}`. Długie tabele: `longtable` (przykład w rozdziale 4).
- **Listing:** domyślnie styl `terminal`; kod: `[style=code, language=Python]`.
- **Skróty i ścieżki w tekście:** `\code{}`, `\file{}`, `\cmd{}`, `\hash{}`.
- **Pytanie i odpowiedź:** `\begin{qa}{Treść pytania} ... \end{qa}`.
- **Cytowanie:** dodaj wpis do `bib/references.bib` i użyj `\cite{klucz}`.
- **Załącznik:** dodaj plik w `appendices/` i `\input` w `main.tex`; numeracja zmienia się na literową.
- **Druk jednostronny:** w `main.tex` zamień `twoside` na `oneside`.

## Kompilacja

Silnik: **pdfLaTeX** + **BibTeX** (bez `--shell-escape`). Na Overleaf wybierz kompilator *pdfLaTeX*
i plik główny `main.tex`; Overleaf sam uruchomi kolejne przebiegi i BibTeX-a. Lokalnie:
`pdflatex`, `bibtex`, `pdflatex`, `pdflatex`.

## Budowanie archiwum szablonu

```powershell
powershell -ExecutionPolicy Bypass -File scripts\make-zip.ps1
```

Wynik: `dist\report-template.zip` (tylko pliki źródłowe, bez plików pomocniczych LaTeX-a).
