# LaTeX Assignment Template
 
A LaTeX assignment template originally created for York University STEM students but is usable by anyone looking for an assignment template.
 
---
 
## Quick Start
 
1. Fill in the metadata block at the top of `main.tex`
2. Replace `Hello, world!` with `\input{yourfile}` pointing to your content
3. Compile with **PDFLaTeX → Biber → PDFLaTeX → PDFLaTeX**
---
 
## File Structure
 
```
├── assets/                         ← Support files
│   ├── demo.pdf                    ← Compiled demo
│   ├── demo.tex                    ← Demo file showing all features
│   ├── frontmatter.tex             ← Abstract, TOC, LOF, LOT,... (edit as needed)
│   ├── placeholder_logo.png        ← Replace with your school's logo
│   ├── stemtemplate.sty            ← Packages (don't edit)
│   ├── titlepage_abstract.tex      ← Title page layouts (don't edit)
│   ├── titlepage_compact.tex
│   └── titlepage_standard.tex
├── figures/                        ← Place your images here
│   └── .gitkeep                    ← Placeholder file
├── sections/                       ← Place your content files here
│   └── .gitkeep                    ← Placeholder file
├── .gitignore                      ← Used by GitHub
├── LICENCSE                        ← MIT license
├── main.tex                        ← Edit metadata here, compile this file
└── README.md                       ← Read this for instructions
```
 
---
 
## Metadata
 
All settings are controlled from the top of `main.tex`. The full metadata block is shown below with every available field:
 
```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% METADATA (EDIT FOR EACH SUBMISSION)
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\newcommand{\metaAssignmentTitle}{Assignment Title}
\newcommand{\metaStudentName}{Your Name}
\newcommand{\metaStudentNumber}{123456789}
\newcommand{\metaStudentEmail}{email@my.yorku.ca}
\newcommand{\metaPartners}{}                                              % "Jane Doe & 123456789\\John Doe & 123456789..."
\newcommand{\metaUniversity}{e.g., York University}
\newcommand{\metaFaculty}{e.g., Lassonde School of Engineering}
\newcommand{\metaDepartment}{e.g., Earth \& Space Science \& Engineering} % Empty to remove
\newcommand{\metaCourseCode}{Course Code}
\newcommand{\metaCourseName}{Course Name}
\newcommand{\metaInstructor}{Dr. Professor}
\newcommand{\metaDate}{Due date}

% TITLE PAGE ----------------------------------------------
\newcommand{\metaTitlePage}{standard}                   % standard, abstract, or compact
\newcommand{\metaLogoPath}{assets/placeholder_logo.png} % Empty to remove
\newcommand{\metaLogoLocation}{default}                 % default or york

% BIBLIOGRAPHY --------------------------------------------
\newcommand{\metaBibFile}{references.bib} % Change to reference file name
\newcommand{\metaBibStyle}{ieee}          % e.g., ieee, apa, etc.
\newcommand{\metaShowBackref}{true}       % true or false (shows page back-references in bibliography)

% FONT & SPACING ------------------------------------------
\newcommand{\metaSerifFont}{}          % Empty = IBM Plex Serif, or any system font name (e.g., Georgia)
\newcommand{\metaSansFont}{}           % Empty = IBM Plex Sans, or any system font name (e.g., Arial)
\newcommand{\metaDefaultFont}{sans}    % sans or serif (selects which font family is used for body text)
\newcommand{\metaLineSpacing}{onehalf} % single, onehalf, or double (changes line spacing)

% COLOURS -------------------------------------------------
% Input custom colour, built-in colour, or hex-code (e.g., #003366)
\newcommand{\metaThemeColour}{} % Theme colour, controls: headings, rules, boxes
\newcommand{\metaLinkColour}{}  % Internal links colour, leave empty to use theme colour
\newcommand{\metaCiteColour}{}  % Citations colour, leave empty to use theme colour
\newcommand{\metaUrlColour}{}   % URL colour, leave empty to use theme colour

% EQUATIONS, FIGURES, TABLES NUMBERED BY SECTION ----------
\newcommand{\metaNumberEquations}{false}  % true or false
\newcommand{\metaNumberFigures}{false}    % true or false
\newcommand{\metaNumberTables}{false}     % true or false
\newcommand{\metaNumberTheorems}{false}   % true or false
\newcommand{\metaNumberProblems}{false}   % true or false
\newcommand{\metaNumberAlgorithms}{false} % true or false
\newcommand{\metaNumberListings}{false}   % true or false

% DRAFTING (TRUE FOR FINAL COPY)---------------------------
\newcommand{\metaFinalDraft}{false}  % true or false, general document quality
\newcommand{\metaShowFigures}{false} % true or false, true turns on figures
\newcommand{\metaShowBib}{false}     % true or false, false skips biblatex
\newcommand{\metaUseMinted}{false}   % true or false (Keep false if not using minted; requires -8bit -shell-escape)
 
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% ABSTRACT (EDIT FOR EACH SUBMISSION)
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\newcommand{\metaAbstract}{Type abstract here.}  % Used when metaTitlePage is abstract
```
 
