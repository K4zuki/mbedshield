include ../Makefile.in

INPUT = mbeDshield2015.md
OUTPUT = $(shell basename $(INPUT) .md)
CSV = $(shell ls *.csv)
PICS = $(CSV:.csv=.png)


all: docx html png

docx: $(PICS)
	$(PANDOC) $(OPTIONS) --reference-docx=$(PANSTYLES)/ref.docx $(INPUT) -o $(OUTPUT).docx

html: $(PICS)
	$(PANDOC) $(OPTIONS) --self-contained -thtml5 --template=$(PANSTYLES)/github.html --webtex $(INPUT) -o $(OUTPUT).html

%.png: %.csv
	$(PYTHON) $(CSV2PNG) --file $< --output $@

png: $(PICS)

clean:
	if [ -f $(OUTPUT).docx ] ;then rm $(OUTPUT).docx ;fi
	if [ -f $(OUTPUT).html ] ;then rm $(OUTPUT).html ;fi
