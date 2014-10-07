# University of Tasmania Mathematics Style File and Thesis Template for LaTeX2e

## Historical note

*This material was previously available here:* http://staff.acecrc.org.au/~mdsumner/TCallaghan/

In ca. 2002 Tim Callaghan very kindly provided a LaTeX2e template for
a UTas thesis. The content here is a fairly faithful copy of his
original. Read the original summary file "utas_latex.html", which is
otherwise reproduced in this readme.

Michael Sumner

##What is this?

A style file is a way of getting LaTeX to do a lot of formatting and
processing for tasks that are so common that they are deemed style
file "worthy". The generation of a PhD thesis is once such task that
(in my opinion) falls into this category. Since the Research Higher
Degrees Resource Book lays out fairly specific formatting guidelines
for the thesis it becomes the task of the style file to automatically
meet these formatting requirements. Basically then, we can visualise a
style file in this instance as performing the appropriate formatting
commands behind the scenes. The advantage of this approach is two
fold: It enables easy alterations to the thesis as a whole and, more
importantly, it frees the student from the sometimes troubling
formatting problems that arise, allowing them to focus entirely on the
contents of the thesis.

A template is, in this instance, a set of basic fundamental files that
constitute the various elements of a thesis. These can be used as
bare-bones starting points for populating the thesis with ideas. The
template files include chapters, appendices, bibliography etc. To make
a thesis from the template all one needs to do is edit the appropriate
files with one's own content and the overall structure should already
be in place.

 
##What this isn't.

This is not a tutorial on how to use LaTeX. There are many fine
references on the net that address this issue. A good place to start
is "The (Not So) Short Introduction to LaTeX2e" which is not only a
good introduction but also serves as a handy reference manual . Thus
in the following discussion I assume that you know what LaTeX is and
how to use it on your operating system of choice. I also assume you
know how to install packages (add-ons for LaTeX that increase its
functionality) since the thesis style file is dependent on a few
packages for fancy effects...no point reinventing the wheel.

 
##Who can use it?

This style file is designed primarily for students of mathematics at
UTas who are undertaking a PhD. However, only very minor changes need
to be made to the wording in a few places to use it as a template for
an honours or Masters thesis as well. In fact, there is no particular
reason why this could be not used for, say, an Arts thesis (Shock,
Horror!) since it is mainly about the formatting and less about the
content. However, the heading and chapter structure has been chosen so
as to be more in line with standard practice in the scientific
streams. Again, if you know what you're doing then it's really not
that difficult to modify the style file at the appropriate places. I
have tried to comment it quite heavily so that interested persons can
see how it does all its work and, hopefully, make changes that reflect
personal tastes etc. Okay, if you're still with me then read on...

 
##How do you use it?

Follow the steps below to set your computer up to use the thesis style file and templates. 

###Get the required packages

You must ensure that your LaTeX installation has the following packages installed.

* 'graphicx' for graphics manipulation
* 'makeidx' for generating the index
* 'fancyhdr' for nice headers and footers.
* 'tocbibind' for adding table of contents entries for bibliography, index etc.
* 'sectsty' for generating stylised chapter and section headings.

I believe the first two are part of any standard LaTeX installation
but unless you have a complete installation with all packages the
remaining three will have to be obtained. This is easy enough to
do. Just go to CTAN and grab the ones that are listed above and follow
their self install directions for your particular OS.

 
###Download the thesis files

You must download the following files and save them all to the same directory on your computer 

* The thesis style file mathphdthesis.sty
* The thesis TeX file thesis.tex
* The prelude TeX file prelude.tex
* The new commands TeX file newcom.tex
* The chapter TeX files chap1.tex, chap2.tex, chap3.tex and chap4.tex
* The appendix switch TeX file app0.tex
* The appendix TeX files app1.tex and app2.tex
* The bibliography switch TeX file biby.tex
* The sample bibliography database thesis.bib
* The index switch TeX file index.tex
* The UTas graphics logo Utas_vert_BW.ps

If you prefer, you can just download the zip archive thesis.zip which
contains all the files listed above as well as the dvi and pdf
versions of the bare bones thesis that you will generate in the next
section.

 
###Test the bare-bones files

Now that you have all the files in one directory with all the relevant
packages installed you can make the bare bones thesis by running LaTeX
on the file 'thesis.tex'. In order for LaTeX to determine the page
numbers correctly in the table of contents you have to execute the
commands in the following order.

1. Run LaTeX on thesis.tex
2. Run BIBTex on thesis.tex
3. Run MakeIndex on thesis.idx (note the different file extension)
4. Run LaTeX again on thesis.tex
5. Run LaTeX once more on thesis.tex

