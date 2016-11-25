TITLE = 2016_talk_h2oSL_THW

$(TITLE).pdf: $(TITLE).tex header.tex
	xelatex $<

notes: $(TITLE)_withnotes.pdf

all: $(TITLE).pdf notes web clean

clean:
	rm -f *.{aux,log,nav,out,snm,toc,vrb}

$(TITLE)_withnotes.pdf: $(TITLE)_withnotes.tex header.tex
	xelatex $(TITLE)_withnotes
	pdfnup $(TITLE)_withnotes.pdf \
		--nup 1x2 --no-landscape --paper letterpaper --frame true --scale 0.9
	mv $(TITLE)_withnotes-nup.pdf $(TITLE)_withnotes.pdf

$(TITLE)_withnotes.tex: $(TITLE).tex Ruby/createVersionWithNotes.rb
	Ruby/createVersionWithNotes.rb $(TITLE).tex $(TITLE)_withnotes.tex

web: $(TITLE).pdf $(TITLE)_withnotes.pdf
	scp $(TITLE).pdf \
		nhejazi@arwen.berkeley.edu:/mirror/data/pub/users/nhejazi/present/$(TITLE).pdf
	scp $(TITLE)_withnotes.pdf \
		nhejazi@arwen.berkeley.edu:/mirror/data/pub/users/nhejazi/present/$(TITLE)_withnotes.pdf
	ssh nhejazi@arwen.berkeley.edu \
		'chmod go+r /mirror/data/pub/users/nhejazi/present/$(TITLE).pdf'
	ssh nhejazi@arwen.berkeley.edu \
		'chmod go+r /mirror/data/pub/users/nhejazi/present/$(TITLE)_withnotes.pdf'
