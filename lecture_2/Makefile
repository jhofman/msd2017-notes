lecture:=$(shell basename `pwd`).tex
template:='\Huge{Notes from uni} \\normalsize \subfile{uni/uni.tex} \pagebreak \\newpage'

all:
	cat header.tex > $(lecture)
	for uni in `find . -type d -maxdepth 1 | egrep '[a-z]+[0-9]+' | sed 's|./||'`; \
	  do echo $(template) | sed "s/uni/$$uni/g" >> $(lecture); \
	done
	cat footer.tex >> $(lecture)

	pdflatex $(lecture)

clean:
	rm *.aux *.log *.out *~
	rm -rf auto
