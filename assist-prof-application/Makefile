BASENAME = propunere-cariera
TEX = $(addsuffix .tex, $(BASENAME))
PDF = $(addsuffix .pdf, $(BASENAME))
PDFLATEX = pdflatex
OUT_DIR = texfiles
IMG_DIR = img

.PHONY: clean all

all: $(PDF)

$(PDF): $(TEX)
	# Rebuild image files, if any.
	-test -d $(IMG_DIR) && test -f $(IMG_DIR)/Makefile && make -C $(IMG_DIR)
	# Create out directory
	-test -d $(OUT_DIR) || mkdir $(OUT_DIR)
	$(PDFLATEX) -output-directory $(OUT_DIR) $<
	$(PDFLATEX) -output-directory $(OUT_DIR) $<
	ln -f $(OUT_DIR)/$@ .

clean:
	-rm -fr $(OUT_DIR)
	-rm -f $(PDF)
	-test -d $(IMG_DIR) && test -f $(IMG_DIR)/Makefile && make -C $(IMG_DIR) clean
