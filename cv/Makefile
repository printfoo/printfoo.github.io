LATEX=xelatex
BIBTEX=bibtex
BIBFILE=bibliography.bib
CV=shanjiang-cv
RS=research-summary
PS=personal-statement
#PDFLATEX=xelatex -file-line-error -interaction=nonstopmode --shell-escape
PDFLATEX=xelatex -file-line-error -halt-on-error

TEXFILES = $(wildcard *.tex) 

.SUFFIXES:	.plot .eps .fig

default: all clean move

all: $(CV).pdf

$(CV).pdf: $(TEXFILES) 
	$(PDFLATEX) $(CV).tex

-dPDFSETTINGS=/screen 
embedcv: $(CV).pdf
	gs -dCompatibilityLevel=1.4 -dCompressFonts=true -dSubsetFonts=true -dNOPAUSE -dBATCH -sDEVICE=pdfwrite -sOutputFile=$(PAPER)_embed.pdf -c ".setpdfwrite <</NeverEmbed [ ]>> setdistillerparams" -f $(CV).pdf

clean:
	rm -f *.dvi *.aux *.ps *~ *.log *.lot *.lof *.toc *.blg *.bbl *.synctex.gz *.out

move:
	mv $(CV).pdf ../
