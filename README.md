# mobi-template
template directory for building a mobi file suitable for Kindle ebooks

##instructions

* Pull this project.
* Save your file as html, eg text.html, into the top level directory (ie the one with sed.sed in it).
* run sed against your text.html ie *sed -f sed.sed myfile.html>t.html* this uses the edit commands in sed.sed to bulk edit the file. You may need to modify sed.sed for your use depending on what styles/format options you end up with in your text.html. The idea is to get a clean html file in t.html.
* copy t.html to the kindle directory. Rename it to text.html.
* delete all the header stuff in this new text.html, everything above </body>, and replace it with the header in text.html_template.
* Check your class="xxx" entries in text.html to make sure they match up with those in styles.css. You can open text.html in your browser to see how it looks.
* Edit toc.ncx and add your chapters in there. Make sure each chapter has an id="xxx" in text.html and that it matches up with the pointers in this file (src=xxx).
* Edit toc.html and nav.html and add the same information. You probably only need two of these three files but once you have done one it is simple enough to make both the other two.
* Note the landmarks section at the end of nav.html. This solves the problem of Kindle not opening the book at the beginning the first time it is opened.
* Make a cover image. It ought to be a jpeg file around 1800x2880 pixels. Call it cover.jpg and put it into the kindle/images directory (overwrite the dummy one there).
* download the Kindle Previewer from http://www.amazon.com/gp/feature.html?docId=1000765261 and install it. There are versions for Windows and Mac. I used the WIndows version running under Wine on my Linux machine.
* Use the Kindle Previewer to open the opf file and let it generate and display your Mobi file. Verify that it looks right, check the build log (arrows under the OK button) for probems. It's a bit clunky in style but very functional.
* I copied the resulting mobi file to the Kindle app on my Android phone for a second check.
* upload the mobi file to Amazon when you're happy with it. You'll need to upload your cover jpg file separately as well so Amazon can use it without unpacking your mobi.

