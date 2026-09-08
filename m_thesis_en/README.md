# English Master's Thesis Template

## Writing your thesis

Edit `mthesis.tex` to fill in the cover information and write your thesis.

The files in `chapters/` contain **examples for demonstrating the layout only**.
Delete these example files when writing your actual thesis, remove their
`\input{chapters/...}` lines from `mthesis.tex`, and write your own chapters
directly in `mthesis.tex`. Keep `\appendix` only if your thesis has appendices.
Also replace the sample abstract and acknowledgements in `mthesis.tex`.

No changes to `pethesis.sty` or `latexmkrc` are needed for normal writing.
Add your bibliography entries to `reference.bib` and replace its example entries.

## Compiling on Overleaf

1. Create a new Overleaf project and upload the contents of this directory.
   Place `mthesis.tex`, `pethesis.sty`, `latexmkrc`, `reference.bib`, and
   `waseda_logo.pdf` at the project root. Keep the `chapters/` directory if you
   want to compile the sample before replacing it. Do not upload `build/` or
   `output/`.
2. Set the **Main document** to `mthesis.tex`.
3. Set the **Compiler** to **LaTeX**. The included `latexmkrc` configures
   pLaTeX followed by dvipdfmx to produce the PDF. Do not select pdfLaTeX,
   XeLaTeX, or LuaLaTeX for this template.
4. Select a current **TeX Live version** and click **Recompile**. The template
   no longer depends on the obsolete `tocstyle` package or requires the
   `2021 (Legacy)` setting. It has been tested locally with TeX Live 2023;
   Overleaf TeX Live 2026 has not yet been tested.
5. If you are replacing an older template in an existing project, use
   **Recompile from scratch** to clear cached compilation files.

Keep `latexmkrc` at the Overleaf project root so that its settings are loaded.

## Compiling locally

Install a TeX distribution with Japanese typesetting support, such as a full
TeX Live installation or MacTeX. Required components include `latexmk`,
`platex`, `pbibtex`, `dvipdfmx`, `jsclasses`, `fancyhdr`, `etoolbox`, `PSNFSS`,
`graphicx`, `url`, `float`, and `amsmath`. Save your source files as UTF-8.

Open a terminal in this template directory and run:

```sh
latexmk -outdir=build mthesis.tex
```

The compiled PDF is saved as `build/mthesis.pdf`. Run the same command after
editing; latexmk automatically runs the necessary compilation and bibliography
steps.

If your personal latexmk settings interfere with compilation, explicitly load
only this template's configuration:

```sh
latexmk -norc -r latexmkrc -outdir=build mthesis.tex
```

### VS Code with LaTeX Workshop

Open this template directory in VS Code and use a latexmk recipe with these
arguments:

```json
["-cd", "-outdir=build", "%DOC%"]
```

Build `mthesis.tex` as the main document. Avoid recipes that force `-pdf`,
`-xelatex`, or `-lualatex`, as they override the intended pLaTeX workflow.

The PDF in `output/pdf/` is a sample snapshot. Local compilation updates
`build/mthesis.pdf`, not that snapshot.
