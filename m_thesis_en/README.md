# Master thesis (English)

## If you are using overleaf

Set the compiler to `LaTex`.

## If you are using vscode

Here is an example of `settings.json`.

```json
{
    "[tex]": {
        "editor.suggest.snippetsPreventQuickSuggestions": false,
        "editor.tabSize": 2
    },

    "[latex]": {
        "editor.suggest.snippetsPreventQuickSuggestions": false,
        "editor.tabSize": 2
    },

    "[bibtex]": {
        "editor.tabSize": 2
    },

    "latex-workshop.intellisense.package.enabled": true,

    "latex-workshop.latex.clean.fileTypes": [
        "*.aux",
        "*.bbl",
        "*.blg",
        "*.idx",
        "*.ind",
        "*.lof",
        "*.lot",
        "*.out",
        "*.toc",
        "*.acn",
        "*.acr",
        "*.alg",
        "*.glg",
        "*.glo",
        "*.gls",
        "*.ist",
        "*.fls",
        "*.log",
        "*.fdb_latexmk",
        "*.snm",
        "*.nav",
        "*.dvi",
        "*.synctex.gz"
    ],

    "latex-workshop.latex.outDir": "out",

    "latex-workshop.latex.recipes": [
        {
            "name": "latexmk",
            "tools": [
                "latexmk"
            ]
        },
    ],

    "latex-workshop.latex.tools": [
        {
            "name": "latexmk",
            "command": "latexmk",
            "args": [
                "-silent",
                "-outdir=%OUTDIR%",
                "%DOC%"
            ],
        },
    ],
}
```
