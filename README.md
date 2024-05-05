# thesis-templates
Templates of B and M thesis

# When you write a thesis in Japanese

make `latexmkrc` on the current dir.

```latexmkrc
$latex = 'platex';
$bibtex = 'pbibtex';
$dvipdf = 'dvipdfmx %O -o %D %S';
$makeindex = 'mendex %O -o %D %S';
$pdf_mode = 3; 
$ENV{TZ} = 'Asia/Tokyo';
$ENV{OPENTYPEFONTS} = '/usr/share/fonts//:';
$ENV{TTFONTS} = '/usr/share/fonts//:';
```

On Overleaf, set as below.

* Compiler: LaTeX
* TeX Live version: 2021 (Legacy)
