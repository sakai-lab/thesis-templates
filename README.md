# Thesis Templates

LaTeX templates for bachelor's and master's theses and thesis abstracts at the Sakai Laboratory, Waseda University.

## Choose a template

| Directory | Document | Main file | Instructions |
|---|---|---|---|
| `b_thesis_en/` | Bachelor's thesis in English | `bthesis.tex` | [README](b_thesis_en/README.md) |
| `b_thesis_ja/` | Bachelor's thesis in Japanese | `bthesis.tex` | [README](b_thesis_ja/README.md) |
| `m_thesis_en/` | Master's thesis in English | `mthesis.tex` | [README](m_thesis_en/README.md) |
| `m_thesis_ja/` | Master's thesis in Japanese | `mthesis.tex` | [README](m_thesis_ja/README.md) |
| `b_abstract/` | Bachelor's thesis abstract | `abs.tex` | Edit `abs.tex` |
| `m_abstract/` | Master's thesis abstract | `abs.tex` | Edit `abs.tex` |

Each directory includes its own `latexmkrc`. Both English and Japanese templates use **pLaTeX → dvipdfmx**.

The four full thesis templates have been tested locally with **TeX Live 2023** and on **Overleaf with TeX Live 2026**. They do not require the old `2021 (Legacy)` setting. This verification statement does not cover the two abstract templates.

## Compiling on Overleaf

1. Create a new Overleaf project and upload the **contents of your chosen template directory**.
2. Keep `latexmkrc`, the main `.tex` file, and the accompanying style and bibliography files at the project root. For a full thesis template, also include `waseda_logo.pdf` and the `chapters/` directory when compiling the sample. Do not upload `build/` or `output/`.
3. Set **Main document** to the file listed in the table above.
4. Set **Compiler** to **LaTeX**. The included `latexmkrc` runs pLaTeX and dvipdfmx. Do not select pdfLaTeX, XeLaTeX, or LuaLaTeX.
5. For the four full thesis templates, select **TeX Live 2026** and click **Recompile**.

When replacing an older template in an existing project, use **Recompile from scratch** to clear cached compilation files.

## Compiling locally

Install a TeX distribution with Japanese typesetting support, such as a full TeX Live installation or MacTeX. This is required for the English templates too. Save source files as UTF-8.

Open a terminal in the chosen template directory and run `latexmk` with its main file. For example:

```sh
cd b_thesis_en
latexmk -outdir=build bthesis.tex
```

For a master's thesis, use `mthesis.tex`; for an abstract, use `abs.tex`. The generated PDF is saved in `build/`.

If personal latexmk settings interfere with compilation, explicitly load only the template configuration:

```sh
latexmk -norc -r latexmkrc -outdir=build bthesis.tex
```

The PDFs in the full thesis templates' `output/pdf/` directories are sample snapshots. Local compilation updates `build/`, not those snapshots.

## Writing your document

For a full thesis, edit `bthesis.tex` or `mthesis.tex` to replace the cover information, abstract, acknowledgements and body text.

The files in `chapters/` are **formatting examples only**. Delete them and their corresponding `\input{chapters/...}` lines when writing your thesis, then write your chapters directly in the main `.tex` file. Keep `\appendix` only if needed. The example results and journal/conference references are fictional.

Maintain your references in `reference.bib`. For normal writing, you do not need to edit `pethesis.sty` or `latexmkrc`.

For an abstract, edit `abs.tex` and the bibliography file specified by its `\bibliography{...}` command.

See the individual thesis READMEs for detailed instructions, including VS Code configuration.

---

# 卒業論文・修士論文テンプレート

早稲田大学酒井研究室の卒業論文，修士論文および論文概要書のための LaTeX テンプレートです．

## テンプレートの選択

