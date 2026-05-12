# LaTeX Assignment Template
 
A LaTeX assignment template originally created for York University STEM students but is usable by anyone looking for an assignment template. All configuration is done through a single metadata block at the top of `main.tex`, no need to edit any other file for standard use.
 
---
 
## Two Versions
 
This template comes in two versions:
 
| Version | File | Best for |
|---|---|---|
| **Full** | `stemtemplate.sty` | Local compilation in TeXstudio or similar |
| **Overleaf** | `stemtemplate-overleaf.sty` | Collaborating on Overleaf |
 
The Overleaf version is a leaner variant of the full template. It loads fewer packages by default and strips non-essential formatting to keep Overleaf compile times short. Heavy packages like `tikz`, `pgfplots`, and `circuitikz` are commented out and can be uncommented when needed for a specific project.
 
> **Overleaf template:** https://github.com/TylerBignell/LaTeX-AssignmentTemplate-Overleaf
 
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
├── assets/
│   ├── stemtemplate.sty            ← Full template (don't edit)
│   ├── titlepage_standard.tex      ← Title page layouts (don't edit)
│   ├── titlepage_abstract.tex
│   ├── titlepage_compact.tex
│   ├── example.tex                 ← Example file showing all features
│   └── example.pdf                 ← Compiled example
├── figures/                        ← Place your images here
├── main.tex                        ← Edit metadata here, compile this file
└── references.bib                  ← Your bibliography entries
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
\newcommand{\metaPartners}{}   % "Jane Doe & 123456789\\John Doe & 123456789"
\newcommand{\metaUniversity}{York University}
\newcommand{\metaFaculty}{Lassonde School of Engineering}
\newcommand{\metaDepartment}{Department Name}  % Leave empty to omit
\newcommand{\metaCourseCode}{Course Code}
\newcommand{\metaCourseName}{Course Name}
\newcommand{\metaInstructor}{Dr. Professor}
\newcommand{\metaDate}{Due date}
\newcommand{\metaLogoPath}{assets/logo.png}    % Leave empty to omit
 
% TITLE PAGE
\newcommand{\metaTitlePage}{standard}          % standard, abstract, or compact
 
% BIBLIOGRAPHY
\newcommand{\metaBibFile}{references.bib}
\newcommand{\metaBibStyle}{ieee}               % ieee or apa
\newcommand{\metaShowBackref}{true}            % true or false
\newcommand{\metaShowUnusedCitations}{false}   % true or false

% FONT
\newcommand{\metaSerifFont}{}         % Empty = IBM Plex Serif, or any system font name (e.g., Georgia)
\newcommand{\metaSansFont}{}          % Empty = IBM Plex Sans, or any system font name (e.g., Arial)
\newcommand{\metaDefaultFont}{sans}   % sans or serif (selects which font family is used for body text)
 
% MISC
\newcommand{\metaDefaultFont}{sans}            % sans or serif
\newcommand{\metaLineSpacing}{onehalf}         % single, onehalf, or double
\newcommand{\metaShowTodo}{true}               % true or false
\newcommand{\metaWatermarkText}{}              % Leave empty for no watermark
\newcommand{\metaWatermarkScale}{1}            % Scale of watermark text
 
% COLOURS (hex code e.g. #003366, colour name e.g. red, or leave empty for default)
\newcommand{\metaThemeColour}{}   % Headings, rules, boxes — defaults to DefaultBlue
\newcommand{\metaLinkColour}{}    % Internal links — leave empty to use theme colour
\newcommand{\metaCiteColour}{}    % Citations — leave empty to use theme colour
\newcommand{\metaUrlColour}{}     % URLs — leave empty to use theme colour
 
% NUMBERING BY SECTION
\newcommand{\metaNumberEquations}{true}    % true or false
\newcommand{\metaNumberFigures}{true}      % true or false
\newcommand{\metaNumberTables}{true}       % true or false
\newcommand{\metaNumberTheorems}{true}     % true or false
\newcommand{\metaNumberProblems}{true}     % true or false
\newcommand{\metaNumberAlgorithms}{true}   % true or false
\newcommand{\metaNumberListings}{true}     % true or false
 
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
| `\metaLogoPath` | Path to logo image. Leave empty to omit |
 
### Title Page
 
| Field | Options | Description |
|---|---|---|
| `\metaTitlePage` | `standard` | Full title page with all fields |
| | `abstract` | Same as standard but includes `\metaAbstract` below the title block |
| | `compact` | Condensed single-page layout |
| `\metaAbstract` | any text | Abstract text used when `\metaTitlePage` is set to `abstract` |
 
### Bibliography
 
| Field | Options | Description |
|---|---|---|
| `\metaBibFile` | filename | Name of your `.bib` reference file |
| `\metaBibStyle` | `ieee`, `apa` | Citation and bibliography style |
| `\metaShowBackref` | `true`, `false` | Show page numbers where each entry was cited |
| `\metaShowUnusedCitations` | `true`, `false` | Show all bib entries regardless of whether they were cited |

### Font
 
| Field | Options | Description |
|---|---|---|
| `\metaSerifFont` | empty (default serif font), `Georgia`, etc. | Serif font selection |
| `\metaSansFont` | empty (default sans-serif font), `Arial`, etc. | Sans-serif font selection |
| `\metaDefaultFont` | `sans`, `serif` | Document body font based on `\metaSerifFont` or `\metaSansFont` |
 
### MISC.
 
| Field | Options | Description |
|---|---|---|
| `\metaLineSpacing` | `single`, `onehalf`, `double` | Line spacing throughout the document |
| `\metaShowTodo` | `true`, `false` | Show or hide all `\todo{}` notes globally |
| `\metaWatermarkText` | any text or empty | Diagonal watermark on every page. Leave empty to disable |
| `\metaWatermarkScale` | number | Scale factor for the watermark. Default is `1` |
 
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
| `\metaNumberEquations` | `equation` environments |
| `\metaNumberFigures` | `figure` environments |
| `\metaNumberTables` | `table` environments |
| `\metaNumberTheorems` | All theorem environments |
| `\metaNumberProblems` | `problem` environments |
| `\metaNumberAlgorithms` | `algorithm` environments |
| `\metaNumberListings` | Code listings |
 
---
 
## Logo
 
The faculty logo is not included in this repository. Download the official logo from the [York University Brand Assets page](https://www.yorku.ca/brand/assets-downloads/faculty-assets/) and place it in `assets/`. Then update `\metaLogoPath` in the metadata:
 
```latex
\newcommand{\metaLogoPath}{assets/LASS_yu_PRIMARY_hor_RGB.png}
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
