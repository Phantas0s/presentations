# See colors here: https://wiki.contextgarden.net/Color
# Latex templates: https://www.latextemplates.com/

.PHONY: phony all

NAME := lisp
THEME := "Berlin"
COLORTHEME = "seahorse"

# ARGS

# markdown-raw_tex: display slash correctly, and not as "begin latex shenanigans"
PDF_ARGS = -t beamer -V theme=$(THEME) -V colortheme=$(COLORTHEME) -V apsectration="169"

all: output output/lisp.pdf

pdf: output output/lisp.pdf 

output:
	@mkdir -p ./output

output/%.pdf: Makefile | output
	pandoc $(PDF_ARGS) $(NAME).md -o $@

clean: phony
	@rm -rf ./output
	@echo "output folder deleted"

presentation: phony output/style.pdf
	okular --presentation -p 0 output/$(NAME).pdf &
