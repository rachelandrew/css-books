css-books
=========

Example files for building CSS books. Used in my presentation "CSS and Ebooks". Resources and more information about CSS and creating ebooks in a variety of formats can be found on the page for that presentation at http://rachelandrew.co.uk/presentations/css-books.

## Using these files

The file book.html contains 3 articles from my blog to create a "book" of three chapters.

These files are for use when creating an ebook in formats for EPUB, MOBI and PDF using the following commandline tools. 

* [pandoc](http://johnmacfarlane.net/pandoc/)
* [Kindlegen](http://www.amazon.com/gp/feature.html?docId=1000765211)
* [Prince](http://www.princexml.com/)

Download and install these tools first. Prince is a commercial tool however you can use it free of charge for non-commercial usage.

Git clone this repository.

### Create an EPUB

Change into the css-ebboks directory and at the cli run:

    > pandoc -o builds/book.epub book.html --epub-metadata=metadata.xml --toc --toc-depth=2 --epub-cover-image=cover.png --epub-stylesheet=epub-styles.css

### Create a MOBI

Use your EPUB as the source for the Kindlegen tool.

    > /Applications/KindleGen/kindlegen builds/book.epub

### Create a PDF

This uses the toc.html file to create the table of contents.

    > prince -s pdf-styles.css toc.html book.html builds/book.pdf

I've avoided doing much in the way of typography in these examples but feel free to fork this and make it pretty.