# Master thesis (English)

## If you are using overleaf

Set the compiler to `LaTex`.

## If you are using vscode

Here is an example of `settings.json`.

```json
{
    // ---------- Language ----------

    "[tex]": {
        // スニペット補完中にも補完を使えるようにする
        "editor.suggest.snippetsPreventQuickSuggestions": false,
        // インデント幅を2にする
        "editor.tabSize": 2
    },

    "[latex]": {
        // スニペット補完中にも補完を使えるようにする
        "editor.suggest.snippetsPreventQuickSuggestions": false,
        // インデント幅を2にする
        "editor.tabSize": 2
    },

    "[bibtex]": {
        // インデント幅を2にする
        "editor.tabSize": 2
    },


    // ---------- LaTeX Workshop ----------

    // 使用パッケージのコマンドや環境の補完を有効にする
    "latex-workshop.intellisense.package.enabled": true,

    // 生成ファイルを削除するときに対象とするファイル
    // デフォルト値に "*.synctex.gz" を追加
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

    // 生成ファイルを "out" ディレクトリに吐き出す
    "latex-workshop.latex.outDir": "out",

    // ビルドのレシピ
    "latex-workshop.latex.recipes": [
        {
            "name": "latexmk",
            "tools": [
                "latexmk"
            ]
        },
    ],

    // ビルドのレシピに使われるパーツ
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
