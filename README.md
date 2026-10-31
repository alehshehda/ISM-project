# Zarządzanie i reagowanie na incydenty bezpieczeństwa w środowisku Neobank

Dokumentacja projektowa z przedmiotu **Zarządzanie bezpieczeństwem informacji** (Politechnika Wrocławska, Wydział Informatyki i Telekomunikacji, kierunek Cyberbezpieczeństwo).

## Autorzy

- Aleh Shehda (272277)
- Aliaksei Lapachuk (276711)
- Maksym Buhai (276592)

**Prowadzący:** dr inż. Tomasz Krzysztof Janiczek

## Struktura repozytorium

```text
main.tex                              główny plik dokumentu LaTeX
config/
  metadata.tex                        metadane dokumentu i przełączniki części opcjonalnych
  theme-pwr.tex                       motyw graficzny Politechniki Wrocławskiej
preamble/                             konfiguracja pakietów, stylów stron, makr i tabel
frontmatter/
  titlepage.tex                       strona tytułowa
  abstract.tex                        streszczenie i słowa kluczowe
  abbreviations.tex                   spis skrótów i akronimów
chapters/
  1_wstep.tex                         Wstęp i charakterystyka badanej organizacji
  2_wymogi_regulacyjne.tex            Wymogi regulacyjne i podstawy normatywne
  3_organizacja_procesu.tex           Organizacja procesu zarządzania incydentami i plan reagowania
  4_playbooki_operacyjne.tex          Playbooki operacyjne, rejestr incydentów i materiał dowodowy
  5_studium_przypadku.tex             Studium przypadku, działania poincydentowe i wskaźniki skuteczności
  6_podsumowanie.tex                  Podsumowanie i wnioski
appendices/
  A_szablony_formularzy.tex           Szablony formularzy i kart incydentów
bib/
  references.bib                      bibliografia (BibTeX)
  plabbrv-fixed.bst                   styl bibliografii
images/                               rysunki i schematy
logos/                                logotypy uczelni
```

## Kompilacja

Dokument kompilowany przy użyciu **pdfLaTeX** oraz **BibTeX**:

```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```
