# Source files in order
SOURCES = intro.md \
          education_and_experience.md \
          research_interests_and_expertise.md \
          highlighted_projects.md \
          journal_publications.md \
          conference_publications.md \
          technical_reports.md \
          professional_activities.md \
          patents.md \
          personal_interests.md

all: pdf html README

pdf: resume.pdf

html: resume.html

README: README.md

resume-styled: resume-styled.html

README.md: $(SOURCES)
	cat $(SOURCES) > ../README.md 

resume.pdf: $(SOURCES)
	pandoc $(SOURCES) -o Michael_Lawson_Resume.pdf --pdf-engine=pdflatex \
		-V geometry=margin=0.75in \
		-V colorlinks=true \
		-V linkcolor=blue \
		-V urlcolor=blue

resume.html: $(SOURCES)
	pandoc $(SOURCES) -o Michael_Lawson_Resume.html --embed-resources --standalone --css=resume.css

# HTML with nice styling and table of contents
resume-styled.html: $(SOURCES)
	pandoc $(SOURCES) -o Michael_Lawson_Resume-styled.html \
		--embed-resources \
		--standalone \
		--css=resume.css \
		--toc \
		--toc-depth=2

clean:
	rm -f Michael_Lawson_Resume.pdf Michael_Lawson_Resume.html Michael_Lawson_Resume-styled.html ../README.md

.PHONY: all pdf html resume-styled README clean
