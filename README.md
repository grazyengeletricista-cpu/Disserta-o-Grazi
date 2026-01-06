# Dissertação de Mestrado

## Estrutura do Projeto

Este projeto contém uma dissertação de mestrado em LaTeX com a seguinte organização:

```
.
├── main.tex
├── biblioteca.bib
├── Capitulos/
├── Figuras/
├── Anexos/
└── README.md
```

## Como Compilar

```bash
pdflatex main.tex
bibtex main.aux
pdflatex main.tex
pdflatex main.tex
```

Ou use um script automático:
```bash
latexmk -pdf main.tex
```

## Arquivo Principal (main.tex)

```latex
\documentclass[12pt,a4paper]{report}
\usepackage[utf-8]{inputenc}
\usepackage[portuguese]{babel}
\usepackage{graphicx}
\usepackage[hidelinks]{hyperref}

\graphicspath{{Figuras/}}
\bibliography{biblioteca}
\bibliographystyle{abntex2-alf}

\title{Título da Dissertação}
\author{Seu Nome}
\date{\today}

\begin{document}

\maketitle
\tableofcontents

\include{Capitulos/introducao}
\include{Capitulos/desenvolvimento}
\include{Capitulos/conclusao}

\appendix
\include{Anexos/anexo_a}

\bibliographystyle{abntex2-alf}
\bibliography{biblioteca}

\end{document}
```

## Dependências

- `abntex2` - Normas ABNT para LaTeX
- `latexmk` - Compilador automático