---
 
## Metadata Reference
 
### Submission Information
 
| Field | Description |
|---|---|
| `\metaAssignmentTitle` | Assignment or document title shown on the title page |
| `\metaStudentName` | Your full name |
| `\metaStudentNumber` | Your student number |
| `\metaStudentEmail` | Your university email address |
| `\metaPartners` | Group partners as `Name & Number\\Name & Number`. Leave empty for solo submissions |
| `\metaUniversity` | University name |
| `\metaFaculty` | Faculty name |
| `\metaDepartment` | Department name. Leave empty to omit |
| `\metaCourseCode` | Course code, always shown in the page header |
| `\metaCourseName` | Full course name, used by the smart header collision logic |
| `\metaInstructor` | Instructor name |
| `\metaDate` | Submission or due date |
 
### Title Page
 
| Field | Options | Description |
|---|---|---|
| `\metaTitlePage` | `standard` | Full title page with all fields |
| | `abstract` | Same as standard but includes `\metaAbstract` below the title block |
| | `compact` | Condensed single-page layout |
| `\metaLogoPath` | Path to logo image. Leave empty to omit |
| `\metaLogoLocation` | `default`, `york` | Changes the location of the logo from `\metaLogoPath` in the `standard` title page |
|---|---|---|
| `\metaAbstract` | any text | Abstract text used when `\metaTitlePage` is set to `abstract` |
 
### Bibliography
 
| Field | Options | Description |
|---|---|---|
| `\metaBibFile` | filename | Name of your `.bib` reference file |
| `\metaBibStyle` | `ieee`, `apa` | Citation and bibliography style |
| `\metaShowBackref` | `true`, `false` | Show page numbers where each entry was cited |

### Font & Spacing
 
| Field | Options | Description |
|---|---|---|
| `\metaSerifFont` | empty (default serif font), `Georgia`, etc. | Serif font selection |
| `\metaSansFont` | empty (default sans-serif font), `Arial`, etc. | Sans-serif font selection |
| `\metaDefaultFont` | `sans`, `serif` | Document body font based on `\metaSerifFont` or `\metaSansFont` |
| `\metaLineSpacing` | `single`, `onehalf`, `double` | Line spacing throughout the document |
 
### Colours
 
Each colour field accepts a hex code with `#` prefix (e.g. `#810001`), any built-in LaTeX colour name (e.g. `red`), or any custom colour defined in the template (e.g. `LassondeNavy`). Leave any field empty to fall back to the default.
 
| Field | Default | Description |
|---|---|---|
| `\metaThemeColour` | `DefaultBlue` | Primary accent colour for headings, rules, and boxes |
| `\metaLinkColour` | theme colour | Colour for internal cross-references and hyperlinks |
| `\metaCiteColour` | theme colour | Colour for citation references |
| `\metaUrlColour` | theme colour | Colour for URLs and bibliography back-references |
 
Built-in custom colours: `DefaultBlue` (`#1B4F8A`), `LassondeNavy` (`#003366`), `YorkRedDark` (`#810001`), `ScienceSkyBlueDark` (`#065C87`).
 
### Numbering by Section
 
When set to `true`, floats and environments are numbered relative to their section (e.g. Figure 2.1). When set to `false`, they are numbered continuously through the whole document (e.g. Figure 3).
 
| Field | Affects |
|---|---|
| `\metaNumberEquations` | `equation` and `reaction` environments |
| `\metaNumberFigures` | `figure` environments |
| `\metaNumberTables` | `table` environments |
| `\metaNumberTheorems` | All theorem environments |
| `\metaNumberProblems` | `problem` environments |
| `\metaNumberAlgorithms` | `algorithm` environments |
| `\metaNumberListings` | `listing` environments (Code) |

### Drafting
 
Set to `true` before a final draft. Only set `minted` to `true` if properly set up.
 
| Field | Options | Description |
|---|---|---|
| `\metaFinalDraft` | `true`, `false` | Optimal settings |
| `\metaShowFigures` | `true`, `false` | Displays images and problem environments |
| `\metaShowBib` | `true`, `false` | Shows citations and bibliography |
| `\metaUseMinted` | `true`, `false` | `minted` package use |
 
---
 
## Logo
 
The faculty logo is not included in this repository. Download the official logo from the [York University Brand Assets page](https://www.yorku.ca/brand/assets-downloads/faculty-assets/) and place it in `assets/`. Then update `\metaLogoPath` in the metadata:
 
```latex
\newcommand{\metaLogoPath}{assets/placeholder_logo.png}
```
 
Leave it empty to display no logo.
 
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
