lecture:=$(shell basename `pwd`).tex
template:='\pagebreak \\newpage \\noindent\Huge{Notes from uni} \\normalsize \setcounter{section}{0} \subfile{uni/uni.tex}'

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
