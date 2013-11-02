# Scripts

General repository of small scripts and applications

## writeletter

Aid to writing letters using PanDoc + LaTeX to create a PDF output file.
Includes two support files for copying into ~/.pandoc:

*   `input/letter.markdown`

    The raw letter template, which contains a YAML metadata block with
all the variables needed to write a basic letter. It should be edited to
contain your name and address for ease of use.

    The content of the letter goes below the block. You don't need to
write a sign-off at the end as that will be dealt with automatically.


*   `templates/letter.latex`

    The LaTeX template use for converting to a PDF, essentially using
the standard "letter" class that comes with your TeX distribution.

    If you inserted a recipient's name in the metadata your letter
you'll get "Dear $name" and "Yours sincerely", otherwise "Dear Sir or
Madam" and "Yours faithfully". If you want to fiddle with any of this
stuff it's all in this template file.

To invoke manually:

    pandoc --to latex --template letter in.markdown -o out.pdf

To use the support script:

    writeletter new in.markdown
    # creates a fresh markdown file
    writeletter make in.markdown
    # converts to PDF (appends .pdf to name)

