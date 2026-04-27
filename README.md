# York University Assignment Template

A LaTeX assignment template for York University students. All configuration is done through a single metadata block at the top of `main.tex` — no need to edit any other file.

---

## Quick Start

1. Fill in the metadata block at the top of `main.tex`
2. Replace `\input{assets/example}` with your own content
3. Compile with PDFLaTeX → Biber → PDFLaTeX → PDFLaTeX

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

## Faculty Colour

Set `\metaFacultyColor` to `true` to automatically apply your faculty's brand colour to headings, boxes, and rules. Set to `false` for a neutral navy.

Supported faculties:
- `Lassonde School of Engineering` — navy
- `Faculty of Science` — sky blue

Any other value defaults to York red. To add more faculties, add a `\definecolor` and `\ifthenelse` block in `yorku.sty`.

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
| `\metaShowTodo` | `true`, `false` | Show todo notes |
| `\metaWatermarkText` | any text | Watermark, leave empty for none |
| `\metaNumberEquations` | `true`, `false` | Number equations by section |
| `\metaNumberFigures` | `true`, `false` | Number figures by section |
| `\metaNumberTables` | `true`, `false` | Number tables by section |
| `\metaNumberTheorems` | `true`, `false` | Number theorems by section |
| `\metaNumberProblems` | `true`, `false` | Number problems by section |
| `\metaNumberAlgorithms` | `true`, `false` | Number algorithms by section |

---

## Compiling

This template uses **biblatex with Biber**. In TeXstudio go to **Options → Configure TeXstudio → Build** and set the bibliography tool to `Biber`. On first compile run **Tools → Bibliography** manually, then compile twice more.

On Overleaf the compile sequence is handled automatically.

---

## Acknowledgements

This template was developed with the assistance of generative AI

---

## License

MIT License — see [LICENSE](LICENSE) for details.

Copyright (c) 2026 Tyler Bignell

York University and faculty logos are the property of York University and are not covered by this license.
