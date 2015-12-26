include ../Makefile.in

INPUT:=mbeDshield2015.md
OUTPUT:=$(shell $(BASENAME) $(INPUT) .md)
CSV:=$(shell $(LS) *.csv)

ifdef CSV
PICS:=$(CSV:.csv=.png)
else
PICS:=
endif

all: docx html

docx: $(PICS)
	$(PANDOC) $(OPTIONS) --toc --reference-docx=$(PANSTYLES)/ref.docx $(INPUT) -o $(OUTPUT).docx

html: $(PICS)
	$(PANDOC) $(OPTIONS) --self-contained -thtml5 --template=$(PANSTYLES)/github.html --webtex $(INPUT) -o $(OUTPUT).html

tex:
	$(PANDOC) $(OPTIONS) --toc --template=template.tex --latex-engine=xelatex $(INPUT) -o $(OUTPUT).tex

pdf: tex
	xelatex $(OUTPUT).tex;xelatex $(OUTPUT).tex
#	$(PANDOC) $(OPTIONS) --toc --template=template.tex --latex-engine=xelatex $(INPUT) -o $(OUTPUT).pdf

%.png: %.csv
	$(PYTHON) $(CSV2PNG) --file $< --output $@

png: $(PICS)
	@echo "echo"

clean:
	if [ -f $(OUTPUT).docx ] ;then rm $(OUTPUT).docx ;fi
	if [ -f $(OUTPUT).html ] ;then rm $(OUTPUT).html ;fi
	if [ -f $(OUTPUT).tex ] ;then rm $(OUTPUT).tex ;fi
	if [ -f $(OUTPUT).out ] ;then rm $(OUTPUT).out ;fi
	if [ -f $(OUTPUT).aux ] ;then rm $(OUTPUT).aux ;fi
	if [ -f $(OUTPUT).log ] ;then rm $(OUTPUT).log ;fi
	if [ -f $(OUTPUT).toc ] ;then rm $(OUTPUT).toc ;fi
	if [ -f $(OUTPUT).pdf ] ;then rm $(OUTPUT).pdf ;fi
