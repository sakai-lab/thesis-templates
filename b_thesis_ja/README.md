# 日本語卒業論文テンプレート

## 論文の執筆方法

`bthesis.tex` を編集し，表紙の情報と論文の本文を記入してください．
表紙には，年度・論文種別，日本語タイトル，英語タイトル，所属，指導教員，
学籍番号，氏名を指定します．英語タイトルが不要な場合は `\etitle{}` としてください．仮の値はすべて実際の情報に置き換えてください．

`chapters/` 内のファイルは，**書式を確認するためのサンプルにすぎません**．
実際の論文を執筆する際には，これらのサンプルファイルを削除し，
`bthesis.tex` 内の対応する `\input{chapters/...}` の行も削除してください．
その上で，論文の各章を `bthesis.tex` に直接記述してください．
付録が必要な場合にのみ `\appendix` を残してください．
`bthesis.tex` 内の概要と謝辞も，自分の文章に置き換えてください．
サンプルの評価値と学術論文・会議論文の参考文献は架空のものです．

通常の執筆では，`pethesis.sty` や `latexmkrc` を編集する必要はありません．
参考文献は `reference.bib` に追加し，サンプルの項目を置き換えてください．
このテンプレートでは BibTeX と `unsrt` を使用します．ウェブサイトを引用する場合は
`@misc` を使い，URL を `howpublished = {\url{...}}` に記述してください．

## Overleaf でのコンパイル方法

1. Overleaf で新しいプロジェクトを作成し，このディレクトリの内容をアップロードしてください．
   `bthesis.tex`，`pethesis.sty`，`latexmkrc`，`reference.bib`，`waseda_logo.pdf` は，
   プロジェクトのルートに配置してください．サンプルをコンパイルする場合は，
   `chapters/` ディレクトリもそのままアップロードしてください．
   `build/` と `output/` はアップロードする必要はありません．
2. **Main document** を `bthesis.tex` に設定してください．
3. **Compiler** を **LaTeX** に設定してください．同梱の `latexmkrc` により，
   pLaTeX と dvipdfmx を順に実行して PDF を生成します．
   このテンプレートでは pdfLaTeX，XeLaTeX，LuaLaTeX を選択しないでください．
4. **TeX Live version** で現行のバージョンを選び，**Recompile** を実行してください．
   この改訂版では，旧版で指定されていた `2021 (Legacy)` の設定は不要です．
   ローカルの TeX Live 2023 で動作を確認しています．
   Overleaf の TeX Live 2026 でも動作を確認しています．
5. 既存のプロジェクトで古いテンプレートを置き換えた場合は，
   **Recompile from scratch** を実行し，コンパイル用のキャッシュを削除してください．

設定が読み込まれるよう，`latexmkrc` は必ず Overleaf プロジェクトのルートに配置してください．

## ローカル環境でのコンパイル方法

TeX Live のフルインストールや MacTeX など，日本語組版に対応した TeX 環境を
インストールしてください．必要な構成要素には，`latexmk`，`platex`，`pbibtex`，
`dvipdfmx`，`jsclasses`，`pxchfon`，原ノ味フォント，`fancyhdr`，`fancybox`，
`etoolbox`，`PSNFSS`，`graphicx`，`url`，`float`，`amsmath`，`amssymb` があります．
ソースファイルは UTF-8 で保存してください．
日本語フォントには原ノ味フォントのプリセットを使用し，PDF に埋め込みます．
校徽は PDF 形式で同梱しているため，コンパイル時に EPS 変換ツールは必要ありません．

ターミナルでこのテンプレートのディレクトリを開き，次のコマンドを実行してください．

```sh
latexmk -outdir=build bthesis.tex
```

生成した PDF は `build/bthesis.pdf` に保存されます．
編集後も同じコマンドを実行してください．latexmk が，必要なコンパイルと
参考文献の処理を自動的に実行します．

個人用の latexmk 設定がコンパイルに干渉する場合は，次のコマンドで
このテンプレートの設定だけを明示的に読み込んでください．

```sh
latexmk -norc -r latexmkrc -outdir=build bthesis.tex
```

### VS Code と LaTeX Workshop を使用する場合

