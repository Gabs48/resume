IMAGE_DIR = img
PDFLATEX = xelatex
BIBTEX = bibtex
MAIN_TEX = Urbain_Gabriel_resume.tex
JOB = Urbain_Gabriel_resume
JOB_AUX = $(JOB).aux
JOB_PDF = $(JOB).pdf

all: pdf

pdf: image
	$(PDFLATEX) -jobname=$(JOB) $(MAIN_TEX)
	#$(BIBTEX) $(JOB_AUX)
	$(PDFLATEX) -jobname=$(JOB) $(MAIN_TEX)
	$(PDFLATEX) -jobname=$(JOB) $(MAIN_TEX)

image:
	if [ -d "$(IMAGE_DIR)" ]; then \
		cd $(IMAGE_DIR); $(MAKE) all; \
	fi

clean: clean-pdf clean-tex

clean-pdf:
	rm -f *.pdf
	if [ -d "$(IMAGE_DIR)" ]; then \
		cd $(IMAGE_DIR) ; $(MAKE) clean; \
	fi

clean-tex:
	rm -f *.cut *.aux *.bbl *.blg *.lof *.log *.lot *.toc *.out

clean-git:
	git clean -f
