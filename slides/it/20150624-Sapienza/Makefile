#
# $Id: Makefile 152 2015-06-24 04:46:28Z nicb $
#
# You should set the INCLUDED_MAKE_PATH variable to wherever you have
# downloaded the templates module.
# You may find the template module cvs repository at the following CVSROOT:
# 
# :<mode>:<name>@cvs.miu-ft.org:/cvsroot/ec-stuff
#
# and the module name is 'templates'
#
INCLUDED_MAKE_PATH=../materiali
#
# there should be nothing to be changed below here
#

#
# $Id: Makefile 152 2015-06-24 04:46:28Z nicb $
#
TARGET=slides.pdf 


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
	$(PDFLATEX) $<
	$(RM) $@
#	$(BIBTEX) $* 
	$(PDFLATEX) $<
	$(RM) $@
	$(PDFLATEX) $<

images:
	$(MAKE) -C $(IMAGEDIR) -$(MAKEFLAGS)

distclean:
	$(RM) *~ *.aux *.dvi *.out *.log *.bbl *.blg *.toc *.nav *.snm

clean: distclean
	$(RM) $(TARGET)




.PHONY:	clean images

.SUFFIXES:	.pdf .ps .dvi .aux .tex