This may look a little strange but this sequence of commands is
necessary to make sure LaTeX gets all its page numbers and references
correct. If you are interested in why this is so, read up on how LaTeX
generates its table of contents, bibliography and index.

Now look at the dvi file that is produced. It should look like this
thesis.dvi (or the pdf version thesis.pdf). If it does, then all
that's left to do is to read the next section to find out how to
customise your name, abstract etc. for inclusion in the thesis.

If it doesn't work I would guess something wrong with the LaTeX
processing step so try repeating the commands above. It's also
possible that your package installation went awry so perhaps reinstall
(?). Other than that, your guess is as good as mine. You can try
emailing me (see below) but I don't guarantee any form of dedicated
technical support. I can only offer advice and suggestions etc.

 
###Customise the template

Now that you have a working bare-bones thesis you can modify the parts
that will customise it for you personally. The file that you will need
to edit is 'prelude.tex'. If you have a look in this file you will see
the following lines...

> \title{PLACE THESIS TITLE HERE} % use all capital letters
> \author{Your Name} % use mixed upper & lower case
> \prevdegrees{B.A. B.Sc. Hons (Qld)} % Used to specify your previous degrees...use mixed upper & lower case
> \advisor{Dr Ask Me} % example: Professor Lawrence K. Forbes
> \dept{Mathematics} % your academic department
> \submitdate{August, 2004} % month & year of your thesis submission

Just simply change your relevant details in the fields. For example, if your name was John Smith B.A. Hons (QUT) and you were studying Ship Hydrodynamics you would put
\title{SHIP HYDRODYNAMICS} % use all capital letters
\author{John Smith} % use mixed upper & lower case
\prevdegrees{B.A. Hons (QUT)} % Used to specify your previous degrees...use mixed upper & lower case
\advisor{Dr Ask Me} % example: Professor Lawrence K. Forbes
\dept{Mathematics} % your academic department
\submitdate{August, 2004} % month & year of your thesis submission

Now change the abstract and acknowledgements text by altering the text between the {} braces after the commands \newcommand{\abstextwithesis} and \newcommand{\acknowledgement}.
Look at the very top of the file 'prelude.tex'. You will see a lot of commands with 'true' contained at the end of the command name. These are actually flags that specify which elements of the preface you want to generate. By default all the commands are set to true (include everything) but if you don't want to include something you merely change the 'true' to 'false' at the end of the command name. For example, to not include the title page you would change \titlepgtrue to \titlepgfalse. This is actually a handy thing to do since the title page contains the University logo on it and this causes a delay in display refresh times when viewing the dvi file since the image has to load each time. If your computer is slow-ish you probably want to set the above command to false to leave it out until you want to print a rough draft etc.


 
###Populate the Thesis pages with original ideas!

The easy part, or the hard part, depending on what we are talking about. From here all that remains to do is to fill out the chapters with your own work. You edit the chapters as you would any normal LaTeX document by placing your text and markup commands inside a chapter declaration. See the files 'chap1.tex', 'chap2.tex' etc. for examples. You can also add more packages to the preamble (after the documentclass declaration) to extend the functionality of LaTeX even more but you should always be careful of nullifying the formats that are set up in the style file. To make sure your commands are local you should always declare them inside an environment (inside {} braces).
A sample bibliography database has also been included to give you an idea of how to set one up. See the BibTeX manual for more help on this topic. In addition, appendices have been added but these can be removed if needs been by simply commenting the appropriate include statements out in 'thesis.tex'.

Perhaps this is not the best way to produce a thesis but it's a reasonable start and hopefully over time we can all make suggestions about what this style file should include so that the department has a quality style file that can be used by all students. For this reason suggestions and comments are most welcome and should be forwarded to me by way of the contact below. 

 

 
### Acknowledgements

I obtained the information to make this file from a variety of sources on the internet. In particular I have drawn on the work of John Castelloe http://www.divms.uiowa.edu/help/uithesis/index.html. I have used his templating system as it is the obvious way to do things neatly. I have also used some of his code for populating dynamic content. 

Some other useful links that I have profited from along the way are...
http://theoval.sys.uea.ac.uk/~gcc/family/nicky/csed/advice.html General tips and tricks for LaTeX2e
http://zoonek.free.fr/LaTeX/LaTeX_samples_chapter/0.html Some sample chapter heading styles
http://www.cs.brown.edu/system/software/latex/packages-by-category.html LaTeX packages by category
http://www-sigproc.eng.cam.ac.uk/~jrh1008/Resources/Latex/LaTeXPackages.html Packages aimed at thesis preparation

I don't pretend to take credit for originality, however the general code design has been altered enough so as to justifiably call it my own...sort of ;) 

Please send any comments (especially suggestions and bugs/errors) to Tim Callaghan  tgc@hilbert.maths.utas.edu.au





