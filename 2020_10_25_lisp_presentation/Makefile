# See colors here: https://wiki.contextgarden.net/Color
# Latex templates: https://www.latextemplates.com/

.PHONY: phony all

NAME := lisp
THEME := "Berlin"
COLORTHEME = "seahorse"
LOGO = "images/Lisplogo.png"

# ARGS
PDF_ARGS = -t beamer -V theme=$(THEME) -V colortheme=$(COLORTHEME)  -V apsectration="169" --pdf-engine=xelatex
WITH_LOGO = -V logo=$(LOGO)

all: clean output output/$(NAME).pdf output/$(NAME).html

pdf: output output/$(NAME).pdf 

html: output output/$(NAME).html 

output:
	@mkdir -p ./output

output/%.pdf: Makefile | output
	pandoc $(PDF_ARGS) $(NAME).md -o $@

output/%.html: Makefile | output
	pandoc $(PDF_ARGS) $(NAME).md -o $@


clean: phony
	@rm -rf ./output
	@echo "output folder deleted"

run: phony output/style.pdf
	okular --presentation -p 0 output/$(NAME).pdf &