VS Code でこのテンプレートのディレクトリを開き，latexmk のレシピに
次の引数を指定してください．

```json
["-cd", "-outdir=build", "%DOC%"]
```

`bthesis.tex` をメインファイルとしてコンパイルしてください．
`-pdf`，`-xelatex`，`-lualatex` を強制するレシピは，想定している pLaTeX の
処理手順を上書きするため，使用しないでください．

`output/pdf/` 内の PDF は，あらかじめ生成したサンプルです．
ローカルでのコンパイルでは `build/bthesis.pdf` が更新され，
`output/pdf/` 内のサンプルは更新されません．

---

# Japanese Undergraduate Thesis Template

## Writing your thesis

Edit `bthesis.tex` to fill in the cover information and write your thesis.
The cover includes the academic year and thesis type, Japanese title, optional
English title, affiliation, advisor, student number and author name.
Use `\etitle{}` to omit the English title.
Replace all placeholder values with your actual information.

The files in `chapters/` contain **examples for demonstrating the layout only**.
Delete these example files when writing your actual thesis, remove their
`\input{chapters/...}` lines from `bthesis.tex`, and write your own chapters
directly in `bthesis.tex`. Keep `\appendix` only if your thesis has appendices.
Also replace the sample abstract and acknowledgements in `bthesis.tex`.
The example scores and article/conference references are fictional.

No changes to `pethesis.sty` or `latexmkrc` are needed for normal writing.
Add your bibliography entries to `reference.bib` and replace its example entries.
The template uses traditional BibTeX with `unsrt`; for websites, use `@misc`
and place the address in `howpublished = {\url{...}}`.

## Compiling on Overleaf

1. Create a new Overleaf project and upload the contents of this directory.
   Place `bthesis.tex`, `pethesis.sty`, `latexmkrc`, `reference.bib`, and
   `waseda_logo.pdf` at the project root. Keep the `chapters/` directory if you
   want to compile the sample before replacing it. Do not upload `build/` or
   `output/`.
2. Set the **Main document** to `bthesis.tex`.
3. Set the **Compiler** to **LaTeX**. The included `latexmkrc` configures
   pLaTeX followed by dvipdfmx to produce the PDF. Do not select pdfLaTeX,
   XeLaTeX, or LuaLaTeX for this template.
4. Select a current **TeX Live version** and click **Recompile**. This revision
   does not require the original repository's `2021 (Legacy)` setting.
   It has been tested locally with TeX Live 2023 and on Overleaf with
   TeX Live 2026.
5. If replacing an older template in an existing project, use
   **Recompile from scratch** to clear cached compilation files.

Keep `latexmkrc` at the Overleaf project root so that its settings are loaded.

## Compiling locally

Install a TeX distribution with Japanese typesetting support, such as a full
TeX Live installation or MacTeX. Required components include `latexmk`,
`platex`, `pbibtex`, `dvipdfmx`, `jsclasses`, `pxchfon`, the Harano Aji fonts,
`fancyhdr`, `fancybox`, `etoolbox`, `PSNFSS`, `graphicx`, `url`, `float`,
`amsmath`, and `amssymb`. Save your source files as UTF-8.
Japanese fonts are embedded using the Harano Aji preset. The logo is supplied
as PDF, so no EPS converter is required during compilation.

Open a terminal in this template directory and run:

```sh
latexmk -outdir=build bthesis.tex
```

The compiled PDF is saved as `build/bthesis.pdf`. Run the same command after
editing; latexmk automatically runs the necessary compilation and bibliography
steps.

If your personal latexmk settings interfere with compilation, explicitly load
only this template's configuration:

```sh
latexmk -norc -r latexmkrc -outdir=build bthesis.tex
```

### VS Code with LaTeX Workshop

Open this template directory in VS Code and use a latexmk recipe with these
arguments:

```json
["-cd", "-outdir=build", "%DOC%"]
```

Build `bthesis.tex` as the main document. Avoid recipes that force `-pdf`,
`-xelatex`, or `-lualatex`, as they override the intended pLaTeX workflow.

The PDF in `output/pdf/` is a sample snapshot. Local compilation updates
`build/bthesis.pdf`, not that snapshot.
