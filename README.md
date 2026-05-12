# York University Assignment Template
 
A LaTeX assignment template for York University STEM students. All configuration is done through a single metadata block at the top of `main.tex` — no need to edit any other file for standard use.
 
---
 
## Two Versions
 
This template comes in two versions:
 
| Version | File | Best for |
|---|---|---|
| **Full** | `stemtemplate.sty` | Local compilation in TeXstudio or similar |
| **Overleaf** | `stemtemplate-overleaf.sty` | Collaborating on Overleaf |
 
The Overleaf version is a leaner variant of the full template. It loads fewer packages by default and strips non-essential formatting to keep Overleaf compile times short. Heavy packages like `tikz`, `pgfplots`, and `circuitikz` are commented out and can be uncommented when needed for a specific project.
 
> **Overleaf template:** [add link here]
 
### Recommended Workflow
 
1. Start a new project using the Overleaf template
2. Collaborate and write your content on Overleaf
3. When the document is ready for final submission, transfer your content files to this full template and compile locally for the polished final output
Both templates use identical metadata fields, environments, and commands so your content files transfer without any changes.
 
---
 
## Quick Start
 
1. Fill in the metadata block at the top of `main.tex`
2. Replace `\input{assets/example}` with `\input{yourfile}` pointing to your content
3. Compile with **PDFLaTeX → Biber → PDFLaTeX → PDFLaTeX**
---
 
## File Structure
 
```
├── main.tex                        ← Edit metadata here, compile this file
├── assets/
│   ├── stemtemplate.sty            ← Full template (local)
│   ├── stemtemplate-overleaf.sty   ← Lean template (Overleaf)
│   ├── titlepage_standard.tex      ← Title page layouts (don't edit)
│   ├── titlepage_abstract.tex
│   ├── titlepage_compact.tex
│   └── example.tex                 ← Example file showing all features
├── figures/                        ← Place your images here
└── references.bib                  ← Your bibliography entries
```
 
---
 
## Metadata
 
All settings are controlled from the top of `main.tex`:
 
```latex
\newcommand{\metaAssignmentTitle}{Assignment Title}
\newcommand{\metaStudentName}{Your Name}
\newcommand{\metaStudentNumber}{123456789}
\newcommand{\metaStudentEmail}{email@my.yorku.ca}
\newcommand{\metaPartners}{}              % "Jane Doe & 123456789\\John Doe & 123456789"
\newcommand{\metaUniversity}{York University}
\newcommand{\metaFaculty}{Lassonde School of Engineering}
\newcommand{\metaDepartment}{Department Name}
\newcommand{\metaCourseCode}{Code}
\newcommand{\metaCourseName}{Class}
\newcommand{\metaInstructor}{Dr. Professor}
\newcommand{\metaDate}{Due date}
\newcommand{\metaLogoPath}{}              % Path to logo file, or leave empty
```
 
---
 
## Title Page
 
Set `\metaTitlePage` to one of three options:
 
| Option | Description |
|---|---|
| `standard` | Full title page with student and instructor info |
| `abstract` | Same as standard but includes the abstract |
| `compact` | Inline title block, no separate page |
 
---
 
## Logo
 
The faculty logo is not included in this repository. Download the official logo from the [York University Brand Assets page](https://www.yorku.ca/brand/assets-downloads/faculty-assets/) and place it in `assets/`. Then update `\metaLogoPath` in the metadata:
 
```latex
\newcommand{\metaLogoPath}{assets/LASS_yu_PRIMARY_hor_RGB.png}
```
 
Leave it empty to display no logo.
 
---
 
## Other Settings
 
| Metadata | Options | Description |
|---|---|---|
| `\metaBibStyle` | `ieee`, `apa` | Bibliography style |
| `\metaDefaultFont` | `sans`, `serif` | Document font |
| `\metaLineSpacing` | `single`, `onehalf`, `double` | Line spacing |
| `\metaShowTodo` | `true`, `false` | Show or hide todo notes |
| `\metaWatermarkText` | any text or empty | Watermark text, leave empty for none |
| `\metaThemeColour` | hex code, colour name, or empty | Primary accent colour, defaults to navy |
| `\metaNumberEquations` | `true`, `false` | Number equations by section |
| `\metaNumberFigures` | `true`, `false` | Number figures by section |
| `\metaNumberTables` | `true`, `false` | Number tables by section |
| `\metaNumberTheorems` | `true`, `false` | Number theorem environments by section |
| `\metaNumberProblems` | `true`, `false` | Number problem environments by section |
| `\metaNumberAlgorithms` | `true`, `false` | Number algorithms by section |
| `\metaNumberListings` | `true`, `false` | Number code listings by section |
 
---
 
## Compiling
 
This template uses **biblatex with Biber**. In TeXstudio go to **Options → Configure TeXstudio → Build** and set the bibliography tool to `Biber`. On first compile run **Tools → Bibliography** manually, then compile twice more.
 
On Overleaf the compile sequence is handled automatically.
 
---
 
## Acknowledgements
 
This template was developed with the assistance of generative AI.
 
---
 
## License
 
MIT License — see [LICENSE](LICENSE) for details.
 
Copyright (c) 2026 Tyler Bignell
 
York University and faculty logos are the property of York University and are not covered by this license.