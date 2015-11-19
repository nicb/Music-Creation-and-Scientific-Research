#
# $Id: Makefile 152 2015-06-24 04:46:28Z nicb $
#
TARGET=slides.pdf 


PRINTMODE=beamer
DVI=$(TARGET:.pdf=.dvi)
SRC=$(TARGET):.pdf=.dvi)
AUX=$(TARGET):.pdf=.aux)
TOPDIR=../../..
IMAGEDIR=$(TOPDIR)/images
BEAMERDIR=$(TOPDIR)/../latex-templates/beamer/smerm
TEXINPUTS=".:$(BEAMERDIR):$(IMAGEDIR):"
PDFLATEX=TEXINPUTS=$(TEXINPUTS) pdflatex

BIBTEX=bibtex
all: $(TARGET)

$(TARGET):	images

%.pdf:	%.tex
	$(PDFLATEX) '\newcommand{\printmode}{$(PRINTMODE)}\input{$<}'
	$(RM) $@
#	$(BIBTEX) $* 
	$(PDFLATEX) '\newcommand{\printmode}{$(PRINTMODE)}\input{$<}'
	$(RM) $@
	$(PDFLATEX) '\newcommand{\printmode}{$(PRINTMODE)}\input{$<}'

images:
	$(MAKE) -C $(IMAGEDIR) -$(MAKEFLAGS)

distclean:
	$(RM) *~ *.aux *.dvi *.out *.log *.bbl *.blg *.toc *.nav *.snm

clean: distclean
	$(RM) $(TARGET)




.PHONY:	clean images

.SUFFIXES:	.pdf .ps .dvi .aux .tex