| ディレクトリ | 文書 | メインファイル | 使用説明 |
|---|---|---|---|
| `b_thesis_en/` | 英語の卒業論文 | `bthesis.tex` | [README](b_thesis_en/README.md) |
| `b_thesis_ja/` | 日本語の卒業論文 | `bthesis.tex` | [README](b_thesis_ja/README.md) |
| `m_thesis_en/` | 英語の修士論文 | `mthesis.tex` | [README](m_thesis_en/README.md) |
| `m_thesis_ja/` | 日本語の修士論文 | `mthesis.tex` | [README](m_thesis_ja/README.md) |
| `b_abstract/` | 卒業論文概要書 | `abs.tex` | `abs.tex` を編集 |
| `m_abstract/` | 修士論文概要書 | `abs.tex` | `abs.tex` を編集 |

各ディレクトリには `latexmkrc` が同梱されています．英語版と日本語版のいずれも **pLaTeX → dvipdfmx** を使用します．

4 種類の論文本体のテンプレートは，ローカルの **TeX Live 2023** と **Overleaf の TeX Live 2026** で動作を確認しています．従来の `2021 (Legacy)` 設定は不要です．この動作確認の記述は，2 種類の概要書テンプレートには適用されません．

## Overleaf でのコンパイル方法

1. Overleaf で新しいプロジェクトを作成し，**選択したテンプレートのディレクトリの内容**をアップロードしてください．
2. `latexmkrc`，メインの `.tex` ファイル，付属のスタイルファイルと参考文献ファイルをプロジェクトのルートに配置してください．論文本体のサンプルをコンパイルする場合は，`waseda_logo.pdf` と `chapters/` ディレクトリも含めてください．`build/` と `output/` はアップロードする必要はありません．
3. **Main document** を上の表に示したファイルに設定してください．
4. **Compiler** を **LaTeX** に設定してください．同梱の `latexmkrc` により pLaTeX と dvipdfmx が実行されます．pdfLaTeX，XeLaTeX，LuaLaTeX は選択しないでください．
5. 4 種類の論文本体のテンプレートでは，**TeX Live 2026** を選択し，**Recompile** を実行してください．

既存のプロジェクトで古いテンプレートを置き換える場合は，**Recompile from scratch** を実行してコンパイル用のキャッシュを削除してください．

## ローカル環境でのコンパイル方法

TeX Live のフルインストールや MacTeX など，日本語組版に対応した TeX 環境をインストールしてください．英語版のテンプレートでも必要です．ソースファイルは UTF-8 で保存してください．

ターミナルで選択したテンプレートのディレクトリを開き，メインファイルを指定して `latexmk` を実行してください．例：

```sh
cd b_thesis_en
latexmk -outdir=build bthesis.tex
```

修士論文では `mthesis.tex`，概要書では `abs.tex` を指定してください．生成した PDF は `build/` に保存されます．

個人用の latexmk 設定がコンパイルに干渉する場合は，次のようにテンプレートの設定だけを明示的に読み込んでください．

```sh
latexmk -norc -r latexmkrc -outdir=build bthesis.tex
```

論文本体のテンプレートの `output/pdf/` にある PDF は，あらかじめ生成したサンプルです．ローカルでコンパイルすると `build/` 内のファイルが更新され，これらのサンプルは更新されません．

## 文書の執筆方法

論文本体を執筆する場合は，`bthesis.tex` または `mthesis.tex` を編集し，表紙の情報，概要，謝辞，本文を自分の内容に置き換えてください．

`chapters/` 内のファイルは，**書式を確認するためのサンプルにすぎません**．実際の論文を執筆する際には，これらのファイルと対応する `\input{chapters/...}` の行を削除し，メインの `.tex` ファイルに各章を直接記述してください．`\appendix` は必要な場合にのみ残してください．サンプルの結果と学術論文・会議論文の参考文献は架空のものです．

参考文献は `reference.bib` で管理してください．通常の執筆では，`pethesis.sty` や `latexmkrc` を編集する必要はありません．

概要書の場合は，`abs.tex` と，その `\bibliography{...}` コマンドで指定されている参考文献ファイルを編集してください．

VS Code の設定を含む詳しい使用方法は，各論文テンプレートの README を参照してください．
