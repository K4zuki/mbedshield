include ../Makefile.in

#INPUT:=mbeDshield2015.md
INPUT:=mbeDshield.md
OUTPUT:=$(shell $(BASENAME) $(INPUT) .md)
PNG:=$(shell $(LS) ../pic/*.png)
#
#ifdef CSV
PICS:=$(PNG:.png=.mono.png)
#else
#PICS:=
#endif

all: docx html

docx: $(PICS)
	$(PANDOC) $(OPTIONS) --toc --reference-docx=$(PANSTYLES)/ref.docx $(INPUT) -o $(OUTPUT).docx

html: $(PICS)
	$(PANDOC) $(OPTIONS) --self-contained -thtml5 --template=$(PANSTYLES)/github.html --webtex $(INPUT) -o $(OUTPUT).html

tex:
	$(PANDOC) $(OPTIONS) --toc --template=template.tex --latex-engine=xelatex $(INPUT) -o $(OUTPUT).tex

pdf: tex
#	lualatex $(OUTPUT).tex;lualatex $(OUTPUT).tex
	xelatex $(OUTPUT).tex;xelatex $(OUTPUT).tex
#	$(PANDOC) $(OPTIONS) --toc --template=template.tex --latex-engine=xelatex $(INPUT) -o $(OUTPUT).pdf

%.mono.png: %.png
	$(PYTHON) $(CONV2MONO) --input $< --output $@

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
	rm ../pic/*.mono.png
