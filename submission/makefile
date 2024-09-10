##########################################
## REVIEW MAKEFILE                      ##
## Author: Guilherme Sadovski           ##
## Contact: guilhermesadovski@gmail.com ##
## Date: 2023/11/07                     ##
##########################################

###########
# MD->PDF #
###########

# DEFINITION OF VARIABLES #
MDS = $(wildcard *.md)
MD2PDF = $(MDS:%.md=%.pdf)
PDFS = $(wildcard $(MD2PDF))
OUT_DIR = $(CLOUD)/work/research/sadovski2022

# CONVERSIONS #
%.pdf: %.md
	pandoc --citeproc -o $@ < $<

#####################
# PHONY CONVERSIONS #
#####################
all: $(MD2PDF) 

open: $(PDFS)
	$(PDFVIEWER) $(PDFS) \
	>/dev/null &

move:
	mv -f $(PDFS) $(OUT_DIR)

clean: 
	rm -f $(PDFS)

quit-md: move clean

.PHONY: all open move clean clean-tex clean-pdf clean-aux quit-md
