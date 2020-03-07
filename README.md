# LaTeX CV/Résumé

Fork of [AltaCV](https://github.com/liantze/AltaCV).

<!--
## Samples

This is how the re-created résumé looks like ([view/open on Overleaf](https://www.overleaf.com/latex/examples/recreating-business-insiders-cv-of-marissa-mayer-using-altacv/gtqfpbwncfvp)):

<img src="mmayer.png" alt="Marissa Mayer's résumé, re-created with AltaCV" width="600px">

Though if you're creating your own CV/résumé, you'd probably prefer using the basic template ([view/open on Overleaf](https://www.overleaf.com/latex/templates/altacv-template/trgqjpwnmtgv)):

<img src="sample.png" alt="sample barebones AltaCV template" width="600px">
-->

## Compilation

compile with:

```sh
pdflatex  -synctex=1 -interaction=nonstopmode -file-line-error -recorder -output-directory="."  "main.tex"
```

in the miktex portable command line, use the following:

```sh
cd "C:\Users\Faris\Dropbox\Career\CV\CV - Faris Hijazi\"

del "./main.pdf" && perl.exe c:\texlive\2019\texmf-dist\scripts\latexmk\latexmk.pl -synctex=1 -interaction=nonstopmode -file-line-error -pdf "-outdir=." "./main" -f || "./main.pdf"
```

## Requirements and Compilation

- pdflatex + biber + pdflatex
- AltaCV uses [`fontawesome`](http://www.ctan.org/pkg/fontawesome) and [`academicons`](http://www.ctan.org/pkg/academicons); they're included in both TeX Live 2016 and MikTeX 2.9.
- Loading `academicons` is optional: enable it by adding the `academicons` option to `\documentclass`.
- Use the `normalphoto` option to get a normal (i.e. non-circular) photo.
- Use the `ragged2d` option to activate hyphenations while keeping text left-justified; line endings will thus be less jagged and more aesthetically pleasing.
- Can now be compiled with pdflatex, XeLaTeX and LuaLaTeX!
- However if you're using `academicons`, you _must_ use either XeLaTeX or LuaLaTeX. If the doc then compiles but the icons don't show up in the output PDF, try compiling with LuaLaTeX instead.
- The samples here use the [Lato](http://www.latofonts.com/lato-free-fonts/) font.
