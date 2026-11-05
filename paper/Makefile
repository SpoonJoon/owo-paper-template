LATEXMK ?= latexmk
BIBTEX ?= bibtex
PDFLATEX ?= pdflatex
PYTHON ?= python3
MAIN ?= main

.PHONY: all paper clean distclean

all: paper

paper:
	$(PDFLATEX) -interaction=nonstopmode -halt-on-error $(MAIN).tex
	-$(BIBTEX) $(MAIN)
	$(PDFLATEX) -interaction=nonstopmode -halt-on-error $(MAIN).tex
	$(PDFLATEX) -interaction=nonstopmode -halt-on-error $(MAIN).tex

clean:
	ls $(MAIN)* | grep -v ".tex" | grep -v ".bib" | xargs rm -f
	rm -f *.bak *~

distclean: clean
	rm -f $(MAIN).pdf

