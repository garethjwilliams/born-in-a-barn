OUT=../ebooks
SRC=../text
ART=../art
TITLE=born-in-a-barn-by-gareth-williams
COVER=born-in-a-barn-cover

all: \
	$(OUT)/$(TITLE).azw3 \
	$(OUT)/$(TITLE).mobi \
	$(OUT)/$(TITLE).epub \
	$(OUT)/$(TITLE)-letter.pdf \
	$(OUT)/$(TITLE)-a4.pdf

$(OUT)/$(TITLE)-a4.pdf: \
	$(OUT)/$(TITLE).epub
	ebook-convert $(OUT)/$(TITLE).epub \
	$(OUT)/$(TITLE)-a4.pdf \
	--preserve-cover-aspect-ratio \
	--paper-size=a4

$(OUT)/$(TITLE)-letter.pdf: \
	$(OUT)/$(TITLE).epub
	ebook-convert $(OUT)/$(TITLE).epub \
	$(OUT)/$(TITLE)-letter.pdf \
	--preserve-cover-aspect-ratio

$(OUT)/$(TITLE).azw3: \
	$(OUT)/$(TITLE).epub
	ebook-convert $(OUT)/$(TITLE).epub \
	 $(OUT)/$(TITLE).azw3

$(OUT)/$(TITLE).mobi: \
	$(OUT)/$(TITLE).epub
	ebook-convert $(OUT)/$(TITLE).epub \
	 $(OUT)/$(TITLE).mobi

$(OUT)/$(TITLE).epub: \
	$(SRC)/$(TITLE).md \
	$(ART)/$(COVER).png
	pandoc $(SRC)/$(TITLE).md \
	-o $(OUT)/$(TITLE).epub \
	--epub-cover-image=$(ART)/$(COVER).png \
	--wrap=none

clean:
	rm $(OUT)/*
