# Zarządzanie i reagowanie na incydenty bezpieczeństwa w środowisku Neobank

[![Zobacz PDF](https://img.shields.io/badge/Zobacz_PDF-GitHub_Pages-8C0014?style=for-the-badge&logo=adobeacrobatreader&logoColor=white)](https://alehshehda.github.io/ISM-project/)
[![Pobierz PDF](https://img.shields.io/badge/Pobierz_PDF-Latest_Release-2ea44f?style=for-the-badge&logo=github&logoColor=white)](https://github.com/alehshehda/ISM-project/releases/download/latest/ISM-project.pdf)

Dokumentacja projektowa z przedmiotu **Zarządzanie bezpieczeństwem informacji** (Politechnika Wrocławska, Wydział Informatyki i Telekomunikacji, kierunek Cyberbezpieczeństwo).

## Autorzy

- Aleh Shehda (272277)
- Aliaksei Lapachuk (276711)
- Maksym Buhai (276592)

**Prowadzący:** dr inż. Tomasz Krzysztof Janiczek

## Struktura repozytorium

```text
main.tex                              główny plik dokumentu LaTeX
.github/
  workflows/
    compile.yml                       automatyczna kompilacja i publikacja PDF (GitHub Actions)
config/
  metadata.tex                        metadane dokumentu i przełączniki części opcjonalnych
  theme-pwr.tex                       motyw graficzny Politechniki Wrocławskiej
preamble/                             konfiguracja pakietów, stylów stron, makr i tabel
frontmatter/
  titlepage.tex                       strona tytułowa
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

## Kompilacja i publikacja (CI/CD)

### Automatyczna (GitHub Actions)
Każdy `push` na gałąź `main` automatycznie uruchamia workflow `.github/workflows/compile.yml`, który:
1. Kompiluje dokument `main.tex` do pliku `ISM-project.pdf`.
2. Aktualizuje wydanie `latest` w zakładce **Releases**.
3. Publikuje najnowszą wersję dokumentu PDF na **GitHub Pages**.

### Lokalna
Dokument można również skompilować lokalnie przy użyciu **pdfLaTeX** oraz **BibTeX**:

```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```
