# Security Incident Management and Response in a Neobank Environment

[![View PDF](https://img.shields.io/badge/View-PDF-blue?style=for-the-badge&logo=adobeacrobatreader&logoColor=white)](https://alehshehda.github.io/ISM-project/ISM-project.pdf)
[![Download PDF](https://img.shields.io/badge/Download-PDF-success?style=for-the-badge&logo=github&logoColor=white)](https://github.com/alehshehda/ISM-project/releases/download/latest/ISM-project.pdf)

Project documentation for the **Information Security Management** course (*Zarządzanie bezpieczeństwem informacji*) at Wrocław University of Science and Technology, Faculty of Information and Communication Technology (Cybersecurity).

## Authors

- Aleh Shehda (272277)
- Aliaksei Lapachuk (276711)
- Maksym Buhai (276592)

**Supervisor:** dr inż. Tomasz Krzysztof Janiczek

## Repository Structure

```text
main.tex                              main LaTeX document file
.github/
  workflows/
    compile.yml                       automated PDF build and release workflow
config/
  metadata.tex                        document metadata and optional section toggles
  theme-pwr.tex                       WUST visual theme and colors
preamble/                             packages, page styles, macros, and table settings
frontmatter/
  titlepage.tex                       title page layout
  abbreviations.tex                   list of abbreviations and acronyms
chapters/
  1_wstep.tex                         Introduction and organization profile
  2_wymogi_regulacyjne.tex            Regulatory requirements and normative foundations
  3_organizacja_procesu.tex           Incident management process and response plan (IRP)
  4_playbooki_operacyjne.tex          Operational playbooks, incident register, and evidence handling
  5_studium_przypadku.tex             Case study, post-incident activities, and KPIs
  6_podsumowanie.tex                  Summary and conclusions
appendices/
  A_szablony_formularzy.tex           Incident forms and report templates
bib/
  references.bib                      BibTeX bibliography database
  plabbrv-fixed.bst                   Polish bibliography style
images/                               figures and diagrams
logos/                                university logos
```

## Build

The document is automatically compiled to `ISM-project.pdf` and published to GitHub Releases and GitHub Pages via the GitHub Actions CI/CD workflow (`.github/workflows/compile.yml`) on every push to `main`.
