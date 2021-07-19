# LaTeX CV/Résumé

Fork of [AltaCV](https://github.com/liantze/AltaCV).

<!--
## Samples

This is how the re-created résumé looks like ([view/open on Overleaf](https://www.overleaf.com/latex/examples/recreating-business-insiders-cv-of-marissa-mayer-using-altacv/gtqfpbwncfvp)):

<img src="mmayer.png" alt="Marissa Mayer's résumé, re-created with AltaCV" width="600px">

Though if you're creating your own CV/résumé, you'd probably prefer using the basic template ([view/open on Overleaf](https://www.overleaf.com/latex/templates/altacv-template/trgqjpwnmtgv)):

<img src="sample.png" alt="sample barebones AltaCV template" width="600px">
-->

## Quick basic LaTex setup

This is not the bets setup, you can find some on the web.

```shell script
# method 1 (recommended): texlive method
sudo apt install -y texlive-full texlive-extra-utils xzdec
sudo apt install -y pdflatex texlive texlive-fonts-recommended texlive-fonts-extra
tlmgr init-usertree
sudo tlmgr update --all

# method 2 (not recommended): miktex install from: https://miktex.org/download/
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys D6BC243565B2087BC3F897C9277A7293F59E4889
echo "deb http://miktex.org/download/ubuntu focal universe" | sudo tee /etc/apt/sources.list.d/miktex.list
sudo apt update
sudo apt install -y miktex
sudo apt install -y texlive-bibtex-extra biber
```

## Compilation

compile with:

```sh
# compile short CV
pdflatex  -synctex=1 -interaction=nonstopmode -file-line-error -recorder -output-directory="." -jobname=FarisHijazi_CV_short '\input{main}'
# compile long CV
pdflatex  -synctex=1 -interaction=nonstopmode -file-line-error -recorder -output-directory="." -jobname=FarisHijazi_CV_long '\newcommand{\isverbose}{ON} \input{main}'

```

in the miktex portable (Windows) command line, use the following:

```powershell
cd "C:\Users\Faris\Dropbox\Career\CV\CV - Faris Hijazi\"

del "./main.pdf" || C:\texlive\2019\tlpkg\tlperl\bin\perl.exe c:\texlive\2019\texmf-dist\scripts\latexmk\latexmk.pl -synctex=1 -interaction=nonstopmode -file-line-error -pdf "-outdir=." "./main" -f || "./main.pdf"

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
