# List of Interested LaTeX Packages

## Macro Packages

### Programming

Programming in TeX

- `parselines` Simple input line parser
- `tokstools` Match, capture, and replace tokens using PEG-type grammars
- `switch` Constant-time expandable switch/case

Execute or bridge to foreign languages

- `bashful`
- `lt3luabridge` Execute Lua code in any TeX engine that exposes the shell
- `runcode` Execute foreign source code and embed the result in the pdf file

(see also CTAN topics [Callback], [Exec foreign], and [External code])

For fun

- `lisp-on-tex` LISP interpreter written in TeX macros, which supports static scoping, dynamic typing, and eager evaluation

Historic

- `texapi` Format-independent `etoolbox` (replaced by `l3kernel`)
- `ltxcmds` Utility macros from LaTeX kernel, exported into `ltx@` namespace (replaced by `l3kernel`)
- `letltxmacro` Let assignment for robust or opt-arg LaTeX macros (replaced by `\CopyCommand` in LaTeX kernel)

[Callback]: https://ctan.org/topic/callback
[Exec foreign]: https://ctan.org/topic/exec-foreign
[External code]: https://ctan.org/topic/ext-code

### Demonstration and debugging

- `visualtoks` Typeset token list in TeXbook style, with catcodes in subscript
- `unravel` Watch TeX digest tokens

### Tabular and list

New table implementations

- `keyvaltable` Re-usable table layouts separating content and presentation
- `tabular2` Table typesetting rewritten in `expl3` and `l3draw`, separating content and style
- `tabularray`
- `nicematrix`

Add-ons to the classic `tabular` + `array` ecosystem

- `fcolumn` Adds column type `F/f` for aligning text and currency amounts, and`\sumline` command.
- `boldline` Variable-width h/v-lines in tabular. Contained in `shipunov` bundle
- `hhline` Better horizontal lines in `tabular`s and `array`s
- `ehhline` Extend the `\hhline` command

List

- `hlist` Provides `hlist` environment in which `\hitem` starts a horizontal and columned item. Doc is in French only.
- `enumext` Multi-column enumerate list
- `tasks` Horizontally columned lists

### Misc

- `keytheorems` good alternative to `thmtools`
- `svg-animate` based on tikz\
  https://github.com/renard/svg-animate

### Misc - old

Color management

- `spotxcolor` spot color support for `xcolor`

### Misc (in old format)

| Name              | Category            | Description                                                  |
| ----------------- | ------------------- | ------------------------------------------------------------ |
| `wiki`            | text markup         | Use wiki-style markup                                        |
| `relsize`         | font                | Changes font size relative to current size.                  |
| `savesym`         | font/math           | Redefines and restores name of symbol command                |
|                   |                     |                                                              |
| `nath`            | math                |                                                              |
| `mismath`         | math                | Miscellaneous mathematical macros                            |
| `nicematrix`      | math                | Improved typesetting of mathematical matrices with TikZ      |
| `systeme`         | math                | Provides a more intuitive way to enter systems of equations or inequalities. <br />Doc is in French only. |
| `autoaligne`      | math                | Aligns lines of math expressions by operators and relations. <br />Doc is in French only. |
| `mleftright`      | math                | Variants of delimiters that act as maths open/close          |
| `mathpunctspace`  | math                | Controls the space after punctuation in math expressions     |
| `letterswitharrows` | math & pgf        | Arrows over math letters                                     |
|                   |                     |                                                              |
| `flowframe`       | layout              | Create text frames that flow from one to another             |
| `paracol`         | layout              | Multiple columns with texts "in parallel"                    |
| `layouts`         | layout show         | Shows layout of document elements.                           |
| `floatrow`        | layout/float        | Float layouts                                                |
| `marginfix`       | layout/marginal     | A `\marginpar` patch to avoid overfull margins               |
| `extramarks`      | marks               | More marks other than `\markleft` and `\markboth`            |
| `updatemarks`     | marks               | Extract and update marks from boxes |
| `tocdata`         | table of contents   | Add a small amount of data to an entry in `toc`              |
| `fncychap`        | section style       | Seven predefined chapter heading styles                      |
| `centeredline`    | paragraph alignment | Extends latex2e macro`\centerline`                           |
|                   |                     |                                                              |
| `csvsimple`       | data processing     | Lightweight CSV processing including filtering and table generation |
|                   |                     |                                                              |
| `graphbox`        | graphics            | Adds options to `\includegraphicx`                           |
| `smartdiagram`    | graphics/pgf        | Generates (SmartArt-like) diagrams from lists                |
| `pgfgantt`        | graphics/pgf        | Draws Gantt charts                                           |
| `tikzlings`       | graphics/pgf        | Predefined small animals                                     |
|                   |                     |                                                              |
| `beamertheme-tcolorbox` | beamer        | Beamer inner theme reproducing standard beamer blocks in `tcolorbox` |
| `lstaddons`       | code listing        | `listings` add-ons: autogobble and line background           |
|                   |                     |                                                              |
| `changes`         | editorial           | Markup change in text manually                               |
|                   |                     |                                                              |
| `sesamanuel`      | class or template   | Class and package for sesamath books or paper                |
|                   |                     |                                                              |
| `expkv-def`       | key-value           | A key-defining frontend for `expkv`                          |
| `silence`         | compilation/log     | Filters errors and warnings produced by standard macros.     |
| `snapshot`        | compilation         | List the external dependencies                               |
| `hypdoc`          | PDF feature         | Adds more links of references.                               |
| `navigator`       | PDF feature         | format-independent `hyperref`                                |
| `lwarp`           | convert format      | Convert LaTeX output (PDF) to HTML.                          |

- math
  - `minim-math` - OpenType math for Lua(La)TeX

## Font Packages

| Name                  | Category   | Description                                  |
| --------------------- | ---------- | -------------------------------------------- |
| `xcharter`            | font & pkg | Extension of Bitstream Charter fonts         |
| `oldstandard`         | font & pkg | Serif, late 19th to early 20th century style |
| `stickstoo`           | font & pkg | Extra number styles and blackboard bold choices to STIX2 |
| `logix`               | font & pkg | Supplemental Unicode math symbols, esp. used in logic |
| `noto-emoji`          | font       | Google's emoji, Android and Linux only       |
| `twemoji-colr`        | font       | Twitter's emoji                              |

## Documentation Packages

| Name                  | Description            |
| --------------------- | ---------------------- |
| `around-the-bend`     | answered TeX exercises |
| `tex-nutshell`        | summary of TeX features and plain TeX macros |
| `tamethebeast`        | bibtex                 |
| `biblatex-cheatsheet` | biblatex, cheatsheet   |

## Supporting Tools

* [latexindent](https://ctan.org/pkg/latexindent) - a `Perl` script that indents `.tex` (and other) files according to an indentation scheme that the user can modify to suit their taste.
* [TLCockpit](https://ctan.org/pkg/tlcockpit) - A GUI frontend to TeX Live Manager (`tlmgr`), requiring JavaFX
* [ClutTeX](https://ctan.org/pkg/cluttex) - a program to automatically process LaTeX document without clutter working directory with `.aux`, `.log`, etc. files
* `mkjobtexmf` - a `Perl` script that generates a texmf tree for a particular job
* `dviasm` - DVI editing utility
    ```bash
    # convert dvi to human readable contents
    dviasm file.[dvi|xdv] > file.dviasm
    # create dvi
    dviasm file.dviasm -o file.[dvi|xdv]
    ```
- Log filters
  - `texlogsieve`
  - `texlogfilter`
  - `texloganalyser`
