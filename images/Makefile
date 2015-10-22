#
# $Id: Makefile 7 2014-02-04 18:16:40Z nicb $
#
TARGETS=Nono-PPPD-schema.pdf CONTAKTE-concept.png
ISCONVERT=inkscape -d 150

all: $(TARGETS)

clean:
	$(RM) $(TARGETS)

.PHONY: clean

.SUFFIXES: .pdf .png .svg

%.pdf: %.svg
	$(ISCONVERT) -A $@ $<

%.png: %.svg
	$(ISCONVERT) -e $@ $<
